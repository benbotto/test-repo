#### What a Cluster: Deployment using Kubernetes and Helm

Here at Benningfield Group, the systems that we develop have slowly migrated from monoliths to microsystems in the past decade or so.  Our typical systems are composed of many small, constituent pieces.  An application may be made of a public website, an API server or two, a handful of databases, lions and tigers and bears, oh my!  Each of these pieces is baked into a Docker image and then moved through development, QA, UAT, and finally to production.  That's great because each service is immutable: if an image passes QA, the *identical* image is deployed to UAT; if it passes UAT then that *exact* image is pushed to production.  And when a bug is identified, a technician can deploy and analyze a perfect production replica locally.  But all that in mind, the transition to microservices and containers comes bearing a new complexity: deployment.  Manually standing up a system in its entirety would be a nightmare.  An engineer would need to understand all of the interconnected dependencies, deployment order, and location and version of each image.  That's just not feasible.

The deployment challenge described above led to the advent of container orchestration platforms, the most notable of which is Kubernetes, or k8s for short.  All major cloud providers, including Google Cloud, AWS, Digital Ocean, and Microsoft Azure, now support k8s, and its rapid adoption has made it the de facto standard for the dev-ops industry.  K8s and its package manager, Helm, let systems engineers describe and version the state of a system in a Helm Chart, and then deploy that chart to a local or cloud-based server cluster.

#### Goal

For me, getting started with k8s was quite a challenge.  The learning curve is steep, and I had a hard time finding up-to-date tutorials that involve deploying a system with dependencies.  In this tutorial we'll create an API application and bake that into a Docker image.  We'll then deploy that image to a local k8s cluster and expose it to external traffic through a load balancer.  Lastly, we'll add a database dependency into the mix and set up communication between the API and database services.

#### Prerequisites

If you’re going to follow along with the remainder of this tutorial, the following software needs to be installed.

1. Virtualbox version 6, and the extension pack.  (You can use another hypervisor if you prefer, but Virtualbox is supported by Minikube for Windows, Linux, and Mac.)
2. Docker version 18.09.
3. Kubernetes version 1.13.
4. Minikube version 0.32.
5. Helm version 2.12.
6. Node.js version 10.  (This one's optional.  If you prefer you can use [my code](https://github.com/benbotto/k8s-tutorial-api).)

#### Making an API Image

With the prerequisites in place, we’re going to build a trivial “Hello, world” API using Node.js and Express.  Start by making a new `k8s-tutorial-api` directory, initializing npm, and installing express and forever as dependencies.

```
npm install -g yarn # Feel free to use npm instead of yarn.
mkdir k8s-tutorial-api
cd k8s-tutorial-api
yarn init
yarn add express forever
```

Next create an [`app.js`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.0.1/app.js) file and add the following code to it.

```javascript
async function main() {
  const express  = require('express');
  const app      = express();
  const port     = 3000;

  app.get('/', (req, res) => res.json({hello: 'world'}));

  await app.listen(port);
  console.log(`Listening on port ${port}.`);
}

main();
```

If you run `node app` and then connect to http://localhost:3000 you’ll see a `{"hello":"world"}` response.

Now add a [`Dockerfile`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.0.1/Dockerfile) with the following code:

```
FROM node:dubnium-alpine

WORKDIR /var/www/node/k8s-tutorial-api

COPY ./ ./

RUN npm install -g yarn forever && \
  yarn install --production

USER node

EXPOSE 3000

CMD ["forever", "app.js"]
```

Also add a [`.dockerignore`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.0.1/.dockerignore) file and ignore the `node_modules` folder and npm's debug log.

```
node_modules
npm-debug.log
```

Building Docker images is outside of the scope of this tutorial, but in a nutshell the above copies the contents of the `k8s-tutorial-api` folder into an image and installs a few npm dependencies.  When the image is utilized, the command `forever app.js` will be issued, running the app on the exposed port, 3000.  So, go ahead and build the image.

```
docker build -t k8s-tutorial-api:latest .
```

Then tag and push the image your container repository.  I’m using Docker Hub, which provides a free repository.

```
docker tag k8s-tutorial-api:latest avejidah/k8s-tutorial-api:latest
docker tag k8s-tutorial-api:latest avejidah/k8s-tutorial-api:<VERSION>
docker push avejidah/k8s-tutorial-api:latest
docker push avejidah/k8s-tutorial-api:<VERSION>
```

Obviously, swap out `<VERSION>` such that it matches the version of your application.  I tagged this as version 1.0.1, and you can see the source here: [https://github.com/benbotto/k8s-tutorial-api/tree/1.0.1](https://github.com/benbotto/k8s-tutorial-api/tree/1.0.1).

#### Make a Local Cluster and Initialize Tiller

Now that we have a basic API, we need to start thinking about deploying to a k8s cluster.  A cluster is a group of one or more virtual or physical machines, called nodes in k8s terms.  In this tutorial we'll use Minikube to make a local cluster, so fire it up.

```
minikube start
```

That command adds a new "minkube" VM in virtual box (`vboxmanage list runningvms`); it hosts your local cluster.  The k8s CLI tool (it's pronounced "cube cuddle," dammit!) will be connected to it: `kubectl config view`.

K8s is pretty low level.  The k8s package manager, [Helm](https://helm.sh/), abstracts away some of the gory details, eliminates a bit of the repetitiveness, and makes it easier to get started with k8s.  Let's initialize Helm by adding the Helm server, Tiller, to our local cluster.

```
helm init
```

#### Create a Helm Chart for the API

Helm has a handy chart generator that can help you to get started building your first chart, but we're going to build ours manually for the sake of learning.  Let's start off by making a new `k8s` directory with a `templates` folder in it.  Inside the `templates` folder, create a [`deployment.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.1.0/k8s/templates/deployment.yaml) file.

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: k8s-tutorial-api-deployment
  labels:
    app.kubernetes.io/name: k8s-tutorial-api
    app.kubernetes.io/instance: {{ .Release.Name }}
    app.kubernetes.io/version: {{ .Values.image.tag }}
    app.kubernetes.io/component: api
    app.kubernetes.io/part-of: k8s-tutorial
    app.kubernetes.io/managed-by: helm
spec:
  replicas: {{ .Values.replicaCount }}
  selector:
    matchLabels:
      app.kubernetes.io/name: k8s-tutorial-api
      app.kubernetes.io/instance: {{ .Release.Name }}
  template:
    metadata:
      labels:
        app.kubernetes.io/name: k8s-tutorial-api
        app.kubernetes.io/instance: {{ .Release.Name }}
    spec:
      containers:
      - name: k8s-tutorial-api
        image: avejidah/k8s-tutorial-api:{{ .Values.image.tag }}
        ports:
        - containerPort: 3000
          name: http
        readinessProbe:
          httpGet:
            path: /
            port: 3000
          initialDelaySeconds: 1
          periodSeconds: 1
        livenessProbe:
          httpGet:
            path: /
            port: 3000
          initialDelaySeconds: 1
          periodSeconds: 5
```

The deployment defines a [ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/) that will bring up pods.  A pod is a group of one or more containers running on one or more nodes.  The number of pods created is defined by the `spec.replicas` property, and the name of the resulting pods will be based on the `name` property.

The above deployment is pretty much identical to the [deployment definition](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) in the k8s docs, so take a minute to read the manual.  There are some key differences, though.  First off, some variables are used, like `{{ .Values.image.tag }}`.  The Helm CLI can read Go templates, which allows users to add dynamic content to manifest files.  More on that in a bit.  Second, the [recommended labels](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels/) are used in the `metadata.labels` section.  These labels uniquely define each resource in the overall system, and other resources can match these labels.  Third, we've used our Docker image, `avejidah/k8s-tutorial-api` in my case, which exposes the API on port 3000.  And lastly, we've added a specification for health checks.

Now we need to expose the API so that we can get external traffic into our cluster.  We'll do this with a [`NodePort`](https://kubernetes.io/docs/concepts/services-networking/service/#nodeport)-type service.  This will cause k8s to allocate and assign a port to each node, and incoming traffic on that port will be proxied to our API service.  Alongside the [`k8s/templates/deployment.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.1.0/k8s/templates/deployment.yaml) file, create [`k8s/templates/service.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.1.0/k8s/templates/service.yaml) and populate it with the following.

```
kind: Service
apiVersion: v1
metadata:
  name: k8s-tutorial-api-service
  labels:
    app.kubernetes.io/name: k8s-tutorial-api
    app.kubernetes.io/instance: {{ .Release.Name }}
    app.kubernetes.io/version: {{ .Values.image.tag }}
    app.kubernetes.io/component: api
    app.kubernetes.io/part-of: k8s-tutorial
    app.kubernetes.io/managed-by: helm
spec:
  selector:
    app.kubernetes.io/name: k8s-tutorial-api
    app.kubernetes.io/instance: {{ .Release.Name }}
  ports:
  - protocol: TCP
    port: 80
    targetPort: 3000
  type: NodePort
```

The metadata should look familiar, as it's mostly the same as the deployment resource.  The `spec.selector` defines which pods this `NodePort` should target, and `spec.ports` says that incoming traffic on port 80 should target port 3000 on the matched pods.  Note that k8s will assign a virtual IP to the service, known as a `ClusterIP`, and allocate a high-number port that each node will proxy to the service.  That is, once deployed you'll be able to access the API externally using an IP and port that k8s assigns. 

We also have to define our chart in [`k8s/Chart.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.1.0/k8s/Chart.yaml).  This file has some self-explanatory information about the Helm chart, such a the chart's version, name, and description.

```
apiVersion: v1
version: 1.0.0
description: A Helm chart for the k8s-tutorial-api.
name: k8s-tutorial-api
```

Finally, we need to define the values that Helm will pass to our templates, like the Docker image tag and the number of replicas.  In the `k8s` folder define [`values.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.1.0/k8s/values.yaml) like so.

```
replicaCount: 1

image:
  tag: latest
```

If you have followed along successfully so far, then your application should look like mine: [https://github.com/benbotto/k8s-tutorial-api/tree/1.1.0](https://github.com/benbotto/k8s-tutorial-api/tree/1.1.0).  I've built, tagged, and pushed this as version 1.1.0.

#### Installing the Chart

With our deployment and service defined, we can install the chart using Helm.  Let's deploy it using the newly-created Docker image, 1.1.0, with 3 replicas.

```
helm install --name=k8s-tutorial-api ./k8s --set replicaCount=3,image.tag=1.1.0
```

The output will contain the deployment, service, and three pods.  Something like this:

```
NAME:   k8s-tutorial-api
LAST DEPLOYED: Tue Jan  8 12:12:12 2019
NAMESPACE: default
STATUS: DEPLOYED

RESOURCES:
==> v1/Service
NAME                      TYPE      CLUSTER-IP      EXTERNAL-IP  PORT(S)       AGE
k8s-tutorial-api-service  NodePort  10.104.181.101  <none>       80:32667/TCP  0s

==> v1/Deployment
NAME                         DESIRED  CURRENT  UP-TO-DATE  AVAILABLE  AGE
k8s-tutorial-api-deployment  3        3        3           0          0s

==> v1/Pod(related)
NAME                                          READY  STATUS   RESTARTS  AGE
k8s-tutorial-api-deployment-5555f6bdb4-cnqfw  0/1    Pending  0         0s
k8s-tutorial-api-deployment-5555f6bdb4-kvrb6  0/1    Pending  0         0s
k8s-tutorial-api-deployment-5555f6bdb4-sq7jq  0/1    Pending  0         0s
```

It'll take a minute to complete the rollout.  You can run the following to see the deployment status.

```
kubectl rollout status deployment.v1.apps/k8s-tutorial-api-deployment
```

#### Connecting to the Service

As mentioned, k8s allocates a high-value port that our nodes will proxy to our service.  We can find that port by inspecting the services.

```
kubectl get services
```

You'll see output similar to this, which shows that my service will be exposed on port 32726.

```
NAME                       TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
k8s-tutorial-api-service   NodePort    10.100.98.151   <none>        80:32726/TCP   144m
kubernetes                 ClusterIP   10.96.0.1       <none>        443/TCP        24h
```

You can connect to the service via a web browser by issuing the command `minikube service k8s-tutorial-api-service`.  The url is your cluster's IP (`minikube ip`) combined with the proxy port that k8s allocated.

#### Adding Ingress

Right now, connecting to our API is a bit obscure given that it's only accessible over an ephemeral port.  Ideally we should be able to connect to our API on port 80.  We'll use an [ingress resource](https://kubernetes.io/docs/concepts/services-networking/ingress/) to manage external access.  An ingress resource defines rules that allow inbound connections to access services within the cluster.  Those rules require an [ingress controller](https://kubernetes.io/docs/concepts/services-networking/ingress/#ingress-controllers) to be running inside the cluster.  There are a number of different controllers to choose from, and the default varies between cloud providers.  Minikube by default uses the [`nginx-ingress`](https://github.com/helm/charts/tree/master/stable/nginx-ingress) controller, and that's the one we're going to use.  Since it's Minikube's default, we could use it implicitly by [enabling the ingress addon](https://kubernetes.github.io/ingress-nginx/deploy/#minikube), but it's best to explicitly install a controller as a dependency.  That way if we later deploy to a cloud provider we can rest assured that the same controller will be used in all our environments.

Like the applications we develop, Helm charts can have dependencies.  Helm is, after all, a package manager.  Subcharts can be manually added to our `k8s/charts`  directory, or, alternatively, we can add a `requirements.yaml` file and declare dependencies in a few short lines.  We'll use the latter method, so create [`k8s/requirements.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.2.0/k8s/requirements.yaml).

```
dependencies:
- name: nginx-ingress
  version: 1.1.3
  repository: https://kubernetes-charts.storage.googleapis.com
```

Note that the repository url is the "stable" Helm repository, found by executing `helm repo list`, and 1.1.3 is the latest version of the `nginx-ingress` *chart* at the time of writing.  You can find packages using `helm search`.

Now we just need to define some ingress rules, specifying where to route incoming traffic.  Our routing rules are simple--route all HTTP traffic to our API service--but keep in mind that the `nginx-ingress` controller provides powerful capabilities.  It allows you to route traffic to different services based on path (a.k.a. layer-7 routing), add sticky sessions, do TLS terminiation, etc.  Anyway, go on and define [`k8s/templates/ingress.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.2.0/k8s/templates/ingress.yaml).

```
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: k8s-tutorial-api-ingress
  labels:
    app.kubernetes.io/name: k8s-tutorial-api
    app.kubernetes.io/instance: {{ .Release.Name }}
    app.kubernetes.io/version: {{ .Values.image.tag }}
    app.kubernetes.io/component: api
    app.kubernetes.io/part-of: k8s-tutorial
    app.kubernetes.io/managed-by: helm
  annotations:
    kubernetes.io/ingress.class: nginx
    nginx.ingress.kubernetes.io/ssl-redirect: "false"
    ingress.kubernetes.io/hsts: "false"
spec:
  rules:
  - http:
      paths:
      - path: /
        backend:
          serviceName: k8s-tutorial-api-service
          servicePort: 80
```

The `kubernetes.io/ingress-class` annotation says explicitly that we'll be using the nginx controller.  We're using plain HTTP, so we don't want to redirect traffic to HTTPS or use HTTP strict transport security (HTST). Hence, we've disabled `nginx.ingress.kubernetes.io/ssl-redirect` and `ingress.kubernetes.io/hsts`.  (Note that the nginx controller [requires annotation values to be strings](https://github.com/kubernetes/ingress-nginx/blob/master/docs/user-guide/nginx-configuration/annotations.md), that's why `false` is quoted.)  As far as rule specifications, we're simply sending all traffic to our API backend on port 80, per our service definition.  Update the chart's dependencies so that `nginx-ingress` is pulled in.

```
helm dep update ./k8s
```

And finally, we upgrade our release.  This will prompt Tiller to install the new dependency.

```
helm upgrade k8s-tutorial-api ./k8s
```

You'll now see a few new services for the nginx-controller (`kubectl get services`).  One is the ingress controller itself, and the other is a [default backend](https://kubernetes.github.io/ingress-nginx/user-guide/default-backend/).  The latter is used to service requests if no backend service can be reached, or if a request to an unknown path is requested.

All said and done, if you connect to the IP of your cluster (`minikube ip`) on port 80, you should get a response from the API.  If you're following along with the code, then your code should be comparable to my version 1.2.0: [https://github.com/benbotto/k8s-tutorial-api/tree/1.2.0](https://github.com/benbotto/k8s-tutorial-api/tree/1.2.0).

#### Add a Database

We'll conclude by adding a MySQL dependency to our application.  Using vanilla k8s it would involve making a [stateful set](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) to define a new pod, a new [service definition](https://kubernetes.io/docs/concepts/services-networking/service/#defining-a-service) to allow communication with the database, a [persistent volume](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#persistent-volumes) to manage non-volatile storage, and a [persistent volume claim](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#persistentvolumeclaims) so that the new pod can use the volume.  But golly, that's an awful lot of work.  Here's where Helm can help us.

There's a [Helm chart for MySQL](https://github.com/helm/charts/tree/master/stable/mysql) that does the heavy lifting for us.  We can declare MySQL as a dependency of our `k8s-tutorial-api` chart, then customize it to our liking.  Let's update [`k8s/requirements.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.3.0/k8s/requirements.yaml).

```
dependencies:
- name: nginx-ingress
  version: 1.1.3
  repository: https://kubernetes-charts.storage.googleapis.com
- name: mysql
  version: 0.12.0
  repository: https://kubernetes-charts.storage.googleapis.com
```

And, like before, we update our chart's dependencies.

```
helm dep update ./k8s
```

Now we need to customize our [configuration](https://github.com/helm/charts/tree/master/stable/mysql#configuration).  We'll want to provide our database name, username, and password.  The last part is sensitive--we wouldn't want to push our password to a public repository, after all.  K8s provides [secrets](https://kubernetes.io/docs/concepts/configuration/secret/) for just this sort of thing.  Secrets can be created in various ways, but we'll create ours using files.

```
echo -n "QC71yg2JGPNpuzoM" > mysql-password
echo -n "nf4Wt4RA3o0dgaHV" > mysql-root-password
kubectl create secret generic k8s-tutorial-db-pass --from-file=./mysql-root-password --from-file=./mysql-password
rm mysql-password mysql-root-password
```

The above commands assume you're using some sort of \*nix environment.  If not, you can create the two files using a text editor, but bear in mind that some editors automatically add newlines at the end of files, and that will cause problems with the secret.  I also used `echo` to create the files for convenience, which means that the commands will be present in history.  If you're on a shared system that might not be acceptable.  Also, the files are removed after storing the secret so that they're not inadvertently committed along side the code.  Outside of the k8s context, where to keep your passwords and how to share them with other developers is up to you.  LastPass or the likes might be a good choice.  Anyway, the files must be named `mysql-password` and `mysql-root-password`, as shown in the [MySQL chart's notes](https://github.com/helm/charts/blob/master/stable/mysql/templates/NOTES.txt).

Now we need to specify values for the MySQL subchart.  Overriding subchart values is discussed in depth [in the Helm docs](https://docs.helm.sh/chart_template_guide/#subcharts-and-global-values).  We'll customize the database, user, and passwords, plus we'll add some initialization scripts to create a table and fill in some data.  Generally a migration tool would be used for that last part, but for our needs this will suffice.  Here's the latest and greatest [`k8s/values.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.3.0/k8s/values.yaml) file.

```
# API section.
replicaCount: 1
image:
  tag: latest
# MySQL section.
mysql:
  mysqlDatabase: k8s_tutorial
  mysqlUser: k8s-tutorial-user
  existingSecret: k8s-tutorial-db-pass
  initializationFiles:
    1-create-table-users.sql: |-
      CREATE TABLE users (
        userID INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        firstName VARCHAR(255),
        lastName VARCHAR(255),
        createdOn TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP);
    2-add-dummy-users.sql: |-
      INSERT INTO users (firstName, lastName) VALUES ('Joe', 'Shmo');
      INSERT INTO users (firstName, lastName) VALUES ('Rand', 'AlThore');
      INSERT INTO users (firstName, lastName) VALUES ('Holly', 'Davis');
      INSERT INTO users (firstName, lastName) VALUES ('Jenny', 'Mather');
```

Sweet!  Time to upgrade.

```
helm upgrade k8s-tutorial-api ./k8s
```

And now `kubectl get pods` will show a new pod for our database.

```
NAME                                                              READY   STATUS    RESTARTS   AGE
k8s-tutorial-api-deployment-56c669ff75-5ghhj                      1/1     Running   1          3m7s
k8s-tutorial-api-deployment-56c669ff75-k4j6f                      1/1     Running   1          3m7s
k8s-tutorial-api-deployment-56c669ff75-nb4kh                      1/1     Running   1          3m7s
k8s-tutorial-api-mysql-5f6bccc754-zwb5k                           1/1     Running   0          3m7s
k8s-tutorial-api-nginx-ingress-controller-845877d6b6-x6psn        1/1     Running   0          3m7s
k8s-tutorial-api-nginx-ingress-default-backend-86998f4669-lk9r9   1/1     Running   0          3m7s
```

If you want, you can get a bash shell running in the MySQL container and take a look around.  Just `exec` bash against `k8s-tutorial-api-mysql` pod which, by default, executes a command against the first container in the pod.  (Your pod name will be slightly different than mine.)

```
kubectl exec -it k8s-tutorial-api-mysql-5f6bccc754-zwb5k -- bash
```

Within the container, our configured values will be set as environmental variables (`env |grep MYSQL`).  You can connect to the database like this.

```
mysql -u${MYSQL_USER} -p${MYSQL_PASSWORD} ${MYSQL_DATABASE}
```

#### Connecting the API to the Database

Now that the database is up and running, we'll connect our API to the database and use it.  Let's add a [MySQL driver](https://github.com/sidorares/node-mysql2) to our JavaScript code.

```
yarn add mysql2
```

And we'll update our [`app.js`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.3.0/app.js) file with a new `users` route that, when hit, returns all the users in the system.

```javascript
async function main() {
  const mysql    = require('mysql2/promise');
  const express  = require('express');
  const app      = express();
  const port     = 3000;
  const connOpts = {
    host     : process.env.DB_HOST,
    user     : process.env.DB_USER,
    password : process.env.DB_PASSWORD,
    database : process.env.DB_DATABASE
  };

  const conn = await mysql.createConnection(connOpts);

  // Close the connection on ctrl+c.
  process.on('SIGINT', close);

  // Hello, world route.
  app.get('/', (req, res) => res.json({hello: 'world'}));

  // Get all users route.
  app.get('/users', getAllUsers);

  app.listen(port);
  console.log(`Listening on port ${port}.`);

  async function close() {
    await conn.end();
    process.exit(0);
  }

  async function getAllUsers(req, res) {
    const [users] = await conn.query(`
      SELECT  u.userID, u.firstName, u.lastName
      FROM    users u`);

    res.json(users);
  }
}

main();
```

We've added code to open and close the database connection, and a new `GET /users` route.  Note that the MySQL host, user, database, and password all come from environment variables.  Our [`k8s/templates/deployment.yaml`](https://raw.githubusercontent.com/benbotto/k8s-tutorial-api/1.3.0/k8s/templates/deployment.yaml) file needs to be updated to provide these variables to our `k8s-tutorial-api` container.

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: k8s-tutorial-api-deployment
  labels:
    app.kubernetes.io/name: k8s-tutorial-api
    app.kubernetes.io/instance: {{ .Release.Name }}
    app.kubernetes.io/version: {{ .Values.image.tag }}
    app.kubernetes.io/component: api
    app.kubernetes.io/part-of: k8s-tutorial
    app.kubernetes.io/managed-by: helm
spec:
  replicas: {{ .Values.replicaCount }}
  selector:
    matchLabels:
      app.kubernetes.io/name: k8s-tutorial-api
      app.kubernetes.io/instance: {{ .Release.Name }}
  template:
    metadata:
      labels:
        app.kubernetes.io/name: k8s-tutorial-api
        app.kubernetes.io/instance: {{ .Release.Name }}
    spec:
      containers:
      - name: k8s-tutorial-api
        image: avejidah/k8s-tutorial-api:{{ .Values.image.tag }}
        ports:
        - containerPort: 3000
          name: http
        readinessProbe:
          httpGet:
            path: /
            port: 3000
          initialDelaySeconds: 1
          periodSeconds: 1
        livenessProbe:
          httpGet:
            path: /
            port: 3000
          initialDelaySeconds: 1
          periodSeconds: 5
        env:
        - name: DB_HOST
          value: {{ .Release.Name }}-mysql
        - name: DB_USER
          value: k8s-tutorial-user
        - name: DB_PASSWORD
          valueFrom:
            secretKeyRef:
              name: k8s-tutorial-db-pass
              key: mysql-password
        - name: DB_DATABASE
          value: k8s_tutorial
```

The four environment variables have been added.  From our API, the database's host name will be based on the relase name.  Since we've named the release `k8s-tutorial-api`, the database's host name will be `k8s-tutorial-api-mysql`.  Also, we've reused the `k8s-tutorial-db-pass` secret to share the password with the API containers.

If you're still following along, your code should be the same as [my version 1.3.0 tag](https://github.com/benbotto/k8s-tutorial-api/tree/1.3.0).  Build, tag, and push your new image, then upgrade.


```
helm upgrade k8s-tutorial-api ./k8s --set replicaCount=3,image.tag=1.3.0
```

If everything goes smoothly, you should be able to hit the new `/users` route and get back an array of users.

#### Cleaning Up

That concludes the tutorial.  Hopefully it helps you to get started with deployment orchestration.  If you want to clean everything up, you can delete and purge the release.

```
helm delete --purge k8s-tutorial-api
```

Or, if you want to completely wipe out Minikube.

```
minikube stop
minikube delete
rm -rf ~/.minikube
kubectl config unset clusters.minikube
kubectl config unset users.minikube
kubectl config unset contexts.minikube
```

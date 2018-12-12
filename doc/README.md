
Work in progress.

[Tutorials](tutorial/getting-started.md) [Tutorials](./tutorial/getting-started.md)

### Development Notes

##### Development Environment

Two docker containers are used during development:

1.  `formn-dev`: An Ubuntu Bionic container with Node.js Dubnium, with the code (this directory) mounted on `/home/node/dev/`. This container has all the dependencies required to run the unit tests, build the application, and generate documentation.
2.  `formn-db`: A Percona 5.7 container with a `formn_test_db` database. This container isn't strictly necessary for development, but while coding it's often useful to test against an actual database. The tables mimic the entity definitions in `src/test/entity/`. The database data and schema are defined in `docker-entrypoint-initdb.d/`.

To bring up the development environment, use Docker Compose: `docker-compose up -d`. The two containers can be seen by running `docker ps -a`. Bring up a bash shell in the dev environment with `docker-compose exec dev bash`. From bash, install the required dependencies using yarn:

```
cd dev
yarn
```

##### Tasks

Tasks such as building, testing, and generating documentation are defined in package.json as npm scripts.

*   `npm run build`: Build the application to ES6. The build will be in `dist`.
*   `npm run doc`: Generate documentation for the project. The documentation is created with TypeDoc and is located in the `doc` folder.
*   `npm run test`: Run the unit tests. Unit tests are written for Jasmine.
*   `npm run test:debug`: Run the unit tests and break immediately. From Chrome, navigate to `chrome://inspect` to debug the application. (Using a `debugger` statement somewhere in the code is helpful.)
*   `npm run clean`: Remove the `dist` and `doc` folders.
*   `npm run watch:test`: Run the unit tests any time a ts file changes. Watching is done via chokidar-cli.
*   `npm run watch:doc`: Generate documentation any time a ts file changes.

##### Unit Tests

Tests are written for Jasmine. Each test suite lives alongside its counterpart file (for example, `src/datamapper/schema.ts` is accompanied by `src/datamapper/schema.spec.ts`). There are also some helper scripts in `src/test/` that are used to aid in the testing process.

*   `test/query/`: One-off queries that were used to generate database results for testing against actual datasets.
*   `test/entity/*.entity.ts`: Table definitions used when testing. These definitions match the `formn_test_db` database.
*   `test/entity/database.ts`: Exports an `initDB()` function. With formn, entities are defined using decorators, and these decorators create metadata about tables and columns. Unit tests sometimes change these metadata definitions to test different scenarios. `initDB()` manually decorates entity classes to prevent state from carrying over from one test to the next. It's generally called from a test's `beforeEach` setup.

## Index

### Classes

* [ColumnLookup](classes/columnlookup.md)
* [ColumnMetaOptions](classes/columnmetaoptions.md)
* [ColumnMetadata](classes/columnmetadata.md)
* [ColumnStore](classes/columnstore.md)
* [ConditionCompiler](classes/conditioncompiler.md)
* [ConditionError](classes/conditionerror.md)
* [ConditionLexer](classes/conditionlexer.md)
* [ConditionParser](classes/conditionparser.md)
* [ConnectionManager](classes/connectionmanager.md)
* [ConnectionOptions](classes/connectionoptions.md)
* [Converter](classes/converter.md)
* [DataContext](classes/datacontext.md)
* [DataMapper](classes/datamapper.md)
* [Delete](classes/delete.md)
* [DeleteModel](classes/deletemodel.md)
* [Escaper](classes/escaper.md)
* [ExecutableQuery](classes/executablequery.md)
* [From](classes/from.md)
* [FromAdapter](classes/fromadapter.md)
* [FromColumnMeta](classes/fromcolumnmeta.md)
* [FromMeta](classes/frommeta.md)
* [FromTableMeta](classes/fromtablemeta.md)
* [Insert](classes/insert.md)
* [LexerToken](classes/lexertoken.md)
* [MSSQLEscaper](classes/mssqlescaper.md)
* [MutateModel](classes/mutatemodel.md)
* [MySQLConnectionManager](classes/mysqlconnectionmanager.md)
* [MySQLDataContext](classes/mysqldatacontext.md)
* [MySQLEscaper](classes/mysqlescaper.md)
* [MySQLExecuter](classes/mysqlexecuter.md)
* [MySQLFromAdapter](classes/mysqlfromadapter.md)
* [MySQLUpdate](classes/mysqlupdate.md)
* [MySQLUpdateModel](classes/mysqlupdatemodel.md)
* [ParameterList](classes/parameterlist.md)
* [ParseTree](classes/parsetree.md)
* [PropertyMapStore](classes/propertymapstore.md)
* [Query](classes/query.md)
* [RelationshipMetaOptions](classes/relationshipmetaoptions.md)
* [RelationshipMetadata](classes/relationshipmetadata.md)
* [RelationshipStore](classes/relationshipstore.md)
* [Schema](classes/schema.md)
* [SchemaColumn](classes/schemacolumn.md)
* [Select](classes/select.md)
* [SubSchema](classes/subschema.md)
* [TableMetaOptions](classes/tablemetaoptions.md)
* [TableMetadata](classes/tablemetadata.md)
* [TableStore](classes/tablestore.md)
* [Update](classes/update.md)
* [UpdateModel](classes/updatemodel.md)

### Interfaces

* [Executer](interfaces/executer.md)

### Type aliases

* [CardinalityType](#cardinalitytype)
* [ConnectionStateType](#connectionstatetype)
* [EntityType](#entitytype)
* [InsertResultType](#insertresulttype)
* [JoinType](#jointype)
* [MutateResultType](#mutateresulttype)
* [OrderByType](#orderbytype)
* [OrderDirectionType](#orderdirectiontype)
* [ParameterType](#parametertype)
* [PropertyMapType](#propertymaptype)
* [SelectResultType](#selectresulttype)
* [TableType](#tabletype)
* [UpdateType](#updatetype)

### Functions

* [Column](#column)
* [ManyToOne](#manytoone)
* [OneToMany](#onetomany)
* [OneToOne](#onetoone)
* [Relationship](#relationship)
* [Table](#table)
* [assert](#assert)

---

## Type aliases

<a id="cardinalitytype"></a>

###  CardinalityType

**Ƭ CardinalityType**: * "OneToOne" &#124; "OneToMany" &#124; "ManyToOne"
*

*Defined in [metadata/relationship/cardinality-type.ts:4](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/cardinality-type.ts#L4)*

Describes how two [Table](#table)\-decorated entities are related.

___
<a id="connectionstatetype"></a>

###  ConnectionStateType

**Ƭ ConnectionStateType**: * "DISCONNECTED" &#124; "CONNECTING" &#124; "CONNECTED"
*

*Defined in [connection/connection-state-type.ts:4](https://github.com/benbotto/formn/blob/f28037b/src/connection/connection-state-type.ts#L4)*

The state of a [ConnectionManager](classes/connectionmanager.md)'s connection.

___
<a id="entitytype"></a>

###  EntityType

**Ƭ EntityType**: *`object`*

*Defined in [metadata/table/entity-type.ts:4](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/entity-type.ts#L4)*

Type definition for Entity ([Table](#table)\-decorated class with type safety).

#### Type declaration

___
<a id="insertresulttype"></a>

###  InsertResultType

**Ƭ InsertResultType**: *`object`*

*Defined in [query/executer/insert-result-type.ts:4](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/insert-result-type.ts#L4)*

Result type for inserts, which generally has at least an insertId.

#### Type declaration

___
<a id="jointype"></a>

###  JoinType

**Ƭ JoinType**: * "INNER JOIN" &#124; "LEFT OUTER JOIN"
*

*Defined in [query/from/join-type.ts:4](https://github.com/benbotto/formn/blob/f28037b/src/query/from/join-type.ts#L4)*

Describes how two tables join to each other.

___
<a id="mutateresulttype"></a>

###  MutateResultType

**Ƭ MutateResultType**: *`object`*

*Defined in [query/executer/mutate-result-type.ts:5](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/mutate-result-type.ts#L5)*

Result type for update and delete queries, which has at least the number of affected rows.

#### Type declaration

___
<a id="orderbytype"></a>

###  OrderByType

**Ƭ OrderByType**: *`object`*

*Defined in [query/select/order-by-type.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/query/select/order-by-type.ts#L6)*

Object describing how to order a select query.

#### Type declaration

___
<a id="orderdirectiontype"></a>

###  OrderDirectionType

**Ƭ OrderDirectionType**: * "ASC" &#124; "DESC"
*

*Defined in [query/select/order-direction-type.ts:4](https://github.com/benbotto/formn/blob/f28037b/src/query/select/order-direction-type.ts#L4)*

Order direction, ascending or descinding.

___
<a id="parametertype"></a>

###  ParameterType

**Ƭ ParameterType**: *`object`*

*Defined in [query/condition/parameter-type.ts:5](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-type.ts#L5)*

Simple key-value pairs that are intended to replace parameters in a query condition.

#### Type declaration

[key: `string`]: `any`

___
<a id="propertymaptype"></a>

###  PropertyMapType

**Ƭ PropertyMapType**: *`object`*

*Defined in [metadata/property/property-map-type.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/metadata/property/property-map-type.ts#L6)*

See [ColumnStore](classes/columnstore.md). This is an object that has all the properties of a [Table](#table)\-decorated class. Each property maps to the name of the property on the class. E.g. {id: 'id', name: 'name'}.

#### Type declaration

[key: `string`]: `string`

___
<a id="selectresulttype"></a>

###  SelectResultType

**Ƭ SelectResultType**: *`object`[]*

*Defined in [query/executer/select-result-type.ts:5](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/select-result-type.ts#L5)*

Result type for select queries, which is an array of key-value pairs. Each key corresponds to a column in the select.

___
<a id="tabletype"></a>

###  TableType

**Ƭ TableType**: *`object`*

*Defined in [metadata/table/table-type.ts:4](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-type.ts#L4)*

Type definition for the type (constructor) of a [Table](#table)\-decorated class.

#### Type declaration

___
<a id="updatetype"></a>

###  UpdateType

**Ƭ UpdateType**: *`object`*

*Defined in [query/update/update-type.ts:5](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-type.ts#L5)*

Key-value pairs used for updating. Each key should be a fully-qualified property.

#### Type declaration

[key: `string`]: `any`

___

## Functions

<a id="column"></a>

###  Column

▸ **Column**(options?: *[ColumnMetaOptions](classes/columnmetaoptions.md)*): `(Anonymous function)`

*Defined in [metadata/column/column.decorator.ts:13](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column.decorator.ts#L13)*

Decorator that is applied to a [Table](#table)\-decorated class's properties. This associates the property with a database column and registers it in the [ColumnStore](classes/columnstore.md).

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` options | [ColumnMetaOptions](classes/columnmetaoptions.md) |  new ColumnMetaOptions() |

**Returns:** `(Anonymous function)`

___
<a id="manytoone"></a>

###  ManyToOne

▸ **ManyToOne**<`ENT_T`,`REF_ENT_T`>(to: *`function`*, on: *`function`*): `(Anonymous function)`

*Defined in [metadata/relationship/many-to-one.decorator.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/many-to-one.decorator.ts#L6)*

Wrapper for [Relationship](#relationship) with a hard-coded cardinality.

**Type parameters:**

#### ENT_T 
#### REF_ENT_T 
**Parameters:**

| Name | Type |
| ------ | ------ |
| to | `function` |
| on | `function` |

**Returns:** `(Anonymous function)`

___
<a id="onetomany"></a>

###  OneToMany

▸ **OneToMany**<`ENT_T`,`REF_ENT_T`>(to: *`function`*, on: *`function`*): `(Anonymous function)`

*Defined in [metadata/relationship/one-to-many.decorator.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/one-to-many.decorator.ts#L6)*

Wrapper for [Relationship](#relationship) with a hard-coded cardinality.

**Type parameters:**

#### ENT_T 
#### REF_ENT_T 
**Parameters:**

| Name | Type |
| ------ | ------ |
| to | `function` |
| on | `function` |

**Returns:** `(Anonymous function)`

___
<a id="onetoone"></a>

###  OneToOne

▸ **OneToOne**<`ENT_T`,`REF_ENT_T`>(to: *`function`*, on: *`function`*): `(Anonymous function)`

*Defined in [metadata/relationship/one-to-one.decorator.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/one-to-one.decorator.ts#L6)*

Wrapper for [Relationship](#relationship) with a hard-coded cardinality.

**Type parameters:**

#### ENT_T 
#### REF_ENT_T 
**Parameters:**

| Name | Type |
| ------ | ------ |
| to | `function` |
| on | `function` |

**Returns:** `(Anonymous function)`

___
<a id="relationship"></a>

###  Relationship

▸ **Relationship**<`ENT_T`,`REF_ENT_T`>(options: *[RelationshipMetaOptions](classes/relationshipmetaoptions.md)<`ENT_T`, `REF_ENT_T`>*): `(Anonymous function)`

*Defined in [metadata/relationship/relationship.decorator.ts:9](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship.decorator.ts#L9)*

Decorator for relationships between two [Table](#table)\-decorated classes. See [RelationshipMetaOptions](classes/relationshipmetaoptions.md) for the parameters.

**Type parameters:**

#### ENT_T 
#### REF_ENT_T 
**Parameters:**

| Name | Type |
| ------ | ------ |
| options | [RelationshipMetaOptions](classes/relationshipmetaoptions.md)<`ENT_T`, `REF_ENT_T`> |

**Returns:** `(Anonymous function)`

___
<a id="table"></a>

###  Table

▸ **Table**(options?: *[TableMetaOptions](classes/tablemetaoptions.md)*): `(Anonymous function)`

*Defined in [metadata/table/table.decorator.ts:12](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table.decorator.ts#L12)*

Decorator that is applied to a class to make it ORM capable. That is, it registers the class with formn so that it can be mapped to and from a database table. The decorator registers the class's [TableMetadata](classes/tablemetadata.md) in the [TableStore](classes/tablestore.md).

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` options | [TableMetaOptions](classes/tablemetaoptions.md) |  new TableMetaOptions() |

**Returns:** `(Anonymous function)`

___
<a id="assert"></a>

###  assert

▸ **assert**(condition: *`any`*, message: *`string`*): `void`

*Defined in [error/assert.ts:7](https://github.com/benbotto/formn/blob/f28037b/src/error/assert.ts#L7)*

Function that throws an Error(message) if condition is falsy.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| condition | `any` |  The condition, which is checked if falsy (!condition). |
| message | `string` |  The message wich is thrown in an Error if \* condition is falsy. |

**Returns:** `void`

___


[formn](../README.md) > [MySQLExecuter](../classes/mysqlexecuter.md)

# Class: MySQLExecuter

An Executer for executing MySQL queries.

## Hierarchy

**MySQLExecuter**

## Implements

* [Executer](../interfaces/executer.md)

## Index

### Constructors

* [constructor](mysqlexecuter.md#constructor)

### Properties

* [pool](mysqlexecuter.md#pool)

### Methods

* [delete](mysqlexecuter.md#delete)
* [insert](mysqlexecuter.md#insert)
* [select](mysqlexecuter.md#select)
* [update](mysqlexecuter.md#update)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MySQLExecuter**(pool: * `Connection` &#124; `Pool`*): [MySQLExecuter](mysqlexecuter.md)

*Defined in [query/executer/mysql-executer.ts:12](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/mysql-executer.ts#L12)*

Initialize the Executer instance.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| pool |  `Connection` &#124; `Pool`|  A MySQL connection instance (pool or single connection) |

**Returns:** [MySQLExecuter](mysqlexecuter.md)

___

## Properties

<a id="pool"></a>

###  pool

**● pool**: * `Connection` &#124; `Pool`
*

*Defined in [query/executer/mysql-executer.ts:18](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/mysql-executer.ts#L18)*

A MySQL connection instance (pool or single connection)

___

## Methods

<a id="delete"></a>

###  delete

▸ **delete**(query: *`string`*, params: *[ParameterType](../#parametertype)*): `Promise`<[MutateResultType](../#mutateresulttype)>

*Implementation of [Executer](../interfaces/executer.md).[delete](../interfaces/executer.md#delete)*

*Defined in [query/executer/mysql-executer.ts:72](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/mysql-executer.ts#L72)*

Execute a delete query.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| query | `string` |  The SQL to execute. |
| params | [ParameterType](../#parametertype) |  An object containing query parameters for the query. Each parameter will be preceded with a colon in query. |

**Returns:** `Promise`<[MutateResultType](../#mutateresulttype)>
An object that has an affectedRows property indicating the number
of rows affected (changed) by the query.

___
<a id="insert"></a>

###  insert

▸ **insert**(query: *`string`*, params: *[ParameterType](../#parametertype)*): `Promise`<[InsertResultType](../#insertresulttype)>

*Implementation of [Executer](../interfaces/executer.md).[insert](../interfaces/executer.md#insert)*

*Defined in [query/executer/mysql-executer.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/mysql-executer.ts#L44)*

Execute an insert query.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| query | `string` |  The SQL to execute. |
| params | [ParameterType](../#parametertype) |  An object containing query parameters for the query. Each parameter will be preceded with a colon in query. |

**Returns:** `Promise`<[InsertResultType](../#insertresulttype)>
A promise that will be resolved with an object describing the
result of the insert.  An insertId should be present on the object if
available (e.g. if the insert inolved a generated column).

___
<a id="select"></a>

###  select

▸ **select**(query: *`string`*, params: *[ParameterType](../#parametertype)*): `Promise`<[SelectResultType](../#selectresulttype)>

*Implementation of [Executer](../interfaces/executer.md).[select](../interfaces/executer.md#select)*

*Defined in [query/executer/mysql-executer.ts:29](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/mysql-executer.ts#L29)*

Execute a select query.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| query | `string` |  The SQL to execute. |
| params | [ParameterType](../#parametertype) |  An object containing query parameters for the query. Each parameter will be preceded with a colon in query. |

**Returns:** `Promise`<[SelectResultType](../#selectresulttype)>
A promise that is resolved with an array of query rows.  Each row
should have key-value pairs, where the keys are the selected columns.

___
<a id="update"></a>

###  update

▸ **update**(query: *`string`*, params: *[ParameterType](../#parametertype)*): `Promise`<[MutateResultType](../#mutateresulttype)>

*Implementation of [Executer](../interfaces/executer.md).[update](../interfaces/executer.md#update)*

*Defined in [query/executer/mysql-executer.ts:58](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/mysql-executer.ts#L58)*

Execute an update query.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| query | `string` |  The SQL to execute. |
| params | [ParameterType](../#parametertype) |  An object containing query parameters for the query. Each parameter will be preceded with a colon in query. |

**Returns:** `Promise`<[MutateResultType](../#mutateresulttype)>
An object that has an affectedRows property indicating the number
of rows affected (changed) by the query.

___


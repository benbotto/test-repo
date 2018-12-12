[formn](../README.md) > [Executer](../interfaces/executer.md)

# Interface: Executer

An Executer executes database queries.

## Hierarchy

**Executer**

## Implemented by

* [MySQLExecuter](../classes/mysqlexecuter.md)

## Index

### Methods

* [delete](executer.md#delete)
* [insert](executer.md#insert)
* [select](executer.md#select)
* [update](executer.md#update)

---

## Methods

<a id="delete"></a>

###  delete

▸ **delete**(query: *`string`*, params: *[ParameterType](../#parametertype)*): `Promise`<[MutateResultType](../#mutateresulttype)>

*Defined in [query/executer/executer.ts:49](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/executer.ts#L49)*

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

*Defined in [query/executer/executer.ts:29](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/executer.ts#L29)*

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

*Defined in [query/executer/executer.ts:18](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/executer.ts#L18)*

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

*Defined in [query/executer/executer.ts:39](https://github.com/benbotto/formn/blob/f28037b/src/query/executer/executer.ts#L39)*

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


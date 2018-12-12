[formn](../README.md) > [Delete](../classes/delete.md)

# Class: Delete

A [Query](query.md) class that represents a DELETE query.

## Hierarchy

 [Query](query.md)

**↳ Delete**

## Index

### Constructors

* [constructor](delete.md#constructor)

### Properties

* [alias](delete.md#alias)
* [colStore](delete.md#colstore)
* [escaper](delete.md#escaper)
* [executer](delete.md#executer)
* [from](delete.md#from)
* [propStore](delete.md#propstore)
* [relStore](delete.md#relstore)
* [tblStore](delete.md#tblstore)

### Methods

* [buildQuery](delete.md#buildquery)
* [execute](delete.md#execute)
* [toString](delete.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new Delete**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, from: *[From](from.md)*, alias?: *`string`*): [Delete](delete.md)

*Overrides [Query](query.md).[constructor](query.md#constructor)*

*Defined in [query/delete/delete.ts:19](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L19)*

Initialize the [Query](query.md) using a [From](from.md) instance.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [Escaper](escaper.md) |  An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions. |
| executer | [Executer](../interfaces/executer.md) |  An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)). |
| from | [From](from.md) |  A [From](from.md) instance which holds the base table, all joined-in tables, and the where clause. |
| `Optional` alias | `string` |  Alias of the table to delete from. Optional and defaults to the base table. |

**Returns:** [Delete](delete.md)

___

## Properties

<a id="alias"></a>

### `<Protected>``<Optional>` alias

**● alias**: *`string`*

*Defined in [query/delete/delete.ts:45](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L45)*

Alias of the table to delete from. Optional and defaults to the base table.

___
<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [Query](query.md).[colStore](query.md#colstore)*

*Defined in [query/delete/delete.ts:38](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L38)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [Query](query.md).[escaper](query.md#escaper)*

*Defined in [query/delete/delete.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L42)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Overrides [Query](query.md).[executer](query.md#executer)*

*Defined in [query/delete/delete.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L43)*

An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="from"></a>

### `<Protected>` from

**● from**: *[From](from.md)*

*Defined in [query/delete/delete.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L44)*

A [From](from.md) instance which holds the base table, all joined-in tables, and the where clause.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [Query](query.md).[propStore](query.md#propstore)*

*Defined in [query/delete/delete.ts:41](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L41)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [Query](query.md).[relStore](query.md#relstore)*

*Defined in [query/delete/delete.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L40)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [Query](query.md).[tblStore](query.md#tblstore)*

*Defined in [query/delete/delete.ts:39](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L39)*

Used for accessing tables in the database.

___

## Methods

<a id="buildquery"></a>

###  buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Overrides [Query](query.md).[buildQuery](query.md#buildquery)*

*Defined in [query/delete/delete.ts:71](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L71)*

Build the query.

**Returns:** [ExecutableQuery](executablequery.md)
The string-representation of the query to execute along with query
parameters.

___
<a id="execute"></a>

###  execute

▸ **execute**(): `Promise`<[MutateResultType](../#mutateresulttype)>

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/delete/delete.ts:84](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L84)*

Execute the query.

**Returns:** `Promise`<[MutateResultType](../#mutateresulttype)>
A promise that shall be resolved with an object containing an
"affectedRows" property.  If an error occurs when executing the query, the
returned promise shall be rejected with the error (unmodified).

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Overrides [Query](query.md).[toString](query.md#tostring)*

*Defined in [query/delete/delete.ts:58](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete.ts#L58)*

Get the SQL that represents the query.

**Returns:** `string`
The SQL representing the update statement.

___


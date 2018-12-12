[formn](../README.md) > [Query](../classes/query.md)

# Class: Query

Base class for Queries (Select, Insert, Delete, Update).

## Hierarchy

**Query**

↳  [Insert](insert.md)

↳  [Select](select.md)

↳  [Delete](delete.md)

↳  [Update](update.md)

↳  [MutateModel](mutatemodel.md)

## Index

### Constructors

* [constructor](query.md#constructor)

### Properties

* [colStore](query.md#colstore)
* [escaper](query.md#escaper)
* [executer](query.md#executer)
* [propStore](query.md#propstore)
* [relStore](query.md#relstore)
* [tblStore](query.md#tblstore)

### Methods

* [buildQuery](query.md#buildquery)
* [execute](query.md#execute)
* [toString](query.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new Query**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*): [Query](query.md)

*Defined in [query/query.ts:13](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L13)*

Initialize the query.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [Escaper](escaper.md) |  An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions. |
| executer | [Executer](../interfaces/executer.md) |  An Executer instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)). |

**Returns:** [Query](query.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Defined in [query/query.ts:28](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L28)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Defined in [query/query.ts:32](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L32)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Defined in [query/query.ts:33](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L33)*

An Executer instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Defined in [query/query.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L31)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Defined in [query/query.ts:30](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L30)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Defined in [query/query.ts:29](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L29)*

Used for accessing tables in the database.

___

## Methods

<a id="buildquery"></a>

### `<Abstract>` buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Defined in [query/query.ts:46](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L46)*

Build the query.

**Returns:** [ExecutableQuery](executablequery.md)
An ExecutableQuery instance with a query sting and parameters.

___
<a id="execute"></a>

### `<Abstract>` execute

▸ **execute**(exe: *[ExecutableQuery](executablequery.md)*): `Promise`<`any`>

*Defined in [query/query.ts:52](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L52)*

Execute the query and return the results.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| exe | [ExecutableQuery](executablequery.md) |  An ExecutableQuery instance with a query string and parameters. |

**Returns:** `Promise`<`any`>

___
<a id="tostring"></a>

### `<Abstract>` toString

▸ **toString**(): `string`

*Defined in [query/query.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L40)*

Convert the query to a string.

**Returns:** `string`
The SQL string.

___


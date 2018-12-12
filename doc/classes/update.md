[formn](../README.md) > [Update](../classes/update.md)

# Class: Update

A [Query](query.md) that represents an UPDATE.

## Hierarchy

 [Query](query.md)

**↳ Update**

↳  [MySQLUpdate](mysqlupdate.md)

## Index

### Constructors

* [constructor](update.md#constructor)

### Properties

* [colStore](update.md#colstore)
* [escaper](update.md#escaper)
* [executer](update.md#executer)
* [from](update.md#from)
* [model](update.md#model)
* [paramList](update.md#paramlist)
* [paramLookup](update.md#paramlookup)
* [propStore](update.md#propstore)
* [relStore](update.md#relstore)
* [tblStore](update.md#tblstore)
* [updateCols](update.md#updatecols)

### Methods

* [buildQuery](update.md#buildquery)
* [execute](update.md#execute)
* [toString](update.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new Update**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, from: *[From](from.md)*, model: *[UpdateType](../#updatetype)*): [Update](update.md)

*Overrides [Query](query.md).[constructor](query.md#constructor)*

*Defined in [query/update/update.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L31)*

Initialize the query using a From instance.

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
| model | [UpdateType](../#updatetype) |  An object containing key-value pairs. Each key must correspond to a fully-qualified property (&lt;table-alias&gt;.&lt;property&gt;), and each associated value is the value to update in the database. |

**Returns:** [Update](update.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [Query](query.md).[colStore](query.md#colstore)*

*Defined in [query/update/update.ts:53](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L53)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [Query](query.md).[escaper](query.md#escaper)*

*Defined in [query/update/update.ts:57](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L57)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Overrides [Query](query.md).[executer](query.md#executer)*

*Defined in [query/update/update.ts:58](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L58)*

An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="from"></a>

### `<Protected>` from

**● from**: *[From](from.md)*

*Defined in [query/update/update.ts:59](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L59)*

A [From](from.md) instance which holds the base table, all joined-in tables, and the where clause.

___
<a id="model"></a>

### `<Protected>` model

**● model**: *[UpdateType](../#updatetype)*

*Defined in [query/update/update.ts:60](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L60)*

An object containing key-value pairs. Each key must correspond to a fully-qualified property (<table-alias>.<property>), and each associated value is the value to update in the database.

___
<a id="paramlist"></a>

### `<Protected>` paramList

**● paramList**: *[ParameterList](parameterlist.md)*

*Defined in [query/update/update.ts:28](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L28)*

___
<a id="paramlookup"></a>

### `<Protected>` paramLookup

**● paramLookup**: *`Map`<`string`, `string`>*

*Defined in [query/update/update.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L31)*

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [Query](query.md).[propStore](query.md#propstore)*

*Defined in [query/update/update.ts:56](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L56)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [Query](query.md).[relStore](query.md#relstore)*

*Defined in [query/update/update.ts:55](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L55)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [Query](query.md).[tblStore](query.md#tblstore)*

*Defined in [query/update/update.ts:54](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L54)*

Used for accessing tables in the database.

___
<a id="updatecols"></a>

### `<Protected>` updateCols

**● updateCols**: *[FromColumnMeta](fromcolumnmeta.md)[]*

*Defined in [query/update/update.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L25)*

___

## Methods

<a id="buildquery"></a>

###  buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Overrides [Query](query.md).[buildQuery](query.md#buildquery)*

*Defined in [query/update/update.ts:120](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L120)*

Build the query.

**Returns:** [ExecutableQuery](executablequery.md)
The string-representation of the query to execute along with query
parameters.

___
<a id="execute"></a>

###  execute

▸ **execute**(): `Promise`<[MutateResultType](../#mutateresulttype)>

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/update/update.ts:133](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L133)*

Execute the query.

**Returns:** `Promise`<[MutateResultType](../#mutateresulttype)>
A promise that shall be resolved with an object containing an
"affectedRows" property.  If an error occurs when executing the query, the
returned promise shall be rejected with the error (unmodified).

___
<a id="tostring"></a>

### `<Abstract>` toString

▸ **toString**(): `string`

*Inherited from [Query](query.md).[toString](query.md#tostring)*

*Defined in [query/query.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L40)*

Convert the query to a string.

**Returns:** `string`
The SQL string.

___


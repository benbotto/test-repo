[formn](../README.md) > [MySQLUpdate](../classes/mysqlupdate.md)

# Class: MySQLUpdate

A [Query](query.md) that represents an UPDATE for a MySQL database.

## Hierarchy

↳  [Update](update.md)

**↳ MySQLUpdate**

## Index

### Constructors

* [constructor](mysqlupdate.md#constructor)

### Properties

* [colStore](mysqlupdate.md#colstore)
* [escaper](mysqlupdate.md#escaper)
* [executer](mysqlupdate.md#executer)
* [from](mysqlupdate.md#from)
* [model](mysqlupdate.md#model)
* [paramList](mysqlupdate.md#paramlist)
* [paramLookup](mysqlupdate.md#paramlookup)
* [propStore](mysqlupdate.md#propstore)
* [relStore](mysqlupdate.md#relstore)
* [tblStore](mysqlupdate.md#tblstore)
* [updateCols](mysqlupdate.md#updatecols)

### Methods

* [buildQuery](mysqlupdate.md#buildquery)
* [execute](mysqlupdate.md#execute)
* [toString](mysqlupdate.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MySQLUpdate**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[MySQLEscaper](mysqlescaper.md)*, executer: *[MySQLExecuter](mysqlexecuter.md)*, from: *[From](from.md)*, model: *[UpdateType](../#updatetype)*): [MySQLUpdate](mysqlupdate.md)

*Overrides [Update](update.md).[constructor](update.md#constructor)*

*Defined in [query/update/mysql-update.ts:22](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L22)*

Initialize the query using a From instance.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [MySQLEscaper](mysqlescaper.md) |  An [Escaper](escaper.md) for MySQL. Used when escaping column names. |
| executer | [MySQLExecuter](mysqlexecuter.md) |  An [Executer](../interfaces/executer.md) instance for MySQL. |
| from | [From](from.md) |  A [From](from.md) instance which holds the base table, all joined-in tables, and the where clause. |
| model | [UpdateType](../#updatetype) |  An object containing key-value pairs. Each key must correspond to a fully-qualified property (&lt;table-alias&gt;.&lt;property&gt;), and each associated value is the value to update in the database. |

**Returns:** [MySQLUpdate](mysqlupdate.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [Update](update.md).[colStore](update.md#colstore)*

*Defined in [query/update/mysql-update.ts:41](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L41)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[MySQLEscaper](mysqlescaper.md)*

*Overrides [Update](update.md).[escaper](update.md#escaper)*

*Defined in [query/update/mysql-update.ts:45](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L45)*

An [Escaper](escaper.md) for MySQL. Used when escaping column names.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[MySQLExecuter](mysqlexecuter.md)*

*Overrides [Update](update.md).[executer](update.md#executer)*

*Defined in [query/update/mysql-update.ts:46](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L46)*

An [Executer](../interfaces/executer.md) instance for MySQL.

___
<a id="from"></a>

### `<Protected>` from

**● from**: *[From](from.md)*

*Overrides [Update](update.md).[from](update.md#from)*

*Defined in [query/update/mysql-update.ts:47](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L47)*

A [From](from.md) instance which holds the base table, all joined-in tables, and the where clause.

___
<a id="model"></a>

### `<Protected>` model

**● model**: *[UpdateType](../#updatetype)*

*Overrides [Update](update.md).[model](update.md#model)*

*Defined in [query/update/mysql-update.ts:48](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L48)*

An object containing key-value pairs. Each key must correspond to a fully-qualified property (<table-alias>.<property>), and each associated value is the value to update in the database.

___
<a id="paramlist"></a>

### `<Protected>` paramList

**● paramList**: *[ParameterList](parameterlist.md)*

*Inherited from [Update](update.md).[paramList](update.md#paramlist)*

*Defined in [query/update/update.ts:28](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L28)*

___
<a id="paramlookup"></a>

### `<Protected>` paramLookup

**● paramLookup**: *`Map`<`string`, `string`>*

*Inherited from [Update](update.md).[paramLookup](update.md#paramlookup)*

*Defined in [query/update/update.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L31)*

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [Update](update.md).[propStore](update.md#propstore)*

*Defined in [query/update/mysql-update.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L44)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [Update](update.md).[relStore](update.md#relstore)*

*Defined in [query/update/mysql-update.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L43)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [Update](update.md).[tblStore](update.md#tblstore)*

*Defined in [query/update/mysql-update.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L42)*

Used for accessing tables in the database.

___
<a id="updatecols"></a>

### `<Protected>` updateCols

**● updateCols**: *[FromColumnMeta](fromcolumnmeta.md)[]*

*Inherited from [Update](update.md).[updateCols](update.md#updatecols)*

*Defined in [query/update/update.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L25)*

___

## Methods

<a id="buildquery"></a>

###  buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Inherited from [Update](update.md).[buildQuery](update.md#buildquery)*

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

*Inherited from [Update](update.md).[execute](update.md#execute)*

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/update/update.ts:133](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update.ts#L133)*

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

*Defined in [query/update/mysql-update.ts:57](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update.ts#L57)*

Get the SQL that represents the query.

**Returns:** `string`
The SQL representing the update statement.

___


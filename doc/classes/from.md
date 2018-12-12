[formn](../README.md) > [From](../classes/from.md)

# Class: From

Represents the FROM portion of a query, with any JOINs and optionally a WHERE condition. This class is used when selecting, updating, or deleting.

## Hierarchy

**From**

↳  [FromAdapter](fromadapter.md)

## Index

### Constructors

* [constructor](from.md#constructor)

### Properties

* [colStore](from.md#colstore)
* [escaper](from.md#escaper)
* [propStore](from.md#propstore)
* [relStore](from.md#relstore)
* [tblStore](from.md#tblstore)

### Methods

* [getBaseTableMeta](from.md#getbasetablemeta)
* [getFromMeta](from.md#getfrommeta)
* [getFromString](from.md#getfromstring)
* [getJoinMeta](from.md#getjoinmeta)
* [getJoinString](from.md#getjoinstring)
* [getParameterList](from.md#getparameterlist)
* [getWhereString](from.md#getwherestring)
* [innerJoin](from.md#innerjoin)
* [join](from.md#join)
* [leftOuterJoin](from.md#leftouterjoin)
* [toString](from.md#tostring)
* [where](from.md#where)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new From**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, FromEntity: *[TableType](../#tabletype)*, fromAlias?: *`string`*): [From](from.md)

*Defined in [query/from/from.ts:24](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L24)*

Initialize.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [Escaper](escaper.md) |  An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions. |
| FromEntity | [TableType](../#tabletype) |  Constructor of the FROM table. |
| `Optional` fromAlias | `string` |  Alias for the FROM table, used in conditions, joins, and column selection. Optional: defaults to the name of the table. |

**Returns:** [From](from.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Defined in [query/from/from.ts:41](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L41)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Defined in [query/from/from.ts:45](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L45)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Defined in [query/from/from.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L44)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Defined in [query/from/from.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L43)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Defined in [query/from/from.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L42)*

Used for accessing tables in the database.

___

## Methods

<a id="getbasetablemeta"></a>

###  getBaseTableMeta

▸ **getBaseTableMeta**(): [FromTableMeta](fromtablemeta.md)

*Defined in [query/from/from.ts:64](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L64)*

Helper method to get the meta data of the FROM table, which is the first table in [FromMeta](frommeta.md).

**Returns:** [FromTableMeta](fromtablemeta.md)
A meta object describing the table.

___
<a id="getfrommeta"></a>

###  getFromMeta

▸ **getFromMeta**(): [FromMeta](frommeta.md)

*Defined in [query/from/from.ts:254](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L254)*

Get the metadata (tables, columns, and parameters).

**Returns:** [FromMeta](frommeta.md)

___
<a id="getfromstring"></a>

###  getFromString

▸ **getFromString**(): `string`

*Defined in [query/from/from.ts:188](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L188)*

Get the FROM portion of the query as a string.

**Returns:** `string`
The FROM portion of the query (FROM &lt;table&gt; AS
&lt;alias&gt;), escaped.

___
<a id="getjoinmeta"></a>

###  getJoinMeta

▸ **getJoinMeta**(): [FromTableMeta](fromtablemeta.md)[]

*Defined in [query/from/from.ts:73](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L73)*

Helper method to get the meta data of the JOIN'd in tables.

**Returns:** [FromTableMeta](fromtablemeta.md)[]
An array of meta objects describing each table.  The meta objects
are in insertion order (e.g. in the order the tables were joined in).

___
<a id="getjoinstring"></a>

###  getJoinString

▸ **getJoinString**(): `string`

*Defined in [query/from/from.ts:200](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L200)*

Get the JOIN parts of the query string.

**Returns:** `string`
The JOIN parts of the query, escaped.

___
<a id="getparameterlist"></a>

###  getParameterList

▸ **getParameterList**(): [ParameterList](parameterlist.md)

*Defined in [query/from/from.ts:247](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L247)*

Get the list of parameters for the From.

**Returns:** [ParameterList](parameterlist.md)

___
<a id="getwherestring"></a>

###  getWhereString

▸ **getWhereString**(): `string`

*Defined in [query/from/from.ts:222](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L222)*

Get the WHERE portion of the query string.

**Returns:** `string`
The WHERE part of the query, or a blank string if there is no
where clause.

___
<a id="innerjoin"></a>

###  innerJoin

▸ **innerJoin**<`J`>(Entity: *[TableType](../#tabletype)*, alias: *`string`*, fqParentProperty: *`string`*, joinCond?: *`object`*, joinParams?: *[ParameterType](../#parametertype)*): `this`

*Defined in [query/from/from.ts:136](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L136)*

Inner join in a table. See [From.join](from.md#join).

**Type parameters:**

#### J 
**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |
| alias | `string` |
| fqParentProperty | `string` |
| `Optional` joinCond | `object` |
| `Optional` joinParams | [ParameterType](../#parametertype) |

**Returns:** `this`

___
<a id="join"></a>

###  join

▸ **join**<`J`>(joinType: *[JoinType](../#jointype)*, Entity: *[TableType](../#tabletype)*, alias: *`string`*, fqParentProperty: *`string`*, joinCond?: *`object`*, joinParams?: *[ParameterType](../#parametertype)*): `this`

*Defined in [query/from/from.ts:90](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L90)*

Join in a table.

**Type parameters:**

#### J 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| joinType | [JoinType](../#jointype) |  How to join the two tables (INNER JOIN, LEFT OUTER JOIN). |
| Entity | [TableType](../#tabletype) |  The [Table](../#table)\-decorated Entity to join in. |
| alias | `string` |  Alias of the joined-in table. |
| fqParentProperty | `string` |  The fully-qualified property name on the parent Entity to which this Entity will be mapped. |
| `Optional` joinCond | `object` |  An optional condition that describes how to join the two tables. If not supplied then the join condition will be derived. |
| `Optional` joinParams | [ParameterType](../#parametertype) |  An optional set of parameters that will be used to replace values in joinCond. |

**Returns:** `this`

___
<a id="leftouterjoin"></a>

###  leftOuterJoin

▸ **leftOuterJoin**<`J`>(Entity: *[TableType](../#tabletype)*, alias: *`string`*, fqParentProperty: *`string`*, joinCond?: *`object`*, joinParams?: *[ParameterType](../#parametertype)*): `this`

*Defined in [query/from/from.ts:150](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L150)*

Left outer join in a table. See [From.join](from.md#join).

**Type parameters:**

#### J 
**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |
| alias | `string` |
| fqParentProperty | `string` |
| `Optional` joinCond | `object` |
| `Optional` joinParams | [ParameterType](../#parametertype) |

**Returns:** `this`

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Defined in [query/from/from.ts:232](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L232)*

Get the SQL that represents the query.

**Returns:** `string`
The actual SQL query (FROM, JOINS, and WHERE).

___
<a id="where"></a>

###  where

▸ **where**(cond: *`object`*, params: *[ParameterType](../#parametertype)*): `this`

*Defined in [query/from/from.ts:167](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L167)*

Add a WHERE condition to the query. This method can only be called one time (if called a second time an exception is raised).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| cond | `object` |  The where condition object. |
| params | [ParameterType](../#parametertype) |  Any parameter replacements in the condition object. |

**Returns:** `this`

___


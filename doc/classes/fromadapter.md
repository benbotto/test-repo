[formn](../README.md) > [FromAdapter](../classes/fromadapter.md)

# Class: FromAdapter

Adapter for the [From](from.md) class that exposes a nice user interface for [Select](select.md), [Delete](delete.md), and [Update](update.md), all of which depend on a [From](from.md) instance.

## Type parameters
#### T 
## Hierarchy

 [From](from.md)

**↳ FromAdapter**

↳  [MySQLFromAdapter](mysqlfromadapter.md)

## Index

### Constructors

* [constructor](fromadapter.md#constructor)

### Properties

* [colStore](fromadapter.md#colstore)
* [escaper](fromadapter.md#escaper)
* [executer](fromadapter.md#executer)
* [propStore](fromadapter.md#propstore)
* [relStore](fromadapter.md#relstore)
* [tblStore](fromadapter.md#tblstore)

### Methods

* [delete](fromadapter.md#delete)
* [getBaseTableMeta](fromadapter.md#getbasetablemeta)
* [getFromMeta](fromadapter.md#getfrommeta)
* [getFromString](fromadapter.md#getfromstring)
* [getJoinMeta](fromadapter.md#getjoinmeta)
* [getJoinString](fromadapter.md#getjoinstring)
* [getParameterList](fromadapter.md#getparameterlist)
* [getWhereString](fromadapter.md#getwherestring)
* [innerJoin](fromadapter.md#innerjoin)
* [join](fromadapter.md#join)
* [leftOuterJoin](fromadapter.md#leftouterjoin)
* [select](fromadapter.md#select)
* [toString](fromadapter.md#tostring)
* [update](fromadapter.md#update)
* [where](fromadapter.md#where)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new FromAdapter**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, FromEntity: *[EntityType](../#entitytype)<`T`>*, fromAlias?: *`string`*): [FromAdapter](fromadapter.md)

*Overrides [From](from.md).[constructor](from.md#constructor)*

*Defined in [query/from/from-adapter.ts:22](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L22)*

Initialize the From instance.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [Escaper](escaper.md) |  An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions. |
| executer | [Executer](../interfaces/executer.md) |  An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)). |
| FromEntity | [EntityType](../#entitytype)<`T`> |  Constructor of the FROM table. |
| `Optional` fromAlias | `string` |  Alias for the FROM table, used in conditions, joins, and column selection. Optional: defaults to the name of the table. |

**Returns:** [FromAdapter](fromadapter.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [From](from.md).[colStore](from.md#colstore)*

*Defined in [query/from/from-adapter.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L40)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [From](from.md).[escaper](from.md#escaper)*

*Defined in [query/from/from-adapter.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L44)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Defined in [query/from/from-adapter.ts:45](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L45)*

An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [From](from.md).[propStore](from.md#propstore)*

*Defined in [query/from/from-adapter.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L43)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [From](from.md).[relStore](from.md#relstore)*

*Defined in [query/from/from-adapter.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L42)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [From](from.md).[tblStore](from.md#tblstore)*

*Defined in [query/from/from-adapter.ts:41](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L41)*

Used for accessing tables in the database.

___

## Methods

<a id="delete"></a>

###  delete

▸ **delete**(alias?: *`string`*): [Delete](delete.md)

*Defined in [query/from/from-adapter.ts:70](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L70)*

Delete from a table. See [Delete](delete.md).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| `Optional` alias | `string` |  The unique alias of the table from which records will be deleted. Optional, defaults to the alias of the from table. |

**Returns:** [Delete](delete.md)
A Delete instance that can be executed.

___
<a id="getbasetablemeta"></a>

###  getBaseTableMeta

▸ **getBaseTableMeta**(): [FromTableMeta](fromtablemeta.md)

*Inherited from [From](from.md).[getBaseTableMeta](from.md#getbasetablemeta)*

*Defined in [query/from/from.ts:64](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L64)*

Helper method to get the meta data of the FROM table, which is the first table in [FromMeta](frommeta.md).

**Returns:** [FromTableMeta](fromtablemeta.md)
A meta object describing the table.

___
<a id="getfrommeta"></a>

###  getFromMeta

▸ **getFromMeta**(): [FromMeta](frommeta.md)

*Inherited from [From](from.md).[getFromMeta](from.md#getfrommeta)*

*Defined in [query/from/from.ts:254](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L254)*

Get the metadata (tables, columns, and parameters).

**Returns:** [FromMeta](frommeta.md)

___
<a id="getfromstring"></a>

###  getFromString

▸ **getFromString**(): `string`

*Inherited from [From](from.md).[getFromString](from.md#getfromstring)*

*Defined in [query/from/from.ts:188](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L188)*

Get the FROM portion of the query as a string.

**Returns:** `string`
The FROM portion of the query (FROM &lt;table&gt; AS
&lt;alias&gt;), escaped.

___
<a id="getjoinmeta"></a>

###  getJoinMeta

▸ **getJoinMeta**(): [FromTableMeta](fromtablemeta.md)[]

*Inherited from [From](from.md).[getJoinMeta](from.md#getjoinmeta)*

*Defined in [query/from/from.ts:73](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L73)*

Helper method to get the meta data of the JOIN'd in tables.

**Returns:** [FromTableMeta](fromtablemeta.md)[]
An array of meta objects describing each table.  The meta objects
are in insertion order (e.g. in the order the tables were joined in).

___
<a id="getjoinstring"></a>

###  getJoinString

▸ **getJoinString**(): `string`

*Inherited from [From](from.md).[getJoinString](from.md#getjoinstring)*

*Defined in [query/from/from.ts:200](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L200)*

Get the JOIN parts of the query string.

**Returns:** `string`
The JOIN parts of the query, escaped.

___
<a id="getparameterlist"></a>

###  getParameterList

▸ **getParameterList**(): [ParameterList](parameterlist.md)

*Inherited from [From](from.md).[getParameterList](from.md#getparameterlist)*

*Defined in [query/from/from.ts:247](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L247)*

Get the list of parameters for the From.

**Returns:** [ParameterList](parameterlist.md)

___
<a id="getwherestring"></a>

###  getWhereString

▸ **getWhereString**(): `string`

*Inherited from [From](from.md).[getWhereString](from.md#getwherestring)*

*Defined in [query/from/from.ts:222](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L222)*

Get the WHERE portion of the query string.

**Returns:** `string`
The WHERE part of the query, or a blank string if there is no
where clause.

___
<a id="innerjoin"></a>

###  innerJoin

▸ **innerJoin**<`J`>(Entity: *[TableType](../#tabletype)*, alias: *`string`*, fqParentProperty: *`string`*, joinCond?: *`object`*, joinParams?: *[ParameterType](../#parametertype)*): `this`

*Inherited from [From](from.md).[innerJoin](from.md#innerjoin)*

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

*Inherited from [From](from.md).[join](from.md#join)*

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

*Inherited from [From](from.md).[leftOuterJoin](from.md#leftouterjoin)*

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
<a id="select"></a>

###  select

▸ **select**(...cols: *`string`[]*): [Select](select.md)<`T`>

*Defined in [query/from/from-adapter.ts:57](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L57)*

Select from the table. See [Select.select](select.md#select-1).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| `Rest` cols | `string`[] |  An optional set of columns to select. |

**Returns:** [Select](select.md)<`T`>
An executable [[Select]] instance.

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Inherited from [From](from.md).[toString](from.md#tostring)*

*Defined in [query/from/from.ts:232](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L232)*

Get the SQL that represents the query.

**Returns:** `string`
The actual SQL query (FROM, JOINS, and WHERE).

___
<a id="update"></a>

### `<Abstract>` update

▸ **update**(model: *[UpdateType](../#updatetype)*): [Update](update.md)

*Defined in [query/from/from-adapter.ts:81](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-adapter.ts#L81)*

Update a table. See [Update](update.md).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| model | [UpdateType](../#updatetype) |  The model describing what to update. |

**Returns:** [Update](update.md)
An [[Update]] instance matching the database type (e.g.
[[MySQLUpdate]]).

___
<a id="where"></a>

###  where

▸ **where**(cond: *`object`*, params: *[ParameterType](../#parametertype)*): `this`

*Inherited from [From](from.md).[where](from.md#where)*

*Defined in [query/from/from.ts:167](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from.ts#L167)*

Add a WHERE condition to the query. This method can only be called one time (if called a second time an exception is raised).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| cond | `object` |  The where condition object. |
| params | [ParameterType](../#parametertype) |  Any parameter replacements in the condition object. |

**Returns:** `this`

___


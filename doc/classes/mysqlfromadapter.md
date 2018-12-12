[formn](../README.md) > [MySQLFromAdapter](../classes/mysqlfromadapter.md)

# Class: MySQLFromAdapter

A specialized [FromAdapter](fromadapter.md) for MySQL databases. See [FromAdapter](fromadapter.md).

## Type parameters
#### T 
## Hierarchy

↳  [FromAdapter](fromadapter.md)<`T`>

**↳ MySQLFromAdapter**

## Index

### Constructors

* [constructor](mysqlfromadapter.md#constructor)

### Properties

* [colStore](mysqlfromadapter.md#colstore)
* [escaper](mysqlfromadapter.md#escaper)
* [executer](mysqlfromadapter.md#executer)
* [propStore](mysqlfromadapter.md#propstore)
* [relStore](mysqlfromadapter.md#relstore)
* [tblStore](mysqlfromadapter.md#tblstore)

### Methods

* [delete](mysqlfromadapter.md#delete)
* [getBaseTableMeta](mysqlfromadapter.md#getbasetablemeta)
* [getFromMeta](mysqlfromadapter.md#getfrommeta)
* [getFromString](mysqlfromadapter.md#getfromstring)
* [getJoinMeta](mysqlfromadapter.md#getjoinmeta)
* [getJoinString](mysqlfromadapter.md#getjoinstring)
* [getParameterList](mysqlfromadapter.md#getparameterlist)
* [getWhereString](mysqlfromadapter.md#getwherestring)
* [innerJoin](mysqlfromadapter.md#innerjoin)
* [join](mysqlfromadapter.md#join)
* [leftOuterJoin](mysqlfromadapter.md#leftouterjoin)
* [select](mysqlfromadapter.md#select)
* [toString](mysqlfromadapter.md#tostring)
* [update](mysqlfromadapter.md#update)
* [where](mysqlfromadapter.md#where)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MySQLFromAdapter**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[MySQLEscaper](mysqlescaper.md)*, executer: *[MySQLExecuter](mysqlexecuter.md)*, FromEntity: *[EntityType](../#entitytype)<`T`>*, fromAlias?: *`string`*): [MySQLFromAdapter](mysqlfromadapter.md)

*Overrides [FromAdapter](fromadapter.md).[constructor](fromadapter.md#constructor)*

*Defined in [query/from/mysql-from-adapter.ts:17](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L17)*

Initialize the From instance.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [MySQLEscaper](mysqlescaper.md) |  An [Escaper](escaper.md) for MySQL. Used when escaping column names. |
| executer | [MySQLExecuter](mysqlexecuter.md) |  An [Executer](../interfaces/executer.md) instance for MySQL. |
| FromEntity | [EntityType](../#entitytype)<`T`> |  Constructor of the FROM table. |
| `Optional` fromAlias | `string` |  Alias for the FROM table, used in conditions, joins, and column selection. Optional: defaults to the name of the table. |

**Returns:** [MySQLFromAdapter](mysqlfromadapter.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [FromAdapter](fromadapter.md).[colStore](fromadapter.md#colstore)*

*Defined in [query/from/mysql-from-adapter.ts:33](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L33)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[MySQLEscaper](mysqlescaper.md)*

*Overrides [FromAdapter](fromadapter.md).[escaper](fromadapter.md#escaper)*

*Defined in [query/from/mysql-from-adapter.ts:37](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L37)*

An [Escaper](escaper.md) for MySQL. Used when escaping column names.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[MySQLExecuter](mysqlexecuter.md)*

*Overrides [FromAdapter](fromadapter.md).[executer](fromadapter.md#executer)*

*Defined in [query/from/mysql-from-adapter.ts:38](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L38)*

An [Executer](../interfaces/executer.md) instance for MySQL.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [FromAdapter](fromadapter.md).[propStore](fromadapter.md#propstore)*

*Defined in [query/from/mysql-from-adapter.ts:36](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L36)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [FromAdapter](fromadapter.md).[relStore](fromadapter.md#relstore)*

*Defined in [query/from/mysql-from-adapter.ts:35](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L35)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [FromAdapter](fromadapter.md).[tblStore](fromadapter.md#tblstore)*

*Defined in [query/from/mysql-from-adapter.ts:34](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L34)*

Used for accessing tables in the database.

___

## Methods

<a id="delete"></a>

###  delete

▸ **delete**(alias?: *`string`*): [Delete](delete.md)

*Inherited from [FromAdapter](fromadapter.md).[delete](fromadapter.md#delete)*

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

*Inherited from [FromAdapter](fromadapter.md).[select](fromadapter.md#select)*

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

###  update

▸ **update**(model: *[UpdateType](../#updatetype)*): [MySQLUpdate](mysqlupdate.md)

*Overrides [FromAdapter](fromadapter.md).[update](fromadapter.md#update)*

*Defined in [query/from/mysql-from-adapter.ts:50](https://github.com/benbotto/formn/blob/f28037b/src/query/from/mysql-from-adapter.ts#L50)*

Update a table. See [MySQLUpdate](mysqlupdate.md).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| model | [UpdateType](../#updatetype) |  The model describing what to update. |

**Returns:** [MySQLUpdate](mysqlupdate.md)
A [[MySQLUpdate]] instance that is executable.

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


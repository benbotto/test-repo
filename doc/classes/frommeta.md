[formn](../README.md) > [FromMeta](../classes/frommeta.md)

# Class: FromMeta

A helper class for keeping metadata about tables and columns used in a [From](from.md) instance.

## Hierarchy

**FromMeta**

## Index

### Constructors

* [constructor](frommeta.md#constructor)

### Properties

* [availableCols](frommeta.md#availablecols)
* [columnLookup](frommeta.md#columnlookup)
* [mapHierarchy](frommeta.md#maphierarchy)
* [paramList](frommeta.md#paramlist)
* [tableMetas](frommeta.md#tablemetas)

### Methods

* [addTable](frommeta.md#addtable)
* [compileCondition](frommeta.md#compilecondition)
* [getFromColumnMeta](frommeta.md#getfromcolumnmeta)
* [getFromColumnMetaByProp](frommeta.md#getfromcolumnmetabyprop)
* [getFromTableMeta](frommeta.md#getfromtablemeta)
* [getFromTableMetaByAlias](frommeta.md#getfromtablemetabyalias)
* [getTableMetadataByAlias](frommeta.md#gettablemetadatabyalias)
* [isColumnAvailable](frommeta.md#iscolumnavailable)
* [setCondition](frommeta.md#setcondition)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new FromMeta**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, escaper: *[Escaper](escaper.md)*): [FromMeta](frommeta.md)

*Defined in [query/from/from-meta.ts:63](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L63)*

Initialize.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for finding relationships between parent and child tables. |
| escaper | [Escaper](escaper.md) |  An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md). Used when escaping column names in compiled conditions. |

**Returns:** [FromMeta](frommeta.md)

___

## Properties

<a id="availablecols"></a>

###  availableCols

**● availableCols**: *`Map`<`string`, [FromColumnMeta](fromcolumnmeta.md)>* =  new Map()

*Defined in [query/from/from-meta.ts:39](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L39)*

A map from fully-qualified property name to [FromColumnMeta](fromcolumnmeta.md). These are the columns that are available for selecting, performing conditions on, or ordering by.

___
<a id="columnlookup"></a>

###  columnLookup

**● columnLookup**: *[ColumnLookup](columnlookup.md)* =  new ColumnLookup()

*Defined in [query/from/from-meta.ts:57](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L57)*

Lookup functionality between fully-qualified property names and fully-qualified column names. Users operate on [Column](../#column)\-decorated properties, but ultimately those properties need to be mapped to fully-qualified column names when querying.

___
<a id="maphierarchy"></a>

###  mapHierarchy

**● mapHierarchy**: *`Map`<`string`, `Set`<`string`>>* =  new Map()

*Defined in [query/from/from-meta.ts:49](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L49)*

Holds the mapping ([RelationshipMetadata.mapTo](relationshipmetadata.md#mapto)) hierarchy. The map uses the parent alias as the key and a Set of mapping names (mapTo) as the values. The same mapping can be used multiple times, but each mapping must be unique to a parent. For example, it's valid for a person to have a "photo" and a building to have a "photo," but there cannot be two "photo" properties at same level (e.g. under person).

___
<a id="paramlist"></a>

###  paramList

**● paramList**: *[ParameterList](parameterlist.md)* =  new ParameterList()

*Defined in [query/from/from-meta.ts:63](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L63)*

Stores all the parameters for the query. The parameters are used for WHERE and ON conditions.

___
<a id="tablemetas"></a>

###  tableMetas

**● tableMetas**: *`Map`<`string`, [FromTableMeta](fromtablemeta.md)>* =  new Map()

*Defined in [query/from/from-meta.ts:32](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L32)*

A map from table alias to [FromTableMeta](fromtablemeta.md) objects.

___

## Methods

<a id="addtable"></a>

###  addTable

▸ **addTable**(Entity: *[TableType](../#tabletype)*, alias: *`string`*, parentAlias?: *`string`*, property?: *`string`*, joinType?: *[JoinType](../#jointype)*, cond?: *`object`*, params?: *[ParameterType](../#parametertype)*): `this`

*Defined in [query/from/from-meta.ts:95](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L95)*

Add a table to the list and make all the columns in the table "available" for use in a select, condition, or order clause.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| Entity | [TableType](../#tabletype) | - |  Constructor of the [Table](../#table)\-decorated class. |
| alias | `string` | - |  Alias of the table. |
| `Default value` parentAlias | `string` |  null |  Alias of the parent table. |
| `Default value` property | `string` |  null |  Property in the parent Entity to which children (this Entity) will be mapped. |
| `Default value` joinType | [JoinType](../#jointype) |  null |  How this table was joined to from the parent. |
| `Default value` cond | `object` |  null |  A join condition object for the two tables, or a where condition object for the parent table. |
| `Default value` params | [ParameterType](../#parametertype) |  null |  Any parameters used in the condition. |

**Returns:** `this`

___
<a id="compilecondition"></a>

###  compileCondition

▸ **compileCondition**(cond: *`object`*): `string`

*Defined in [query/from/from-meta.ts:249](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L249)*

Helper method to compile a condition. The compilation process ensures that each parameter in the condition has a replacement in the parameter list, and that each fully-qualified property in the condition is available (that is, belongs to one of the tables used in the [From](from.md)). Also, a [ColumnLookup](columnlookup.md) is supplied so that fully-qualified property names can be mapped to the associated column names.

**Parameters:**

| Name | Type |
| ------ | ------ |
| cond | `object` |

**Returns:** `string`

___
<a id="getfromcolumnmeta"></a>

###  getFromColumnMeta

▸ **getFromColumnMeta**(): [FromColumnMeta](fromcolumnmeta.md)[]

*Defined in [query/from/from-meta.ts:211](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L211)*

Get the metadata for all available columns as an array.

**Returns:** [FromColumnMeta](fromcolumnmeta.md)[]

___
<a id="getfromcolumnmetabyprop"></a>

###  getFromColumnMetaByProp

▸ **getFromColumnMetaByProp**(fqProp: *`string`*): [FromColumnMeta](fromcolumnmeta.md)

*Defined in [query/from/from-meta.ts:201](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L201)*

Get the [FromColumnMeta](fromcolumnmeta.md) for a column by fully-qualified property.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| fqProp | `string` |  The fully-qualified property name to look for. |

**Returns:** [FromColumnMeta](fromcolumnmeta.md)

___
<a id="getfromtablemeta"></a>

###  getFromTableMeta

▸ **getFromTableMeta**(): [FromTableMeta](fromtablemeta.md)[]

*Defined in [query/from/from-meta.ts:237](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L237)*

Get all the [FromTableMeta](fromtablemeta.md) as an array.

**Returns:** [FromTableMeta](fromtablemeta.md)[]

___
<a id="getfromtablemetabyalias"></a>

###  getFromTableMetaByAlias

▸ **getFromTableMetaByAlias**(alias: *`string`*): [FromTableMeta](fromtablemeta.md)

*Defined in [query/from/from-meta.ts:219](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L219)*

Get the [FromTableMeta](fromtablemeta.md) for a table by alias or throw.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| alias | `string` |  Alias of the table. |

**Returns:** [FromTableMeta](fromtablemeta.md)

___
<a id="gettablemetadatabyalias"></a>

###  getTableMetadataByAlias

▸ **getTableMetadataByAlias**(alias: *`string`*): [TableMetadata](tablemetadata.md)

*Defined in [query/from/from-meta.ts:230](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L230)*

Get the [TableMetadata](tablemetadata.md) for a table by alias or throw.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| alias | `string` |  Alias of the table. |

**Returns:** [TableMetadata](tablemetadata.md)

___
<a id="iscolumnavailable"></a>

###  isColumnAvailable

▸ **isColumnAvailable**(fqProp: *`string`*): `boolean`

*Defined in [query/from/from-meta.ts:193](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L193)*

Check if the column is available (for selecting, for a condition, or for an order by clause).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| fqProp | `string` |  The fully-qualified property name to look for. |

**Returns:** `boolean`

___
<a id="setcondition"></a>

###  setCondition

▸ **setCondition**(alias: *`string`*, cond: *`object`*, params?: *[ParameterType](../#parametertype)*): `this`

*Defined in [query/from/from-meta.ts:174](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-meta.ts#L174)*

Set the condition object on one of the [FromTableMeta](fromtablemeta.md) objects and compile it.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| alias | `string` | - |  Alias of the table to which the condition will be added. |
| cond | `object` | - |  The condition object to add and compile. |
| `Default value` params | [ParameterType](../#parametertype) |  null |  Any parameters in the cond object. |

**Returns:** `this`

___


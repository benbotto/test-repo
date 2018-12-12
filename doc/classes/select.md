[formn](../README.md) > [Select](../classes/select.md)

# Class: Select

Represents a SELECT query.

## Type parameters
#### T 
## Hierarchy

 [Query](query.md)

**↳ Select**

## Index

### Constructors

* [constructor](select.md#constructor)

### Properties

* [colStore](select.md#colstore)
* [escaper](select.md#escaper)
* [executer](select.md#executer)
* [propStore](select.md#propstore)
* [relStore](select.md#relstore)
* [tblStore](select.md#tblstore)

### Methods

* [buildQuery](select.md#buildquery)
* [execute](select.md#execute)
* [orderBy](select.md#orderby)
* [select](select.md#select-1)
* [toString](select.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new Select**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, from: *[From](from.md)*): [Select](select.md)

*Overrides [Query](query.md).[constructor](query.md#constructor)*

*Defined in [query/select/select.ts:29](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L29)*

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

**Returns:** [Select](select.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [Query](query.md).[colStore](query.md#colstore)*

*Defined in [query/select/select.ts:47](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L47)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [Query](query.md).[escaper](query.md#escaper)*

*Defined in [query/select/select.ts:51](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L51)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Overrides [Query](query.md).[executer](query.md#executer)*

*Defined in [query/select/select.ts:52](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L52)*

An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [Query](query.md).[propStore](query.md#propstore)*

*Defined in [query/select/select.ts:50](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L50)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [Query](query.md).[relStore](query.md#relstore)*

*Defined in [query/select/select.ts:49](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L49)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [Query](query.md).[tblStore](query.md#tblstore)*

*Defined in [query/select/select.ts:48](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L48)*

Used for accessing tables in the database.

___

## Methods

<a id="buildquery"></a>

###  buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Overrides [Query](query.md).[buildQuery](query.md#buildquery)*

*Defined in [query/select/select.ts:278](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L278)*

Build the query.

**Returns:** [ExecutableQuery](executablequery.md)
The string-representation of the query to execute along with query
parameters.

___
<a id="execute"></a>

###  execute

▸ **execute**(): `Promise`<`T`[]>

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/select/select.ts:211](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L211)*

Execute the query and return an array of results of type T.

**Returns:** `Promise`<`T`[]>
A promise that shall be resolved with the normalized query results
of type T.  If an error occurs while executing the query, the returned
promise shall be rejected with the unmodified error.

___
<a id="orderby"></a>

###  orderBy

▸ **orderBy**(...orders: * [OrderByType](../#orderbytype)[] &#124; `string`[]*): `this`

*Defined in [query/select/select.ts:132](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L132)*

Order by one or more columns.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| `Rest` orders |  [OrderByType](../#orderbytype)[] &#124; `string`[]|  A list of fully-qualified properties in the form &lt;table-alias&gt;.&lt;property&gt;, or an array of [OrderByType](../#orderbytype) with the fully-qualified property and direction. |

**Returns:** `this`

___
<a id="select-1"></a>

###  select

▸ **select**(...cols: *`string`[]*): `this`

*Defined in [query/select/select.ts:65](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L65)*

Select columns manually.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| `Rest` cols | `string`[] |  An optional set of columns to select. Each argument should be a fully-qualified property name in the form &lt;table-alias&gt;.&lt;property&gt;. If no columns are specified, then all columns are selected. |

**Returns:** `this`

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Overrides [Query](query.md).[toString](query.md#tostring)*

*Defined in [query/select/select.ts:158](https://github.com/benbotto/formn/blob/f28037b/src/query/select/select.ts#L158)*

Get the SQL that represents the query.

**Returns:** `string`
The SQL representing the select statement.

___


[formn](../README.md) > [Insert](../classes/insert.md)

# Class: Insert

A [Query](query.md) class that represents an INSERT query. Instances of the class can be used to insert models in a database.

## Type parameters
#### T 
## Hierarchy

 [Query](query.md)

**↳ Insert**

## Index

### Constructors

* [constructor](insert.md#constructor)

### Properties

* [colStore](insert.md#colstore)
* [escaper](insert.md#escaper)
* [executer](insert.md#executer)
* [propStore](insert.md#propstore)
* [relStore](insert.md#relstore)
* [tblStore](insert.md#tblstore)

### Methods

* [buildQuery](insert.md#buildquery)
* [execute](insert.md#execute)
* [toString](insert.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new Insert**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [Insert](insert.md)

*Overrides [Query](query.md).[constructor](query.md#constructor)*

*Defined in [query/insert/insert.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L27)*

Initialize the Query.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [Escaper](escaper.md) |  An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions. |
| executer | [Executer](../interfaces/executer.md) |  An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)). |
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to insert, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to insert. |

**Returns:** [Insert](insert.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [Query](query.md).[colStore](query.md#colstore)*

*Defined in [query/insert/insert.ts:46](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L46)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [Query](query.md).[escaper](query.md#escaper)*

*Defined in [query/insert/insert.ts:50](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L50)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Overrides [Query](query.md).[executer](query.md#executer)*

*Defined in [query/insert/insert.ts:51](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L51)*

An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [Query](query.md).[propStore](query.md#propstore)*

*Defined in [query/insert/insert.ts:49](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L49)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [Query](query.md).[relStore](query.md#relstore)*

*Defined in [query/insert/insert.ts:48](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L48)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [Query](query.md).[tblStore](query.md#tblstore)*

*Defined in [query/insert/insert.ts:47](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L47)*

Used for accessing tables in the database.

___

## Methods

<a id="buildquery"></a>

###  buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Overrides [Query](query.md).[buildQuery](query.md#buildquery)*

*Defined in [query/insert/insert.ts:132](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L132)*

Build the query.

**Returns:** [ExecutableQuery](executablequery.md)
An [[ExecutableQuery]] with the query string and any parameters
usded in the query.

___
<a id="execute"></a>

###  execute

▸ **execute**(): `Promise`<`T`>

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/insert/insert.ts:146](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L146)*

Execute the query.

**Returns:** `Promise`<`T`>
A Promise that shall be resolved with the model.  If the
[[Executer.insert]] operation returns a generated insertId the model will
be updated with that ID.  If an error occurs during execution the promise
shall be rejected with the unmodified error.

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Overrides [Query](query.md).[toString](query.md#tostring)*

*Defined in [query/insert/insert.ts:100](https://github.com/benbotto/formn/blob/f28037b/src/query/insert/insert.ts#L100)*

Create the SQL string.

**Returns:** `string`
A SQL representation of the INSERT query as a string.

___


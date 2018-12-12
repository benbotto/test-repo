[formn](../README.md) > [MutateModel](../classes/mutatemodel.md)

# Class: MutateModel

A [Query](query.md) that represents a mutation (update or delete) on an entity by ID.

## Type parameters
#### Q :  [Query](query.md)
#### T 
## Hierarchy

 [Query](query.md)

**↳ MutateModel**

↳  [UpdateModel](updatemodel.md)

↳  [DeleteModel](deletemodel.md)

## Index

### Constructors

* [constructor](mutatemodel.md#constructor)

### Properties

* [Entity](mutatemodel.md#entity)
* [colStore](mutatemodel.md#colstore)
* [escaper](mutatemodel.md#escaper)
* [executer](mutatemodel.md#executer)
* [from](mutatemodel.md#from)
* [model](mutatemodel.md#model)
* [propStore](mutatemodel.md#propstore)
* [query](mutatemodel.md#query)
* [relStore](mutatemodel.md#relstore)
* [tblStore](mutatemodel.md#tblstore)

### Methods

* [buildQuery](mutatemodel.md#buildquery)
* [execute](mutatemodel.md#execute)
* [produceQuery](mutatemodel.md#producequery)
* [toString](mutatemodel.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MutateModel**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [MutateModel](mutatemodel.md)

*Overrides [Query](query.md).[constructor](query.md#constructor)*

*Defined in [query/mutate-model.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L31)*

Initialize the query using an Entity type and an Entity instance (a model).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [Escaper](escaper.md) |  An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions. |
| executer | [Executer](../interfaces/executer.md) |  An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)). |
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to mutate, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to mutate, which must have the primary key set. |

**Returns:** [MutateModel](mutatemodel.md)

___

## Properties

<a id="entity"></a>

### `<Protected>` Entity

**● Entity**: *[EntityType](../#entitytype)<`T`>*

*Defined in [query/mutate-model.ts:58](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L58)*

The type of model to mutate, which is the constructor of a [Table](../#table)\-decorated class.

___
<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [Query](query.md).[colStore](query.md#colstore)*

*Defined in [query/mutate-model.ts:52](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L52)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [Query](query.md).[escaper](query.md#escaper)*

*Defined in [query/mutate-model.ts:56](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L56)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Overrides [Query](query.md).[executer](query.md#executer)*

*Defined in [query/mutate-model.ts:57](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L57)*

An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="from"></a>

### `<Protected>` from

**● from**: *[From](from.md)*

*Defined in [query/mutate-model.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L25)*

A [From](from.md) instance that is used to create a [Query](query.md) of type Q.

___
<a id="model"></a>

### `<Protected>` model

**● model**: *`T`*

*Defined in [query/mutate-model.ts:59](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L59)*

An Entity instance to mutate, which must have the primary key set.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [Query](query.md).[propStore](query.md#propstore)*

*Defined in [query/mutate-model.ts:55](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L55)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="query"></a>

### `<Protected>` query

**● query**: *`Q`*

*Defined in [query/mutate-model.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L31)*

A [Query](query.md) instance (e.g. [Update](update.md) or [Delete](delete.md) that is used in toString, buildQuery, and execute.

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [Query](query.md).[relStore](query.md#relstore)*

*Defined in [query/mutate-model.ts:54](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L54)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [Query](query.md).[tblStore](query.md#tblstore)*

*Defined in [query/mutate-model.ts:53](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L53)*

Used for accessing tables in the database.

___

## Methods

<a id="buildquery"></a>

###  buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Overrides [Query](query.md).[buildQuery](query.md#buildquery)*

*Defined in [query/mutate-model.ts:120](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L120)*

Build the query.

**Returns:** [ExecutableQuery](executablequery.md)
The string-representation of the query to execute along with query
parameters.

___
<a id="execute"></a>

### `<Abstract>` execute

▸ **execute**(exe: *[ExecutableQuery](executablequery.md)*): `Promise`<`any`>

*Inherited from [Query](query.md).[execute](query.md#execute)*

*Defined in [query/query.ts:52](https://github.com/benbotto/formn/blob/f28037b/src/query/query.ts#L52)*

Execute the query and return the results.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| exe | [ExecutableQuery](executablequery.md) |  An ExecutableQuery instance with a query string and parameters. |

**Returns:** `Promise`<`any`>

___
<a id="producequery"></a>

### `<Protected>``<Abstract>` produceQuery

▸ **produceQuery**(from: *[From](from.md)*): `Q`

*Defined in [query/mutate-model.ts:105](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L105)*

Produce a [Query](query.md) instance that's appropriate for the database (e.g. a [MySQLUpdate](mysqlupdate.md)).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| from | [From](from.md) |  A [From](from.md) instance, passed to the [Query](query.md) constructor. |

**Returns:** `Q`

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Overrides [Query](query.md).[toString](query.md#tostring)*

*Defined in [query/mutate-model.ts:111](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L111)*

Get the SQL that represents the query.

**Returns:** `string`
The SQL representing the mutation.

___


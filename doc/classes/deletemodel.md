[formn](../README.md) > [DeleteModel](../classes/deletemodel.md)

# Class: DeleteModel

A class for deleting models by ID.

## Type parameters
#### T 
## Hierarchy

↳  [MutateModel](mutatemodel.md)<[Delete](delete.md), `T`>

**↳ DeleteModel**

## Index

### Constructors

* [constructor](deletemodel.md#constructor)

### Properties

* [Entity](deletemodel.md#entity)
* [colStore](deletemodel.md#colstore)
* [escaper](deletemodel.md#escaper)
* [executer](deletemodel.md#executer)
* [from](deletemodel.md#from)
* [model](deletemodel.md#model)
* [propStore](deletemodel.md#propstore)
* [query](deletemodel.md#query)
* [relStore](deletemodel.md#relstore)
* [tblStore](deletemodel.md#tblstore)

### Methods

* [buildQuery](deletemodel.md#buildquery)
* [execute](deletemodel.md#execute)
* [produceQuery](deletemodel.md#producequery)
* [toString](deletemodel.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new DeleteModel**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [DeleteModel](deletemodel.md)

*Overrides [MutateModel](mutatemodel.md).[constructor](mutatemodel.md#constructor)*

*Defined in [query/delete/delete-model.ts:17](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L17)*

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
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to delete, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to delete, which must have the primary key set. |

**Returns:** [DeleteModel](deletemodel.md)

___

## Properties

<a id="entity"></a>

### `<Protected>` Entity

**● Entity**: *[EntityType](../#entitytype)<`T`>*

*Overrides [MutateModel](mutatemodel.md).[Entity](mutatemodel.md#entity)*

*Defined in [query/delete/delete-model.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L43)*

The type of model to delete, which is the constructor of a [Table](../#table)\-decorated class.

___
<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [MutateModel](mutatemodel.md).[colStore](mutatemodel.md#colstore)*

*Defined in [query/delete/delete-model.ts:37](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L37)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [MutateModel](mutatemodel.md).[escaper](mutatemodel.md#escaper)*

*Defined in [query/delete/delete-model.ts:41](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L41)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Overrides [MutateModel](mutatemodel.md).[executer](mutatemodel.md#executer)*

*Defined in [query/delete/delete-model.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L42)*

An [Executer](../interfaces/executer.md) instance that matches the database type (e.g. [MySQLExecuter](mysqlexecuter.md)).

___
<a id="from"></a>

### `<Protected>` from

**● from**: *[From](from.md)*

*Inherited from [MutateModel](mutatemodel.md).[from](mutatemodel.md#from)*

*Defined in [query/mutate-model.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L25)*

A [From](from.md) instance that is used to create a [Query](query.md) of type Q.

___
<a id="model"></a>

### `<Protected>` model

**● model**: *`T`*

*Overrides [MutateModel](mutatemodel.md).[model](mutatemodel.md#model)*

*Defined in [query/delete/delete-model.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L44)*

An Entity instance to delete, which must have the primary key set.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [MutateModel](mutatemodel.md).[propStore](mutatemodel.md#propstore)*

*Defined in [query/delete/delete-model.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L40)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="query"></a>

### `<Protected>` query

**● query**: *[Delete](delete.md)*

*Inherited from [MutateModel](mutatemodel.md).[query](mutatemodel.md#query)*

*Defined in [query/mutate-model.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L31)*

A [Query](query.md) instance (e.g. [Update](update.md) or [Delete](delete.md) that is used in toString, buildQuery, and execute.

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [MutateModel](mutatemodel.md).[relStore](mutatemodel.md#relstore)*

*Defined in [query/delete/delete-model.ts:39](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L39)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [MutateModel](mutatemodel.md).[tblStore](mutatemodel.md#tblstore)*

*Defined in [query/delete/delete-model.ts:38](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L38)*

Used for accessing tables in the database.

___

## Methods

<a id="buildquery"></a>

###  buildQuery

▸ **buildQuery**(): [ExecutableQuery](executablequery.md)

*Inherited from [MutateModel](mutatemodel.md).[buildQuery](mutatemodel.md#buildquery)*

*Overrides [Query](query.md).[buildQuery](query.md#buildquery)*

*Defined in [query/mutate-model.ts:120](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L120)*

Build the query.

**Returns:** [ExecutableQuery](executablequery.md)
The string-representation of the query to execute along with query
parameters.

___
<a id="execute"></a>

###  execute

▸ **execute**(): `Promise`<`T`>

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/delete/delete-model.ts:62](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L62)*

Execute the query.

**Returns:** `Promise`<`T`>
A promise that shall be resolved with the deleted model.

___
<a id="producequery"></a>

### `<Protected>` produceQuery

▸ **produceQuery**(from: *[From](from.md)*): [Delete](delete.md)

*Overrides [MutateModel](mutatemodel.md).[produceQuery](mutatemodel.md#producequery)*

*Defined in [query/delete/delete-model.ts:53](https://github.com/benbotto/formn/blob/f28037b/src/query/delete/delete-model.ts#L53)*

Produce a [Delete](delete.md) instance.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| from | [From](from.md) |  A [From](from.md) instance, passed to the [Delete](delete.md) constructor. |

**Returns:** [Delete](delete.md)

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Inherited from [MutateModel](mutatemodel.md).[toString](mutatemodel.md#tostring)*

*Overrides [Query](query.md).[toString](query.md#tostring)*

*Defined in [query/mutate-model.ts:111](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L111)*

Get the SQL that represents the query.

**Returns:** `string`
The SQL representing the mutation.

___


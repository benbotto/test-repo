[formn](../README.md) > [UpdateModel](../classes/updatemodel.md)

# Class: UpdateModel

A [Query](query.md) that represents an UPDATE query and is used for updating an entity.

## Type parameters
#### T 
## Hierarchy

↳  [MutateModel](mutatemodel.md)<[Update](update.md), `T`>

**↳ UpdateModel**

↳  [MySQLUpdateModel](mysqlupdatemodel.md)

## Index

### Constructors

* [constructor](updatemodel.md#constructor)

### Properties

* [Entity](updatemodel.md#entity)
* [colStore](updatemodel.md#colstore)
* [escaper](updatemodel.md#escaper)
* [executer](updatemodel.md#executer)
* [from](updatemodel.md#from)
* [model](updatemodel.md#model)
* [propStore](updatemodel.md#propstore)
* [query](updatemodel.md#query)
* [relStore](updatemodel.md#relstore)
* [tblStore](updatemodel.md#tblstore)

### Methods

* [buildQuery](updatemodel.md#buildquery)
* [createUpdateModel](updatemodel.md#createupdatemodel)
* [execute](updatemodel.md#execute)
* [produceQuery](updatemodel.md#producequery)
* [toString](updatemodel.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new UpdateModel**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[Escaper](escaper.md)*, executer: *[Executer](../interfaces/executer.md)*, Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [UpdateModel](updatemodel.md)

*Overrides [MutateModel](mutatemodel.md).[constructor](mutatemodel.md#constructor)*

*Defined in [query/update/update-model.ts:21](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L21)*

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
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to update, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to update, which must have the primary key set. |

**Returns:** [UpdateModel](updatemodel.md)

___

## Properties

<a id="entity"></a>

### `<Protected>` Entity

**● Entity**: *[EntityType](../#entitytype)<`T`>*

*Overrides [MutateModel](mutatemodel.md).[Entity](mutatemodel.md#entity)*

*Defined in [query/update/update-model.ts:47](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L47)*

The type of model to update, which is the constructor of a [Table](../#table)\-decorated class.

___
<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [MutateModel](mutatemodel.md).[colStore](mutatemodel.md#colstore)*

*Defined in [query/update/update-model.ts:41](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L41)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[Escaper](escaper.md)*

*Overrides [MutateModel](mutatemodel.md).[escaper](mutatemodel.md#escaper)*

*Defined in [query/update/update-model.ts:45](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L45)*

An [Escaper](escaper.md) matching the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[Executer](../interfaces/executer.md)*

*Overrides [MutateModel](mutatemodel.md).[executer](mutatemodel.md#executer)*

*Defined in [query/update/update-model.ts:46](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L46)*

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

*Defined in [query/update/update-model.ts:48](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L48)*

An Entity instance to update, which must have the primary key set.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [MutateModel](mutatemodel.md).[propStore](mutatemodel.md#propstore)*

*Defined in [query/update/update-model.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L44)*

Used for pulling table property maps (used in conjunction with the relStore to get remote columns).

___
<a id="query"></a>

### `<Protected>` query

**● query**: *[Update](update.md)*

*Inherited from [MutateModel](mutatemodel.md).[query](mutatemodel.md#query)*

*Defined in [query/mutate-model.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/mutate-model.ts#L31)*

A [Query](query.md) instance (e.g. [Update](update.md) or [Delete](delete.md) that is used in toString, buildQuery, and execute.

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Overrides [MutateModel](mutatemodel.md).[relStore](mutatemodel.md#relstore)*

*Defined in [query/update/update-model.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L43)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [MutateModel](mutatemodel.md).[tblStore](mutatemodel.md#tblstore)*

*Defined in [query/update/update-model.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L42)*

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
<a id="createupdatemodel"></a>

### `<Protected>` createUpdateModel

▸ **createUpdateModel**(from: *[From](from.md)*): [UpdateType](../#updatetype)

*Defined in [query/update/update-model.ts:57](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L57)*

Create a model that is suitable for use with an [Update](update.md) query. This should be called from a child class's produceQuery method.

**Parameters:**

| Name | Type |
| ------ | ------ |
| from | [From](from.md) |

**Returns:** [UpdateType](../#updatetype)

___
<a id="execute"></a>

###  execute

▸ **execute**(): `Promise`<`T`>

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/update/update-model.ts:96](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L96)*

Execute the query.

**Returns:** `Promise`<`T`>
A promise that shall be resolved with the mutated model.

___
<a id="producequery"></a>

### `<Protected>``<Abstract>` produceQuery

▸ **produceQuery**(from: *[From](from.md)*): [Update](update.md)

*Overrides [MutateModel](mutatemodel.md).[produceQuery](mutatemodel.md#producequery)*

*Defined in [query/update/update-model.ts:90](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L90)*

Produce an [Update](update.md) instance that's appropriate for the database (e.g. a [MySQLUpdate](mysqlupdate.md)).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| from | [From](from.md) |  A [From](from.md) instance, passed to the [Update](update.md) constructor. |

**Returns:** [Update](update.md)

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


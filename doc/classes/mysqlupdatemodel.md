[formn](../README.md) > [MySQLUpdateModel](../classes/mysqlupdatemodel.md)

# Class: MySQLUpdateModel

An [UpdateModel](updatemodel.md) class for MySQL.

## Type parameters
#### T 
## Hierarchy

↳  [UpdateModel](updatemodel.md)<`T`>

**↳ MySQLUpdateModel**

## Index

### Constructors

* [constructor](mysqlupdatemodel.md#constructor)

### Properties

* [Entity](mysqlupdatemodel.md#entity)
* [colStore](mysqlupdatemodel.md#colstore)
* [escaper](mysqlupdatemodel.md#escaper)
* [executer](mysqlupdatemodel.md#executer)
* [from](mysqlupdatemodel.md#from)
* [model](mysqlupdatemodel.md#model)
* [propStore](mysqlupdatemodel.md#propstore)
* [query](mysqlupdatemodel.md#query)
* [relStore](mysqlupdatemodel.md#relstore)
* [tblStore](mysqlupdatemodel.md#tblstore)

### Methods

* [buildQuery](mysqlupdatemodel.md#buildquery)
* [createUpdateModel](mysqlupdatemodel.md#createupdatemodel)
* [execute](mysqlupdatemodel.md#execute)
* [produceQuery](mysqlupdatemodel.md#producequery)
* [toString](mysqlupdatemodel.md#tostring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MySQLUpdateModel**(colStore: *[ColumnStore](columnstore.md)*, tblStore: *[TableStore](tablestore.md)*, relStore: *[RelationshipStore](relationshipstore.md)*, propStore: *[PropertyMapStore](propertymapstore.md)*, escaper: *[MySQLEscaper](mysqlescaper.md)*, executer: *[MySQLExecuter](mysqlexecuter.md)*, Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [MySQLUpdateModel](mysqlupdatemodel.md)

*Overrides [UpdateModel](updatemodel.md).[constructor](updatemodel.md#constructor)*

*Defined in [query/update/mysql-update-model.ts:17](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L17)*

Initialize the query using an Entity type and an Entity instance (a model).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| colStore | [ColumnStore](columnstore.md) |  Used for accessing columns in tables. |
| tblStore | [TableStore](tablestore.md) |  Used for accessing tables in the database. |
| relStore | [RelationshipStore](relationshipstore.md) |  Used for accessing relationships between tables. |
| propStore | [PropertyMapStore](propertymapstore.md) |  Used for pulling table property maps (used in conjunction with the relStore to get remote columns). |
| escaper | [MySQLEscaper](mysqlescaper.md) |  A [MySQLEscaper](mysqlescaper.md) instance. Used when escaping column names in compiled conditions. |
| executer | [MySQLExecuter](mysqlexecuter.md) |  A [MySQLExecuter](mysqlexecuter.md) instance for executing queries. |
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to update, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to update, which must have the primary key set. |

**Returns:** [MySQLUpdateModel](mysqlupdatemodel.md)

___

## Properties

<a id="entity"></a>

### `<Protected>` Entity

**● Entity**: *[EntityType](../#entitytype)<`T`>*

*Overrides [UpdateModel](updatemodel.md).[Entity](updatemodel.md#entity)*

*Defined in [query/update/mysql-update-model.ts:41](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L41)*

The type of model to update, which is the constructor of a [Table](../#table)\-decorated class.

___
<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Overrides [UpdateModel](updatemodel.md).[colStore](updatemodel.md#colstore)*

*Defined in [query/update/mysql-update-model.ts:35](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L35)*

Used for accessing columns in tables.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[MySQLEscaper](mysqlescaper.md)*

*Overrides [UpdateModel](updatemodel.md).[escaper](updatemodel.md#escaper)*

*Defined in [query/update/mysql-update-model.ts:39](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L39)*

A [MySQLEscaper](mysqlescaper.md) instance. Used when escaping column names in compiled conditions.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[MySQLExecuter](mysqlexecuter.md)*

*Overrides [UpdateModel](updatemodel.md).[executer](updatemodel.md#executer)*

*Defined in [query/update/mysql-update-model.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L40)*

A [MySQLExecuter](mysqlexecuter.md) instance for executing queries.

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

*Overrides [UpdateModel](updatemodel.md).[model](updatemodel.md#model)*

*Defined in [query/update/mysql-update-model.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L42)*

An Entity instance to update, which must have the primary key set.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Overrides [UpdateModel](updatemodel.md).[propStore](updatemodel.md#propstore)*

*Defined in [query/update/mysql-update-model.ts:38](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L38)*

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

*Overrides [UpdateModel](updatemodel.md).[relStore](updatemodel.md#relstore)*

*Defined in [query/update/mysql-update-model.ts:37](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L37)*

Used for accessing relationships between tables.

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Overrides [UpdateModel](updatemodel.md).[tblStore](updatemodel.md#tblstore)*

*Defined in [query/update/mysql-update-model.ts:36](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L36)*

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

*Inherited from [UpdateModel](updatemodel.md).[createUpdateModel](updatemodel.md#createupdatemodel)*

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

*Inherited from [UpdateModel](updatemodel.md).[execute](updatemodel.md#execute)*

*Overrides [Query](query.md).[execute](query.md#execute)*

*Defined in [query/update/update-model.ts:96](https://github.com/benbotto/formn/blob/f28037b/src/query/update/update-model.ts#L96)*

Execute the query.

**Returns:** `Promise`<`T`>
A promise that shall be resolved with the mutated model.

___
<a id="producequery"></a>

### `<Protected>` produceQuery

▸ **produceQuery**(from: *[From](from.md)*): [MySQLUpdate](mysqlupdate.md)

*Overrides [UpdateModel](updatemodel.md).[produceQuery](updatemodel.md#producequery)*

*Defined in [query/update/mysql-update-model.ts:53](https://github.com/benbotto/formn/blob/f28037b/src/query/update/mysql-update-model.ts#L53)*

Produce a [MySQLUpdate](mysqlupdate.md) instance using the [From](from.md) instance and the update model created from createUpdateModel.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| from | [From](from.md) |  A [From](from.md) instance, passed to the [MySQLUpdate](mysqlupdate.md) constructor. constructor. |

**Returns:** [MySQLUpdate](mysqlupdate.md)

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


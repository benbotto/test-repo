[formn](../README.md) > [DataContext](../classes/datacontext.md)

# Class: DataContext

This is the main interface to the ORM. It provides access to CRUD operations and connection management.

## Hierarchy

**DataContext**

↳  [MySQLDataContext](mysqldatacontext.md)

## Index

### Constructors

* [constructor](datacontext.md#constructor)

### Properties

* [colStore](datacontext.md#colstore)
* [propStore](datacontext.md#propstore)
* [relStore](datacontext.md#relstore)
* [tblStore](datacontext.md#tblstore)

### Methods

* [connect](datacontext.md#connect)
* [delete](datacontext.md#delete)
* [end](datacontext.md#end)
* [from](datacontext.md#from)
* [getEscaper](datacontext.md#getescaper)
* [getExecuter](datacontext.md#getexecuter)
* [insert](datacontext.md#insert)
* [update](datacontext.md#update)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new DataContext**(): [DataContext](datacontext.md)

*Defined in [datacontext/data-context.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L27)*

Initialize the DataContext.

**Returns:** [DataContext](datacontext.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Defined in [datacontext/data-context.ts:24](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L24)*

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Defined in [datacontext/data-context.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L27)*

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Defined in [datacontext/data-context.ts:26](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L26)*

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Defined in [datacontext/data-context.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L25)*

___

## Methods

<a id="connect"></a>

### `<Abstract>` connect

▸ **connect**(connOpts: *[ConnectionOptions](connectionoptions.md)*): `Promise`<`this`>

*Defined in [datacontext/data-context.ts:113](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L113)*

Connect to the database.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| connOpts | [ConnectionOptions](connectionoptions.md) |  Connection options for setting up a connection to the database. |

**Returns:** `Promise`<`this`>
A promise that will be resolved with this [[DataContext]] instance.

___
<a id="delete"></a>

###  delete

▸ **delete**<`T`>(Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [DeleteModel](deletemodel.md)<`T`>

*Defined in [datacontext/data-context.ts:102](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L102)*

Create a new [DeleteModel](deletemodel.md) instance that can be used to delete a model by ID. For complex delete operations, use the [DataContext.from](datacontext.md#from) method to obtain a [FromAdapter](fromadapter.md) instance, and then call [FromAdapter.delete](fromadapter.md#delete) on that instance.

**Type parameters:**

#### T 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to delete, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to delete, which must have the primary key set. |

**Returns:** [DeleteModel](deletemodel.md)<`T`>
A [[DeleteModel]] instance that can be executed using
[[DeleteModel.execute]].

___
<a id="end"></a>

### `<Abstract>` end

▸ **end**(): `Promise`<`void`>

*Defined in [datacontext/data-context.ts:118](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L118)*

End the connection pool.

**Returns:** `Promise`<`void`>

___
<a id="from"></a>

### `<Abstract>` from

▸ **from**<`T`>(Entity: *[TableType](../#tabletype)*, alias: *`string`*): [FromAdapter](fromadapter.md)<`T`>

*Defined in [datacontext/data-context.ts:74](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L74)*

Create a new [FromAdapter](fromadapter.md) instance, which can then be used to select, update, or delete.

**Type parameters:**

#### T 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [TableType](../#tabletype) |  A [Table](../#table)\-decorated entity which is the constructor of the FROM table. |
| alias | `string` |  Alias for the FROM table, used in conditions, joins, and column selection. Optional: defaults to the name of the table. |

**Returns:** [FromAdapter](fromadapter.md)<`T`>
A [[FromAdapter]] that implements [[FromAdapter.select]],
[[FromAdapter.update]], and [[FromAdapter.delete]].

___
<a id="getescaper"></a>

### `<Abstract>` getEscaper

▸ **getEscaper**(): [Escaper](escaper.md)

*Defined in [datacontext/data-context.ts:49](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L49)*

Get an [Escaper](escaper.md) instance for the database (e.g. [MySQLEscaper](mysqlescaper.md)).

**Returns:** [Escaper](escaper.md)

___
<a id="getexecuter"></a>

### `<Abstract>` getExecuter

▸ **getExecuter**(): [Executer](../interfaces/executer.md)

*Defined in [datacontext/data-context.ts:44](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L44)*

Get an [Executer](../interfaces/executer.md) instance for the database (e.g. [MySQLExecuter](mysqlexecuter.md)).

**Returns:** [Executer](../interfaces/executer.md)

___
<a id="insert"></a>

###  insert

▸ **insert**<`T`>(Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [Insert](insert.md)<`T`>

*Defined in [datacontext/data-context.ts:59](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L59)*

Create and return a new [Insert](insert.md) instance.

**Type parameters:**

#### T 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to insert, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to insert. |

**Returns:** [Insert](insert.md)<`T`>
An [[Insert]] instance that can be executed using
[[Insert.execute]].

___
<a id="update"></a>

### `<Abstract>` update

▸ **update**<`T`>(Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [UpdateModel](updatemodel.md)<`T`>

*Defined in [datacontext/data-context.ts:88](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L88)*

Create a new [UpdateModel](updatemodel.md) instance that can be used to update a model by ID. For complex update operations, use the [DataContext.from](datacontext.md#from) method to obtain a [FromAdapter](fromadapter.md) instance, and then call [FromAdapter.update](fromadapter.md#update) on that instance.

**Type parameters:**

#### T 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to update, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to update, which must have the primary key set. |

**Returns:** [UpdateModel](updatemodel.md)<`T`>
An [[UpdateModel]] instance that can be executed using
[[UpdateModel.execute]].

___


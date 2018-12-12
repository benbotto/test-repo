[formn](../README.md) > [MySQLDataContext](../classes/mysqldatacontext.md)

# Class: MySQLDataContext

A [DataContext](datacontext.md) class specialized for MySQL.

## Hierarchy

 [DataContext](datacontext.md)

**↳ MySQLDataContext**

## Index

### Constructors

* [constructor](mysqldatacontext.md#constructor)

### Properties

* [colStore](mysqldatacontext.md#colstore)
* [connMan](mysqldatacontext.md#connman)
* [escaper](mysqldatacontext.md#escaper)
* [executer](mysqldatacontext.md#executer)
* [propStore](mysqldatacontext.md#propstore)
* [relStore](mysqldatacontext.md#relstore)
* [tblStore](mysqldatacontext.md#tblstore)

### Methods

* [connect](mysqldatacontext.md#connect)
* [delete](mysqldatacontext.md#delete)
* [end](mysqldatacontext.md#end)
* [from](mysqldatacontext.md#from)
* [getEscaper](mysqldatacontext.md#getescaper)
* [getExecuter](mysqldatacontext.md#getexecuter)
* [insert](mysqldatacontext.md#insert)
* [update](mysqldatacontext.md#update)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MySQLDataContext**(): [MySQLDataContext](mysqldatacontext.md)

*Overrides [DataContext](datacontext.md).[constructor](datacontext.md#constructor)*

*Defined in [datacontext/mysql-data-context.ts:32](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L32)*

Initialize the [DataContext](datacontext.md).

**Returns:** [MySQLDataContext](mysqldatacontext.md)

___

## Properties

<a id="colstore"></a>

### `<Protected>` colStore

**● colStore**: *[ColumnStore](columnstore.md)*

*Inherited from [DataContext](datacontext.md).[colStore](datacontext.md#colstore)*

*Defined in [datacontext/data-context.ts:24](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L24)*

___
<a id="connman"></a>

### `<Protected>` connMan

**● connMan**: *[MySQLConnectionManager](mysqlconnectionmanager.md)*

*Defined in [datacontext/mysql-data-context.ts:32](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L32)*

Manages the connection pool.

___
<a id="escaper"></a>

### `<Protected>` escaper

**● escaper**: *[MySQLEscaper](mysqlescaper.md)*

*Defined in [datacontext/mysql-data-context.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L27)*

Used for escaping queries.

___
<a id="executer"></a>

### `<Protected>` executer

**● executer**: *[MySQLExecuter](mysqlexecuter.md)*

*Defined in [datacontext/mysql-data-context.ts:22](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L22)*

Used for executing queries.

___
<a id="propstore"></a>

### `<Protected>` propStore

**● propStore**: *[PropertyMapStore](propertymapstore.md)*

*Inherited from [DataContext](datacontext.md).[propStore](datacontext.md#propstore)*

*Defined in [datacontext/data-context.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L27)*

___
<a id="relstore"></a>

### `<Protected>` relStore

**● relStore**: *[RelationshipStore](relationshipstore.md)*

*Inherited from [DataContext](datacontext.md).[relStore](datacontext.md#relstore)*

*Defined in [datacontext/data-context.ts:26](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L26)*

___
<a id="tblstore"></a>

### `<Protected>` tblStore

**● tblStore**: *[TableStore](tablestore.md)*

*Inherited from [DataContext](datacontext.md).[tblStore](datacontext.md#tblstore)*

*Defined in [datacontext/data-context.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/data-context.ts#L25)*

___

## Methods

<a id="connect"></a>

###  connect

▸ **connect**(connOpts: *[ConnectionOptions](connectionoptions.md)*): `Promise`<`this`>

*Overrides [DataContext](datacontext.md).[connect](datacontext.md#connect)*

*Defined in [datacontext/mysql-data-context.ts:101](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L101)*

Connect to the database.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| connOpts | [ConnectionOptions](connectionoptions.md) |  Connection options for setting up a connection to the database. |

**Returns:** `Promise`<`this`>
A promise that will be resolved with this [[MySQLDataContext]]
instance.

___
<a id="delete"></a>

###  delete

▸ **delete**<`T`>(Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [DeleteModel](deletemodel.md)<`T`>

*Inherited from [DataContext](datacontext.md).[delete](datacontext.md#delete)*

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

###  end

▸ **end**(): `Promise`<`void`>

*Overrides [DataContext](datacontext.md).[end](datacontext.md#end)*

*Defined in [datacontext/mysql-data-context.ts:114](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L114)*

End the connection pool.

**Returns:** `Promise`<`void`>

___
<a id="from"></a>

###  from

▸ **from**<`T`>(Entity: *[EntityType](../#entitytype)<`T`>*, alias: *`string`*): [MySQLFromAdapter](mysqlfromadapter.md)<`T`>

*Overrides [DataContext](datacontext.md).[from](datacontext.md#from)*

*Defined in [datacontext/mysql-data-context.ts:72](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L72)*

Create a new [MySQLFromAdapter](mysqlfromadapter.md) instance, which can then be used to select, update, or delete.

**Type parameters:**

#### T 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [EntityType](../#entitytype)<`T`> |  A [Table](../#table)\-decorated entity which is the constructor of the FROM table. |
| alias | `string` |  Alias for the FROM table, used in conditions, joins, and column selection. Optional: defaults to the name of the table. |

**Returns:** [MySQLFromAdapter](mysqlfromadapter.md)<`T`>
A [[MySQLFromAdapter]] that implements [[MySQLFromAdapter.select]],
[[MySQLFromAdapter.update]], and [[MySQLFromAdapter.delete]].

___
<a id="getescaper"></a>

###  getEscaper

▸ **getEscaper**(): [MySQLEscaper](mysqlescaper.md)

*Overrides [DataContext](datacontext.md).[getEscaper](datacontext.md#getescaper)*

*Defined in [datacontext/mysql-data-context.ts:58](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L58)*

Get a [MySQLEscaper](mysqlescaper.md) instance for escaping column and table names.

**Returns:** [MySQLEscaper](mysqlescaper.md)

___
<a id="getexecuter"></a>

###  getExecuter

▸ **getExecuter**(): [MySQLExecuter](mysqlexecuter.md)

*Overrides [DataContext](datacontext.md).[getExecuter](datacontext.md#getexecuter)*

*Defined in [datacontext/mysql-data-context.ts:48](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L48)*

Get a [MySQLExecuter](mysqlexecuter.md) instance that can be used to execute queries.

**Returns:** [MySQLExecuter](mysqlexecuter.md)

___
<a id="insert"></a>

###  insert

▸ **insert**<`T`>(Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [Insert](insert.md)<`T`>

*Inherited from [DataContext](datacontext.md).[insert](datacontext.md#insert)*

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

###  update

▸ **update**<`T`>(Entity: *[EntityType](../#entitytype)<`T`>*, model: *`T`*): [MySQLUpdateModel](mysqlupdatemodel.md)<`T`>

*Overrides [DataContext](datacontext.md).[update](datacontext.md#update)*

*Defined in [datacontext/mysql-data-context.ts:89](https://github.com/benbotto/formn/blob/f28037b/src/datacontext/mysql-data-context.ts#L89)*

Create a new [MySQLUpdateModel](mysqlupdatemodel.md) instance that can be used to update a model by ID. For complex update operations, use the [MySQLDataContext.from](mysqldatacontext.md#from) method to obtain a [MySQLFromAdapter](mysqlfromadapter.md) instance, and then call [MySQLFromAdapter.update](mysqlfromadapter.md#update) on that instance.

**Type parameters:**

#### T 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [EntityType](../#entitytype)<`T`> |  The type of model to update, which is the constructor of a [Table](../#table)\-decorated class. |
| model | `T` |  An Entity instance to update, which must have the primary key set. |

**Returns:** [MySQLUpdateModel](mysqlupdatemodel.md)<`T`>
An [[MySQLUpdateModel]] instance that can be executed using
[[MySQLUpdateModel.execute]].

___


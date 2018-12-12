[formn](../README.md) > [TableMetadata](../classes/tablemetadata.md)

# Class: TableMetadata

Stores metadata about [Table](../#table)\-decorated classes.

## Hierarchy

**TableMetadata**

## Index

### Constructors

* [constructor](tablemetadata.md#constructor)

### Properties

* [Entity](tablemetadata.md#entity)
* [database](tablemetadata.md#database)
* [name](tablemetadata.md#name)
* [schema](tablemetadata.md#schema)

### Methods

* [getFQName](tablemetadata.md#getfqname)
* [produceEntity](tablemetadata.md#produceentity)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new TableMetadata**(Entity: *[TableType](../#tabletype)*, name: *`string`*, database: *`string`*, schema?: *`string`*): [TableMetadata](tablemetadata.md)

*Defined in [metadata/table/table-metadata.ts:7](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-metadata.ts#L7)*

Initialize the Table's metadata.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [TableType](../#tabletype) |  The constructor for the @[Table](../#table)\-decorated class. |
| name | `string` |  The name of the database table. |
| database | `string` |  The database to which this table belongs. |
| `Optional` schema | `string` |  The database schema, if any. |

**Returns:** [TableMetadata](tablemetadata.md)

___

## Properties

<a id="entity"></a>

###  Entity

**● Entity**: *[TableType](../#tabletype)*

*Defined in [metadata/table/table-metadata.ts:16](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-metadata.ts#L16)*

The constructor for the @[Table](../#table)\-decorated class.

___
<a id="database"></a>

###  database

**● database**: *`string`*

*Defined in [metadata/table/table-metadata.ts:18](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-metadata.ts#L18)*

The database to which this table belongs.

___
<a id="name"></a>

###  name

**● name**: *`string`*

*Defined in [metadata/table/table-metadata.ts:17](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-metadata.ts#L17)*

The name of the database table.

___
<a id="schema"></a>

### `<Optional>` schema

**● schema**: *`string`*

*Defined in [metadata/table/table-metadata.ts:19](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-metadata.ts#L19)*

The database schema, if any.

___

## Methods

<a id="getfqname"></a>

###  getFQName

▸ **getFQName**(): `string`

*Defined in [metadata/table/table-metadata.ts:34](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-metadata.ts#L34)*

Get the fully-qualified table name in the form <schema>.<name>.

**Returns:** `string`

___
<a id="produceentity"></a>

###  produceEntity

▸ **produceEntity**(): `any`

*Defined in [metadata/table/table-metadata.ts:26](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-metadata.ts#L26)*

Produce an entity.

**Returns:** `any`
An instance of Entity type.

___


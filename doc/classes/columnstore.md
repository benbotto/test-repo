[formn](../README.md) > [ColumnStore](../classes/columnstore.md)

# Class: ColumnStore

Storage for [ColumnMetadata](columnmetadata.md) with lookup operations.

## Hierarchy

**ColumnStore**

## Index

### Methods

* [addColumnMetadata](columnstore.md#addcolumnmetadata)
* [getColumnMetadata](columnstore.md#getcolumnmetadata)
* [getColumnMetadataByMapping](columnstore.md#getcolumnmetadatabymapping)
* [getColumnMetadataByName](columnstore.md#getcolumnmetadatabyname)
* [getPrimaryKey](columnstore.md#getprimarykey)

---

## Methods

<a id="addcolumnmetadata"></a>

###  addColumnMetadata

▸ **addColumnMetadata**(col: *[ColumnMetadata](columnmetadata.md)*): `this`

*Defined in [metadata/column/column-store.ts:14](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-store.ts#L14)*

Add a column's metadata.

**Parameters:**

| Name | Type |
| ------ | ------ |
| col | [ColumnMetadata](columnmetadata.md) |

**Returns:** `this`

___
<a id="getcolumnmetadata"></a>

###  getColumnMetadata

▸ **getColumnMetadata**(Entity: *[TableType](../#tabletype)*): [ColumnMetadata](columnmetadata.md)[]

*Defined in [metadata/column/column-store.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-store.ts#L31)*

Get all the [ColumnMetadata](columnmetadata.md) for a [Table](../#table)\-decorated Entity.

**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |

**Returns:** [ColumnMetadata](columnmetadata.md)[]

___
<a id="getcolumnmetadatabymapping"></a>

###  getColumnMetadataByMapping

▸ **getColumnMetadataByMapping**(Entity: *[TableType](../#tabletype)*, mapTo: *`string`*): [ColumnMetadata](columnmetadata.md)

*Defined in [metadata/column/column-store.ts:55](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-store.ts#L55)*

Get the [ColumnMetadata](columnmetadata.md) for a [Table](../#table)\-decorated Entity by column mapping (property name in parent Entity).

**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |
| mapTo | `string` |

**Returns:** [ColumnMetadata](columnmetadata.md)

___
<a id="getcolumnmetadatabyname"></a>

###  getColumnMetadataByName

▸ **getColumnMetadataByName**(Entity: *[TableType](../#tabletype)*, name: *`string`*): [ColumnMetadata](columnmetadata.md)

*Defined in [metadata/column/column-store.ts:42](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-store.ts#L42)*

Get the [ColumnMetadata](columnmetadata.md) for a [Table](../#table)\-decorated Entity by column name.

**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |
| name | `string` |

**Returns:** [ColumnMetadata](columnmetadata.md)

___
<a id="getprimarykey"></a>

###  getPrimaryKey

▸ **getPrimaryKey**(Entity: *[TableType](../#tabletype)*): [ColumnMetadata](columnmetadata.md)[]

*Defined in [metadata/column/column-store.ts:67](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-store.ts#L67)*

Get the primary key for a table.

**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |

**Returns:** [ColumnMetadata](columnmetadata.md)[]

___


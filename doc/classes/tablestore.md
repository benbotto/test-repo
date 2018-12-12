[formn](../README.md) > [TableStore](../classes/tablestore.md)

# Class: TableStore

Provides storage and lookup operations for [Table](../#table)\-decorated entities.

## Hierarchy

**TableStore**

## Index

### Methods

* [addTableMetadata](tablestore.md#addtablemetadata)
* [getTable](tablestore.md#gettable)
* [getTableMetadata](tablestore.md#gettablemetadata)

---

## Methods

<a id="addtablemetadata"></a>

###  addTableMetadata

▸ **addTableMetadata**(tbl: *[TableMetadata](tablemetadata.md)*): `this`

*Defined in [metadata/table/table-store.ts:14](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-store.ts#L14)*

Add a Table's metadata to the store.

**Parameters:**

| Name | Type |
| ------ | ------ |
| tbl | [TableMetadata](tablemetadata.md) |

**Returns:** `this`

___
<a id="gettable"></a>

###  getTable

▸ **getTable**(Entity: *[TableType](../#tabletype)*): [TableMetadata](tablemetadata.md)

*Defined in [metadata/table/table-store.ts:45](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-store.ts#L45)*

Get a table by type.

**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |

**Returns:** [TableMetadata](tablemetadata.md)

___
<a id="gettablemetadata"></a>

###  getTableMetadata

▸ **getTableMetadata**(database?: *`string`*): [TableMetadata](tablemetadata.md)[]

*Defined in [metadata/table/table-store.ts:34](https://github.com/benbotto/formn/blob/f28037b/src/metadata/table/table-store.ts#L34)*

Get all the TableMetadata for a database.

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` database | `string` | &quot;default&quot; |

**Returns:** [TableMetadata](tablemetadata.md)[]

___


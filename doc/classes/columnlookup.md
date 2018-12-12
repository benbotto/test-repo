[formn](../README.md) > [ColumnLookup](../classes/columnlookup.md)

# Class: ColumnLookup

Helper class that maps between column aliases and fully-qualified column names. Users of formn always deal with properties ([Column](../#column)\-decorated properties of [Table](../#table)\-decorated classes), and those properties need to be mapped to column names when querying. This class helps with that mapping process.

## Hierarchy

**ColumnLookup**

## Index

### Methods

* [addColumn](columnlookup.md#addcolumn)
* [getColumn](columnlookup.md#getcolumn)

---

## Methods

<a id="addcolumn"></a>

###  addColumn

▸ **addColumn**(property: *`string`*, fqColName: *`string`*): `this`

*Defined in [metadata/column/column-lookup.ts:20](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-lookup.ts#L20)*

Add a lookup from property to column.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| property | `string` |  The property name. |
| fqColName | `string` |  Generally this is a fully-qualified column name (see [ColumnMetadata.createFQName](columnmetadata.md#createfqname)), but it can be any string that's associated with property. |

**Returns:** `this`

___
<a id="getcolumn"></a>

###  getColumn

▸ **getColumn**(property: *`string`*): `string`

*Defined in [metadata/column/column-lookup.ts:29](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-lookup.ts#L29)*

Get the column associated with property or throw.

**Parameters:**

| Name | Type |
| ------ | ------ |
| property | `string` |

**Returns:** `string`

___


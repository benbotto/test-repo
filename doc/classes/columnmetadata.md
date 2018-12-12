[formn](../README.md) > [ColumnMetadata](../classes/columnmetadata.md)

# Class: ColumnMetadata

Stores metadata about [Column](../#column)\-decorated properties on [Table](../#table)\-decorated classes (Entities).

## Hierarchy

**ColumnMetadata**

## Index

### Constructors

* [constructor](columnmetadata.md#constructor)

### Properties

* [Entity](columnmetadata.md#entity)
* [converter](columnmetadata.md#converter)
* [dataType](columnmetadata.md#datatype)
* [defaultValue](columnmetadata.md#defaultvalue)
* [isGenerated](columnmetadata.md#isgenerated)
* [isNullable](columnmetadata.md#isnullable)
* [isPrimary](columnmetadata.md#isprimary)
* [mapTo](columnmetadata.md#mapto)
* [maxLength](columnmetadata.md#maxlength)
* [name](columnmetadata.md#name)

### Methods

* [createFQName](columnmetadata.md#createfqname)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new ColumnMetadata**(Entity: *[TableType](../#tabletype)*, mapTo: *`string`*, options: *[ColumnMetaOptions](columnmetaoptions.md)*): [ColumnMetadata](columnmetadata.md)

*Defined in [metadata/column/column-metadata.ts:19](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L19)*

Initialize the metadata for a column.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [TableType](../#tabletype) |  The constructor for the [Table](../#table)\-decorated class to which this column belongs. |
| mapTo | `string` |  The name of the property in the class to which this column will be mapped. |
| options | [ColumnMetaOptions](columnmetaoptions.md) |  Configuration options for this column with metadata like dataType, column name, etc. |

**Returns:** [ColumnMetadata](columnmetadata.md)

___

## Properties

<a id="entity"></a>

###  Entity

**● Entity**: *[TableType](../#tabletype)*

*Defined in [metadata/column/column-metadata.ts:10](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L10)*

___
<a id="converter"></a>

### `<Optional>` converter

**● converter**: *[Converter](converter.md)*

*Defined in [metadata/column/column-metadata.ts:19](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L19)*

___
<a id="datatype"></a>

###  dataType

**● dataType**: *`string`*

*Defined in [metadata/column/column-metadata.ts:17](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L17)*

___
<a id="defaultvalue"></a>

###  defaultValue

**● defaultValue**: *`string`*

*Defined in [metadata/column/column-metadata.ts:15](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L15)*

___
<a id="isgenerated"></a>

###  isGenerated

**● isGenerated**: *`boolean`*

*Defined in [metadata/column/column-metadata.ts:14](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L14)*

___
<a id="isnullable"></a>

###  isNullable

**● isNullable**: *`boolean`*

*Defined in [metadata/column/column-metadata.ts:16](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L16)*

___
<a id="isprimary"></a>

###  isPrimary

**● isPrimary**: *`boolean`*

*Defined in [metadata/column/column-metadata.ts:13](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L13)*

___
<a id="mapto"></a>

###  mapTo

**● mapTo**: *`string`*

*Defined in [metadata/column/column-metadata.ts:11](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L11)*

___
<a id="maxlength"></a>

### `<Optional>` maxLength

**● maxLength**: *`number`*

*Defined in [metadata/column/column-metadata.ts:18](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L18)*

___
<a id="name"></a>

###  name

**● name**: *`string`*

*Defined in [metadata/column/column-metadata.ts:12](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L12)*

___

## Methods

<a id="createfqname"></a>

### `<Static>` createFQName

▸ **createFQName**(tableAlias: *`string`*, colName: *`string`*): `string`

*Defined in [metadata/column/column-metadata.ts:55](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-metadata.ts#L55)*

Create a fully-qualified name in the form <table-alias>.<name>.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| tableAlias | `string` |  The alias for the table. |
| colName | `string` |  The name of a column or property. |

**Returns:** `string`
The fully-qualified column name, unescaped.

___


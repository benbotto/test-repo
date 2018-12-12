[formn](../README.md) > [ColumnMetaOptions](../classes/columnmetaoptions.md)

# Class: ColumnMetaOptions

Options for the [Column](../#column) decorator.

## Hierarchy

**ColumnMetaOptions**

## Index

### Properties

* [converter](columnmetaoptions.md#converter)
* [dataType](columnmetaoptions.md#datatype)
* [defaultValue](columnmetaoptions.md#defaultvalue)
* [isGenerated](columnmetaoptions.md#isgenerated)
* [isNullable](columnmetaoptions.md#isnullable)
* [isPrimary](columnmetaoptions.md#isprimary)
* [maxLength](columnmetaoptions.md#maxlength)
* [name](columnmetaoptions.md#name)

---

## Properties

<a id="converter"></a>

### `<Optional>` converter

**● converter**: *[Converter](converter.md)*

*Defined in [metadata/column/column-meta-options.ts:45](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L45)*

Optional Converter to be applied on save/retrieve.

___
<a id="datatype"></a>

### `<Optional>` dataType

**● dataType**: *`string`*

*Defined in [metadata/column/column-meta-options.ts:35](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L35)*

Data type for the column.

___
<a id="defaultvalue"></a>

### `<Optional>` defaultValue

**● defaultValue**: *`string`*

*Defined in [metadata/column/column-meta-options.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L25)*

The column's default value (quoted).

___
<a id="isgenerated"></a>

### `<Optional>` isGenerated

**● isGenerated**: *`boolean`*

*Defined in [metadata/column/column-meta-options.ts:20](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L20)*

Whether or not this column is auto-generated.

___
<a id="isnullable"></a>

### `<Optional>` isNullable

**● isNullable**: *`boolean`*

*Defined in [metadata/column/column-meta-options.ts:30](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L30)*

Whether or not the column is nullable.

___
<a id="isprimary"></a>

### `<Optional>` isPrimary

**● isPrimary**: *`boolean`*

*Defined in [metadata/column/column-meta-options.ts:15](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L15)*

Whether or not this column is the (or part of the) primary key.

___
<a id="maxlength"></a>

### `<Optional>` maxLength

**● maxLength**: *`number`*

*Defined in [metadata/column/column-meta-options.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L40)*

Max length for varchar-type fields.

___
<a id="name"></a>

### `<Optional>` name

**● name**: *`string`*

*Defined in [metadata/column/column-meta-options.ts:10](https://github.com/benbotto/formn/blob/f28037b/src/metadata/column/column-meta-options.ts#L10)*

Column name. Defaults to the name of the Column-decorated property.

___


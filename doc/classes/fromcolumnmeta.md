[formn](../README.md) > [FromColumnMeta](../classes/fromcolumnmeta.md)

# Class: FromColumnMeta

Metadata about columns available to a query (used in [From](from.md)).

## Hierarchy

**FromColumnMeta**

## Index

### Constructors

* [constructor](fromcolumnmeta.md#constructor)

### Properties

* [columnMetadata](fromcolumnmeta.md#columnmetadata)
* [fqColName](fromcolumnmeta.md#fqcolname)
* [fqProp](fromcolumnmeta.md#fqprop)
* [tableAlias](fromcolumnmeta.md#tablealias)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new FromColumnMeta**(tableAlias: *`string`*, columnMetadata: *[ColumnMetadata](columnmetadata.md)*, fqColName: *`string`*, fqProp: *`string`*): [FromColumnMeta](fromcolumnmeta.md)

*Defined in [query/from/from-column-meta.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-column-meta.ts#L6)*

Initialize the metadata.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| tableAlias | `string` |  The unique alias of the table to which the column belongs. |
| columnMetadata | [ColumnMetadata](columnmetadata.md) |  Metadata about the column ([Column](../#column)\-decorated property). |
| fqColName | `string` |  The fully-qualified column name, in the form &lt;table-alias&gt;.&lt;column-name&gt;. |
| fqProp | `string` |  The fully-qualified property name, in the form &lt;table-alias&gt;.&lt;property&gt;. |

**Returns:** [FromColumnMeta](fromcolumnmeta.md)

___

## Properties

<a id="columnmetadata"></a>

###  columnMetadata

**● columnMetadata**: *[ColumnMetadata](columnmetadata.md)*

*Defined in [query/from/from-column-meta.ts:20](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-column-meta.ts#L20)*

Metadata about the column ([Column](../#column)\-decorated property).

___
<a id="fqcolname"></a>

###  fqColName

**● fqColName**: *`string`*

*Defined in [query/from/from-column-meta.ts:21](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-column-meta.ts#L21)*

The fully-qualified column name, in the form <table-alias>.<column-name>.

___
<a id="fqprop"></a>

###  fqProp

**● fqProp**: *`string`*

*Defined in [query/from/from-column-meta.ts:22](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-column-meta.ts#L22)*

The fully-qualified property name, in the form <table-alias>.<property>.

___
<a id="tablealias"></a>

###  tableAlias

**● tableAlias**: *`string`*

*Defined in [query/from/from-column-meta.ts:19](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-column-meta.ts#L19)*

The unique alias of the table to which the column belongs.

___


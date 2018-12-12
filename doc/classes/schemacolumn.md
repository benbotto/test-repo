[formn](../README.md) > [SchemaColumn](../classes/schemacolumn.md)

# Class: SchemaColumn

This class is used to store column name-[ColumnMetadata](columnmetadata.md) associations in a [Schema](schema.md) instance.

## Hierarchy

**SchemaColumn**

## Index

### Constructors

* [constructor](schemacolumn.md#constructor)

### Properties

* [meta](schemacolumn.md#meta)
* [name](schemacolumn.md#name)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new SchemaColumn**(meta: *[ColumnMetadata](columnmetadata.md)*, name: *`string`*): [SchemaColumn](schemacolumn.md)

*Defined in [datamapper/schema-column.ts:7](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema-column.ts#L7)*

Initialize the SchemaColumn instance.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| meta | [ColumnMetadata](columnmetadata.md) |  Metadata about the column. |
| name | `string` |  Name of the column in the to-be-serialized query. |

**Returns:** [SchemaColumn](schemacolumn.md)

___

## Properties

<a id="meta"></a>

###  meta

**● meta**: *[ColumnMetadata](columnmetadata.md)*

*Defined in [datamapper/schema-column.ts:14](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema-column.ts#L14)*

Metadata about the column.

___
<a id="name"></a>

###  name

**● name**: *`string`*

*Defined in [datamapper/schema-column.ts:15](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema-column.ts#L15)*

Name of the column in the to-be-serialized query.

___


[formn](../README.md) > [Schema](../classes/schema.md)

# Class: Schema

A Schema is a representation of a serializable database table, consisting of a series of columns and [SubSchema](subschema.md) objects. It's used when mapping a query to a normalized document. The mapping is defined using [TableMetadata](tablemetadata.md), [ColumnMetadata](columnmetadata.md), and [RelationshipMetadata](relationshipmetadata.md).

## Hierarchy

**Schema**

## Index

### Constructors

* [constructor](schema.md#constructor)

### Properties

* [columns](schema.md#columns)
* [schemata](schema.md#schemata)
* [table](schema.md#table)

### Methods

* [addColumn](schema.md#addcolumn)
* [addSchema](schema.md#addschema)
* [getKeyColumn](schema.md#getkeycolumn)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new Schema**(table: *[TableMetadata](tablemetadata.md)*, keyColumnMeta: *[ColumnMetadata](columnmetadata.md)*, keyColumnName: *`string`*): [Schema](schema.md)

*Defined in [datamapper/schema.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema.ts#L27)*

Initialize the Schema instance. Note that the properties are treated as package private: they're accessed directly by DataMapper which provides an efficiency boost, and speed is important here.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| table | [TableMetadata](tablemetadata.md) |  Metadata for the [Table](../#table)\-decorated Entity. This is used to produce an instance of the Entity. |
| keyColumnMeta | [ColumnMetadata](columnmetadata.md) |  Metadata for the unique column in the table, generally the primary key. The metadata comes from a [Column](../#column)\-decorated property of a [Table](../#table)\-decorated class and has the name of the column, the property in the Entity, and an optional [Converter](converter.md). |
| keyColumnName | `string` |  The name of the column associated with keyColumn in the to-be-serialized query. |

**Returns:** [Schema](schema.md)

___

## Properties

<a id="columns"></a>

###  columns

**● columns**: *[SchemaColumn](schemacolumn.md)[]* =  []

*Defined in [datamapper/schema.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema.ts#L27)*

All the [ColumnMetadata](columnmetadata.md) objects (columns of the table) that will be mapped in the resulting document.

___
<a id="schemata"></a>

###  schemata

**● schemata**: *[SubSchema](subschema.md)[]* =  []

*Defined in [datamapper/schema.ts:21](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema.ts#L21)*

All the [SubSchema](subschema.md) instances of this schema.

___
<a id="table"></a>

###  table

**● table**: *[TableMetadata](tablemetadata.md)*

*Defined in [datamapper/schema.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema.ts#L43)*

Metadata for the [Table](../#table)\-decorated Entity. This is used to produce an instance of the Entity.

___

## Methods

<a id="addcolumn"></a>

###  addColumn

▸ **addColumn**(meta: *[ColumnMetadata](columnmetadata.md)*, name: *`string`*): `this`

*Defined in [datamapper/schema.ts:66](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema.ts#L66)*

Add a column to the schema.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| meta | [ColumnMetadata](columnmetadata.md) |  Metadata for the column. The metadata comes from a [Column](../#column)\-decorated property of a [Table](../#table)\-decorated class and has the name of the column, the property in the Entity, and an optional [Converter](converter.md). |
| name | `string` |  The name of the column in the to-be-serialized query. |

**Returns:** `this`

___
<a id="addschema"></a>

###  addSchema

▸ **addSchema**(schema: *[Schema](schema.md)*, relationship: *[RelationshipMetadata](relationshipmetadata.md)*): `this`

*Defined in [datamapper/schema.ts:86](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema.ts#L86)*

Add a [SubSchema](subschema.md), which is a related [Table](../#table)\-decorated Entity and will be nested under this Schema using the [RelationshipMetadata](relationshipmetadata.md).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| schema | [Schema](schema.md) |  A Schema instance. |
| relationship | [RelationshipMetadata](relationshipmetadata.md) |  Relationship metadata for the relationship between this Schema and the sub-Schema. The relationship must be from this Schema's [Table](../#table) to the sub-Schema's [Table](../#table). |

**Returns:** `this`

___
<a id="getkeycolumn"></a>

###  getKeyColumn

▸ **getKeyColumn**(): [SchemaColumn](schemacolumn.md)

*Defined in [datamapper/schema.ts:54](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/schema.ts#L54)*

Helper function to get the key column data (first column in the list of [SchemaColumn](schemacolumn.md)s).

**Returns:** [SchemaColumn](schemacolumn.md)

___


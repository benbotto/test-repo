[formn](../README.md) > [SubSchema](../classes/subschema.md)

# Class: SubSchema

This class is used within [Schema](schema.md) to represent a sub schema, which is a mapping definition (a [Schema](schema.md) instance) and relationship information ([RelationshipMetadata](relationshipmetadata.md)).

## Hierarchy

**SubSchema**

## Index

### Constructors

* [constructor](subschema.md#constructor)

### Properties

* [relationship](subschema.md#relationship)
* [schema](subschema.md#schema)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new SubSchema**(schema: *[Schema](schema.md)*, relationship: *[RelationshipMetadata](relationshipmetadata.md)*): [SubSchema](subschema.md)

*Defined in [datamapper/sub-schema.ts:9](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/sub-schema.ts#L9)*

Initialize the SubSchema.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| schema | [Schema](schema.md) |  A Schema instance for data mapping. |
| relationship | [RelationshipMetadata](relationshipmetadata.md) |  Metadata about the relationship from the parent [Schema](schema.md) to the child. |

**Returns:** [SubSchema](subschema.md)

___

## Properties

<a id="relationship"></a>

###  relationship

**● relationship**: *[RelationshipMetadata](relationshipmetadata.md)*

*Defined in [datamapper/sub-schema.ts:18](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/sub-schema.ts#L18)*

Metadata about the relationship from the parent [Schema](schema.md) to the child.

___
<a id="schema"></a>

###  schema

**● schema**: *[Schema](schema.md)*

*Defined in [datamapper/sub-schema.ts:17](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/sub-schema.ts#L17)*

A Schema instance for data mapping.

___


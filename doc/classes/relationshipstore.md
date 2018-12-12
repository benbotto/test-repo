[formn](../README.md) > [RelationshipStore](../classes/relationshipstore.md)

# Class: RelationshipStore

Stores relationships and provides lookup functions.

## Hierarchy

**RelationshipStore**

## Index

### Methods

* [addRelationshipMetadata](relationshipstore.md#addrelationshipmetadata)
* [getRelationship](relationshipstore.md#getrelationship)
* [getRelationships](relationshipstore.md#getrelationships)

---

## Methods

<a id="addrelationshipmetadata"></a>

###  addRelationshipMetadata

▸ **addRelationshipMetadata**(rel: *[RelationshipMetadata](relationshipmetadata.md)*): `this`

*Defined in [metadata/relationship/relationship-store.ts:13](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-store.ts#L13)*

Add a relationship.

**Parameters:**

| Name | Type |
| ------ | ------ |
| rel | [RelationshipMetadata](relationshipmetadata.md) |

**Returns:** `this`

___
<a id="getrelationship"></a>

###  getRelationship

▸ **getRelationship**(Entity1: *[TableType](../#tabletype)*, Entity2: *[TableType](../#tabletype)*, mapTo: *`string`*): [RelationshipMetadata](relationshipmetadata.md)

*Defined in [metadata/relationship/relationship-store.ts:66](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-store.ts#L66)*

Get the relationship between two tables on a property. Short-hand for getRelationships with oneWay=true, but throws if the relationship does not exist.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity1 | [TableType](../#tabletype) |  The first Entity (constructor), i.e. the class that's decorated with @[Table](../#table). |
| Entity2 | [TableType](../#tabletype) |  The second Entity. |
| mapTo | `string` |  The proeprty on Entity1 where the relationship is defined. |

**Returns:** [RelationshipMetadata](relationshipmetadata.md)
The RelationshipMetadata for the relationship.

___
<a id="getrelationships"></a>

###  getRelationships

▸ **getRelationships**(Entity1: *[TableType](../#tabletype)*, Entity2: *[TableType](../#tabletype)*, oneWay?: *`boolean`*, mapTo?: *`string`*): [RelationshipMetadata](relationshipmetadata.md)[]

*Defined in [metadata/relationship/relationship-store.ts:30](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-store.ts#L30)*

Get all of the relationships between two tables.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| Entity1 | [TableType](../#tabletype) | - |  The first Entity (constructor), i.e. the class that's decorated with @[Table](../#table). |
| Entity2 | [TableType](../#tabletype) | - |  The second Entity. |
| `Default value` oneWay | `boolean` | false |  When true, only return the relationships between Entity1 and Entity2 that Entity1 owns. |
| `Default value` mapTo | `string` |  null |  An optional property on Entity1. If passed, return the relationship for this property only (implies oneWay). |

**Returns:** [RelationshipMetadata](relationshipmetadata.md)[]
An array of RelationshipMetadata instances.

___


[formn](../README.md) > [RelationshipMetadata](../classes/relationshipmetadata.md)

# Class: RelationshipMetadata

Represents a relationship between two tables.

## Hierarchy

**RelationshipMetadata**

## Index

### Constructors

* [constructor](relationshipmetadata.md#constructor)

### Properties

* [Entity](relationshipmetadata.md#entity)
* [cardinality](relationshipmetadata.md#cardinality)
* [mapTo](relationshipmetadata.md#mapto)
* [on](relationshipmetadata.md#on)
* [to](relationshipmetadata.md#to)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new RelationshipMetadata**(Entity: *[TableType](../#tabletype)*, mapTo: *`string`*, to: *`function`*, on: *`function`*, cardinality: *[CardinalityType](../#cardinalitytype)*): [RelationshipMetadata](relationshipmetadata.md)

*Defined in [metadata/relationship/relationship-metadata.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-metadata.ts#L6)*

Initialize the relationship metadata.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [TableType](../#tabletype) |  The type (constructor) of the table where this relationship was defined. |
| mapTo | `string` |  The property in Entity on which this relationship was defined. |
| to | `function` |  A function that, when called, returns the referenced Entity type (constructor). |
| on | `function` |  A function that, when called, returns an array consisting of the names of the local and remote properties. E.g. (user, phoneNumber) => \[user.id, phoneNumber.userID\] (returns \['userID', 'phoneNumberID'\]). The function will be passed [PropertyMapType](../#propertymaptype)s containing all the decorated properties of Entity and RefEntity. |
| cardinality | [CardinalityType](../#cardinalitytype) |  The relationship type (e.g. OneToMany). |

**Returns:** [RelationshipMetadata](relationshipmetadata.md)

___

## Properties

<a id="entity"></a>

###  Entity

**● Entity**: *[TableType](../#tabletype)*

*Defined in [metadata/relationship/relationship-metadata.ts:23](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-metadata.ts#L23)*

The type (constructor) of the table where this relationship was defined.

___
<a id="cardinality"></a>

###  cardinality

**● cardinality**: *[CardinalityType](../#cardinalitytype)*

*Defined in [metadata/relationship/relationship-metadata.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-metadata.ts#L27)*

The relationship type (e.g. OneToMany).

___
<a id="mapto"></a>

###  mapTo

**● mapTo**: *`string`*

*Defined in [metadata/relationship/relationship-metadata.ts:24](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-metadata.ts#L24)*

The property in Entity on which this relationship was defined.

___
<a id="on"></a>

###  on

**● on**: *`function`*

*Defined in [metadata/relationship/relationship-metadata.ts:26](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-metadata.ts#L26)*

A function that, when called, returns an array consisting of the names of the local and remote properties. E.g. (user, phoneNumber) => \[user.id, phoneNumber.userID\] (returns \['userID', 'phoneNumberID'\]). The function will be passed [PropertyMapType](../#propertymaptype)s containing all the decorated properties of Entity and RefEntity.

#### Type declaration
▸(entity: *[PropertyMapType](../#propertymaptype)*, refEntity: *[PropertyMapType](../#propertymaptype)*): `string`[]

**Parameters:**

| Name | Type |
| ------ | ------ |
| entity | [PropertyMapType](../#propertymaptype) |
| refEntity | [PropertyMapType](../#propertymaptype) |

**Returns:** `string`[]

___
<a id="to"></a>

###  to

**● to**: *`function`*

*Defined in [metadata/relationship/relationship-metadata.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-metadata.ts#L25)*

A function that, when called, returns the referenced Entity type (constructor).

#### Type declaration
▸(): [TableType](../#tabletype)

**Returns:** [TableType](../#tabletype)

___


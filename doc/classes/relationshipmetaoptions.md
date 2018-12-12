[formn](../README.md) > [RelationshipMetaOptions](../classes/relationshipmetaoptions.md)

# Class: RelationshipMetaOptions

Options for the [Relationship](../#relationship) decorator. Reads "ENT\_T is related to REF\_ENT\_T."

## Type parameters
#### ENT_T 
#### REF_ENT_T 
## Hierarchy

**RelationshipMetaOptions**

## Index

### Properties

* [cardinality](relationshipmetaoptions.md#cardinality)
* [on](relationshipmetaoptions.md#on)
* [to](relationshipmetaoptions.md#to)

---

## Properties

<a id="cardinality"></a>

###  cardinality

**● cardinality**: *[CardinalityType](../#cardinalitytype)*

*Defined in [metadata/relationship/relationship-meta-options.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-meta-options.ts#L25)*

Cardinality of the relationship (e.g. OneToOne, ManyToOne, etc.).

___
<a id="on"></a>

###  on

**● on**: *`function`*

*Defined in [metadata/relationship/relationship-meta-options.ts:20](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-meta-options.ts#L20)*

How ENT\_T and REF\_ENT\_T are related. This is a function that, given ENT\_T and REF\_ENT\_T [PropertyMapType](../#propertymaptype)s returns an array of Column-decorated property names that will be used to join the two tables.

#### Type declaration
▸(ent: * `ENT_T` &#124; [PropertyMapType](../#propertymaptype)*, refEnt: * `REF_ENT_T` &#124; [PropertyMapType](../#propertymaptype)*):  `string`[] &#124; `any`[]

**Parameters:**

| Name | Type |
| ------ | ------ |
| ent |  `ENT_T` &#124; [PropertyMapType](../#propertymaptype)|
| refEnt |  `REF_ENT_T` &#124; [PropertyMapType](../#propertymaptype)|

**Returns:**  `string`[] &#124; `any`[]

___
<a id="to"></a>

###  to

**● to**: *`function`*

*Defined in [metadata/relationship/relationship-meta-options.ts:13](https://github.com/benbotto/formn/blob/f28037b/src/metadata/relationship/relationship-meta-options.ts#L13)*

Function that returns the type of Table that this references (e.g. the constructor of the associated [Table](../#table)\-decorated class).

#### Type declaration
▸(): `object`

**Returns:** `object`

___


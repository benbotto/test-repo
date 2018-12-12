[formn](../README.md) > [PropertyMapStore](../classes/propertymapstore.md)

# Class: PropertyMapStore

Stores property maps for each [Table](../#table)\-decorated Entity. A property map is a simple key-value pair. The keys are all the properties of Entity, and each maps to the property name as a string.

## Hierarchy

**PropertyMapStore**

## Index

### Methods

* [addProperty](propertymapstore.md#addproperty)
* [getPropertyMap](propertymapstore.md#getpropertymap)

---

## Methods

<a id="addproperty"></a>

###  addProperty

▸ **addProperty**(Entity: *[TableType](../#tabletype)*, property: *`string`*): `this`

*Defined in [metadata/property/property-map-store.ts:17](https://github.com/benbotto/formn/blob/f28037b/src/metadata/property/property-map-store.ts#L17)*

Add a property to the store.

**Parameters:**

| Name | Type |
| ------ | ------ |
| Entity | [TableType](../#tabletype) |
| property | `string` |

**Returns:** `this`

___
<a id="getpropertymap"></a>

###  getPropertyMap

▸ **getPropertyMap**(Entity: *[TableType](../#tabletype)*, alias?: *`string`*): [PropertyMapType](../#propertymaptype)

*Defined in [metadata/property/property-map-store.ts:40](https://github.com/benbotto/formn/blob/f28037b/src/metadata/property/property-map-store.ts#L40)*

Get the property map for a table. For each property in the [Table](../#table)\-decorated Entity, the property map is a simple key-value pair. The keys are all the properties of Entity, and each maps to the property name as a string.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| Entity | [TableType](../#tabletype) |  The [Table](../#table)\-decorated Entity. |
| `Optional` alias | `string` |  An optional table alias. If supplied each value in the property map will be prefixed with the alias as &lt;alias&gt;.&lt;property&gt;. |

**Returns:** [PropertyMapType](../#propertymaptype)

___


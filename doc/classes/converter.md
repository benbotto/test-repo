[formn](../README.md) > [Converter](../classes/converter.md)

# Class: Converter

A converter is used to transform a [Column](../#column)\-decorated property on save or retrieve. For example, formatting dates to and from ISO8601.

## Hierarchy

**Converter**

## Index

### Methods

* [onRetrieve](converter.md#onretrieve)
* [onSave](converter.md#onsave)

---

## Methods

<a id="onretrieve"></a>

###  onRetrieve

▸ **onRetrieve**(val: *`any`*): `any`

*Defined in [converter/converter.ts:9](https://github.com/benbotto/formn/blob/f28037b/src/converter/converter.ts#L9)*

Identity converter on retrieve.

**Parameters:**

| Name | Type |
| ------ | ------ |
| val | `any` |

**Returns:** `any`

___
<a id="onsave"></a>

###  onSave

▸ **onSave**(val: *`any`*): `any`

*Defined in [converter/converter.ts:16](https://github.com/benbotto/formn/blob/f28037b/src/converter/converter.ts#L16)*

Identity converter on save.

**Parameters:**

| Name | Type |
| ------ | ------ |
| val | `any` |

**Returns:** `any`

___


[formn](../README.md) > [ParameterList](../classes/parameterlist.md)

# Class: ParameterList

A class that holds query parameters.

## Hierarchy

**ParameterList**

## Index

### Constructors

* [constructor](parameterlist.md#constructor)

### Methods

* [addParameter](parameterlist.md#addparameter)
* [addParameters](parameterlist.md#addparameters)
* [createParameterName](parameterlist.md#createparametername)
* [getParam](parameterlist.md#getparam)
* [getParamID](parameterlist.md#getparamid)
* [getParamNames](parameterlist.md#getparamnames)
* [getParams](parameterlist.md#getparams)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new ParameterList**(paramList?: *[ParameterList](parameterlist.md)*): [ParameterList](parameterlist.md)

*Defined in [query/condition/parameter-list.ts:13](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L13)*

Initialize the list of parameters.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| `Optional` paramList | [ParameterList](parameterlist.md) |  An optional list of parameters to copy. |

**Returns:** [ParameterList](parameterlist.md)

___

## Methods

<a id="addparameter"></a>

###  addParameter

▸ **addParameter**(key: *`string`*, value: *`any`*, overwrite?: *`boolean`*): `this`

*Defined in [query/condition/parameter-list.ts:81](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L81)*

Add a parameter to the list.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| key | `string` | - |  The name of the parameter. |
| value | `any` | - |  The parameter value. |
| `Default value` overwrite | `boolean` | false |  By default, an exception will be raised if a parameter matching key already exists and the value is different. If this flag is set to true, however, then parameters will be blindly overwritten. |

**Returns:** `this`

___
<a id="addparameters"></a>

###  addParameters

▸ **addParameters**(params: *[ParameterType](../#parametertype)*, overwrite?: *`boolean`*): `this`

*Defined in [query/condition/parameter-list.ts:99](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L99)*

Add parameters to the list.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| params | [ParameterType](../#parametertype) | - |  An object containing key-value pairs. |
| `Default value` overwrite | `boolean` | false |  Whether or not to blindly overwrite existing parameters. |

**Returns:** `this`

___
<a id="createparametername"></a>

###  createParameterName

▸ **createParameterName**(key: *`string`*): `string`

*Defined in [query/condition/parameter-list.ts:69](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L69)*

Create a parameter name by replacing all non-word characters with underscores and adding a unique ID at the end.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| key | `string` |  The parameter key. |

**Returns:** `string`
The unique parameter name.

___
<a id="getparam"></a>

###  getParam

▸ **getParam**(key: *`string`*): `any`

*Defined in [query/condition/parameter-list.ts:43](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L43)*

Get a single param or throw.

**Parameters:**

| Name | Type |
| ------ | ------ |
| key | `string` |

**Returns:** `any`

___
<a id="getparamid"></a>

###  getParamID

▸ **getParamID**(): `number`

*Defined in [query/condition/parameter-list.ts:59](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L59)*

Get the parameterID, which is used for auto-generated parameters.

**Returns:** `number`

___
<a id="getparamnames"></a>

###  getParamNames

▸ **getParamNames**(): `string`[]

*Defined in [query/condition/parameter-list.ts:52](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L52)*

Get all the parameter names.

**Returns:** `string`[]

___
<a id="getparams"></a>

###  getParams

▸ **getParams**(): [ParameterType](../#parametertype)

*Defined in [query/condition/parameter-list.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/parameter-list.ts#L31)*

Get all the parameters as key-value pairs.

**Returns:** [ParameterType](../#parametertype)

___


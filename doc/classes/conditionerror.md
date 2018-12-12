[formn](../README.md) > [ConditionError](../classes/conditionerror.md)

# Class: ConditionError

Custom Error instance for Condition (lex/parse/compile) errors.

## Hierarchy

 `Error`

**↳ ConditionError**

## Index

### Constructors

* [constructor](conditionerror.md#constructor)

### Properties

* [detail](conditionerror.md#detail)
* [message](conditionerror.md#message)
* [name](conditionerror.md#name)
* [stack](conditionerror.md#stack)
* [Error](conditionerror.md#error)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new ConditionError**(message: *`string`*): [ConditionError](conditionerror.md)

*Defined in [error/condition-error.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/error/condition-error.ts#L6)*

Create the Error instance with a user-supplied message.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| message | `string` |  The Description of the error. |

**Returns:** [ConditionError](conditionerror.md)

___

## Properties

<a id="detail"></a>

###  detail

**● detail**: *`string`*

*Defined in [error/condition-error.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/error/condition-error.ts#L6)*

___
<a id="message"></a>

###  message

**● message**: *`string`*

*Inherited from Error.message*

*Defined in /home/node/dev/node_modules/typescript/lib/lib.es5.d.ts:904*

___
<a id="name"></a>

###  name

**● name**: *`string`*

*Overrides Error.name*

*Defined in [error/condition-error.ts:5](https://github.com/benbotto/formn/blob/f28037b/src/error/condition-error.ts#L5)*

___
<a id="stack"></a>

### `<Optional>` stack

**● stack**: *`string`*

*Inherited from Error.stack*

*Overrides Error.stack*

*Defined in /home/node/dev/node_modules/typescript/lib/lib.es5.d.ts:905*

___
<a id="error"></a>

### `<Static>` Error

**● Error**: *`ErrorConstructor`*

*Defined in /home/node/dev/node_modules/typescript/lib/lib.es5.d.ts:914*

___


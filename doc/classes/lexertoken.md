[formn](../README.md) > [LexerToken](../classes/lexertoken.md)

# Class: LexerToken

A token that's generated from the [ConditionLexer](conditionlexer.md). It has a type, a terminal flag, and a value, and is intended for use with the [ConditionParser](conditionparser.md).

## Hierarchy

**LexerToken**

## Index

### Constructors

* [constructor](lexertoken.md#constructor)

### Properties

* [terminal](lexertoken.md#terminal)
* [type](lexertoken.md#type)
* [value](lexertoken.md#value)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new LexerToken**(terminal: *`boolean`*, type: *`string`*, value: * `string` &#124; `number`*): [LexerToken](lexertoken.md)

*Defined in [query/condition/lexer-token.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/lexer-token.ts#L6)*

Initialize the token.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| terminal | `boolean` |  Whether or not the token is terminal. |
| type | `string` |  The token type, as a string (e.g. boolean-operator). |
| value |  `string` &#124; `number`|  The value of the token. |

**Returns:** [LexerToken](lexertoken.md)

___

## Properties

<a id="terminal"></a>

###  terminal

**● terminal**: *`boolean`*

*Defined in [query/condition/lexer-token.ts:14](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/lexer-token.ts#L14)*

Whether or not the token is terminal.

___
<a id="type"></a>

###  type

**● type**: *`string`*

*Defined in [query/condition/lexer-token.ts:15](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/lexer-token.ts#L15)*

The token type, as a string (e.g. boolean-operator).

___
<a id="value"></a>

###  value

**● value**: * `string` &#124; `number`
*

*Defined in [query/condition/lexer-token.ts:16](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/lexer-token.ts#L16)*

The value of the token.

___


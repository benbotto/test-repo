[formn](../README.md) > [ConditionLexer](../classes/conditionlexer.md)

# Class: ConditionLexer

Class that lexicographically parses a condition object into tokens.

## Hierarchy

**ConditionLexer**

## Index

### Methods

* [parse](conditionlexer.md#parse)

---

## Methods

<a id="parse"></a>

###  parse

▸ **parse**(condStr: * `string` &#124; `any`*): [LexerToken](lexertoken.md)[]

*Defined in [query/condition/condition-lexer.ts:16](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/condition-lexer.ts#L16)*

Parse the sentence into tokens.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| condStr |  `string` &#124; `any`|  The condition string to parse. If condStr is an object it is converted to a string using JSON.stringify. |

**Returns:** [LexerToken](lexertoken.md)[]
An array of tokens.  Each token object has the following
properties: terminal, which is a boolean indicating if the token is a
terminal or not; type, as described by the condition BNF; and value.

___


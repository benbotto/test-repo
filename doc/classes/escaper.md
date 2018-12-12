[formn](../README.md) > [Escaper](../classes/escaper.md)

# Class: Escaper

Helper class for escaping parts of a query.

## Hierarchy

**Escaper**

↳  [MySQLEscaper](mysqlescaper.md)

↳  [MSSQLEscaper](mssqlescaper.md)

## Index

### Methods

* [escapeFullyQualifiedColumn](escaper.md#escapefullyqualifiedcolumn)
* [escapeProperty](escaper.md#escapeproperty)

---

## Methods

<a id="escapefullyqualifiedcolumn"></a>

###  escapeFullyQualifiedColumn

▸ **escapeFullyQualifiedColumn**(fqc: *`string`*): `string`

*Defined in [query/escaper/escaper.ts:16](https://github.com/benbotto/formn/blob/f28037b/src/query/escaper/escaper.ts#L16)*

Escape a fully-qualified column name, such as 'u.firstName' or 'phone\_numbers.phoneNumber'.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| fqc | `string` |  The fully-qualified column. |

**Returns:** `string`
The escaped column name.

___
<a id="escapeproperty"></a>

### `<Abstract>` escapeProperty

▸ **escapeProperty**(prop: *`string`*): `string`

*Defined in [query/escaper/escaper.ts:8](https://github.com/benbotto/formn/blob/f28037b/src/query/escaper/escaper.ts#L8)*

Escape a property, such as a table, column name, or alias.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| prop | `string` |  The property to escape. |

**Returns:** `string`
The escaped property as a string.

___


[formn](../README.md) > [MSSQLEscaper](../classes/mssqlescaper.md)

# Class: MSSQLEscaper

Helper class for escaping parts of a query under MSSQL.

## Hierarchy

 [Escaper](escaper.md)

**↳ MSSQLEscaper**

## Index

### Constructors

* [constructor](mssqlescaper.md#constructor)

### Methods

* [escapeFullyQualifiedColumn](mssqlescaper.md#escapefullyqualifiedcolumn)
* [escapeProperty](mssqlescaper.md#escapeproperty)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MSSQLEscaper**(): [MSSQLEscaper](mssqlescaper.md)

*Defined in [query/escaper/mssql-escaper.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/query/escaper/mssql-escaper.ts#L6)*

Initialize the escaper.

**Returns:** [MSSQLEscaper](mssqlescaper.md)

___

## Methods

<a id="escapefullyqualifiedcolumn"></a>

###  escapeFullyQualifiedColumn

▸ **escapeFullyQualifiedColumn**(fqc: *`string`*): `string`

*Inherited from [Escaper](escaper.md).[escapeFullyQualifiedColumn](escaper.md#escapefullyqualifiedcolumn)*

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

###  escapeProperty

▸ **escapeProperty**(prop: *`string`*): `string`

*Overrides [Escaper](escaper.md).[escapeProperty](escaper.md#escapeproperty)*

*Defined in [query/escaper/mssql-escaper.ts:19](https://github.com/benbotto/formn/blob/f28037b/src/query/escaper/mssql-escaper.ts#L19)*

Escape a property, such as a table, column name, or alias.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| prop | `string` |  The property to escape. |

**Returns:** `string`
The escaped property.

___


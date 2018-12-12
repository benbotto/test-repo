[formn](../README.md) > [MySQLEscaper](../classes/mysqlescaper.md)

# Class: MySQLEscaper

Helper class for escaping parts of a query under MySQL.

## Hierarchy

 [Escaper](escaper.md)

**↳ MySQLEscaper**

## Index

### Constructors

* [constructor](mysqlescaper.md#constructor)

### Methods

* [escapeFullyQualifiedColumn](mysqlescaper.md#escapefullyqualifiedcolumn)
* [escapeProperty](mysqlescaper.md#escapeproperty)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new MySQLEscaper**(): [MySQLEscaper](mysqlescaper.md)

*Defined in [query/escaper/mysql-escaper.ts:6](https://github.com/benbotto/formn/blob/f28037b/src/query/escaper/mysql-escaper.ts#L6)*

Initialize the escaper.

**Returns:** [MySQLEscaper](mysqlescaper.md)

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

*Defined in [query/escaper/mysql-escaper.ts:20](https://github.com/benbotto/formn/blob/f28037b/src/query/escaper/mysql-escaper.ts#L20)*

Escape a property, such as a table, column name, or alias, using backticks.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| prop | `string` |  The property to escape. |

**Returns:** `string`
The escaped property.

___


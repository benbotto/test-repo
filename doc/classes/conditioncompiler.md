[formn](../README.md) > [ConditionCompiler](../classes/conditioncompiler.md)

# Class: ConditionCompiler

A class that compiles a [ParseTree](parsetree.md), as created by a [ConditionParser](conditionparser.md) instance, into a SQL condition.

## Hierarchy

**ConditionCompiler**

## Index

### Constructors

* [constructor](conditioncompiler.md#constructor)

### Methods

* [compile](conditioncompiler.md#compile)
* [getColumns](conditioncompiler.md#getcolumns)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new ConditionCompiler**(escaper: *[Escaper](escaper.md)*): [ConditionCompiler](conditioncompiler.md)

*Defined in [query/condition/condition-compiler.ts:15](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/condition-compiler.ts#L15)*

Initialize the compiler.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| escaper | [Escaper](escaper.md) |  An instance of an [Escaper](escaper.md) that matches the database type (e.g. [MySQLEscaper](mysqlescaper.md) or [MSSQLEscaper](mssqlescaper.md)). This is used for escaping column names. |

**Returns:** [ConditionCompiler](conditioncompiler.md)

___

## Methods

<a id="compile"></a>

###  compile

▸ **compile**(parseTree: *[ParseTree](parsetree.md)*, params?: *[ParameterType](../#parametertype)*, columnLookup?: *[ColumnLookup](columnlookup.md)*): `string`

*Defined in [query/condition/condition-compiler.ts:38](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/condition-compiler.ts#L38)*

Compile the parse tree.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| parseTree | [ParseTree](parsetree.md) | - |  A [ParseTree](parsetree.md) object, as created by the [ConditionParser.parse](conditionparser.md#parse) method. |
| `Default value` params | [ParameterType](../#parametertype) |  {} |  An object containing key-value pairs that are used to replace parameters in the query. The compiler verifies that there is a replacement for every parameter, but does not perform the actual replacement. |
| `Optional` columnLookup | [ColumnLookup](columnlookup.md) | - |  An optional [ColumnLookup](columnlookup.md) instance. When provided, the name of each column in the condition will be replaced with the value returned from [ColumnLookup.getColumn](columnlookup.md#getcolumn). |

**Returns:** `string`
The compiled condition as a SQL string.

___
<a id="getcolumns"></a>

###  getColumns

▸ **getColumns**(parseTree: *[ParseTree](parsetree.md)*): `string`[]

*Defined in [query/condition/condition-compiler.ts:167](https://github.com/benbotto/formn/blob/f28037b/src/query/condition/condition-compiler.ts#L167)*

Get all the columns referenced in the [ParseTree](parsetree.md) and return them as an array. The columns will be distinct (that is, if the same column appears multiple times in the same condition, it will exist in the returned array only once).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| parseTree | [ParseTree](parsetree.md) |  The [ParseTree](parsetree.md), as created by a [ConditionParser](conditionparser.md). |

**Returns:** `string`[]

___


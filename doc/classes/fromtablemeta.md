[formn](../README.md) > [FromTableMeta](../classes/fromtablemeta.md)

# Class: FromTableMeta

Keeps metadata about a table that is used in the FROM portion of a query.

## Hierarchy

**FromTableMeta**

## Index

### Constructors

* [constructor](fromtablemeta.md#constructor)

### Properties

* [alias](fromtablemeta.md#alias)
* [cond](fromtablemeta.md#cond)
* [condStr](fromtablemeta.md#condstr)
* [joinType](fromtablemeta.md#jointype)
* [parentAlias](fromtablemeta.md#parentalias)
* [relationshipMetadata](fromtablemeta.md#relationshipmetadata)
* [tableMetadata](fromtablemeta.md#tablemetadata)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new FromTableMeta**(tableMetadata: *[TableMetadata](tablemetadata.md)*, alias: *`string`*, parentAlias?: *`string`*, relationshipMetadata?: *[RelationshipMetadata](relationshipmetadata.md)*, joinType?: *[JoinType](../#jointype)*, cond?: *`object`*, condStr?: *`string`*): [FromTableMeta](fromtablemeta.md)

*Defined in [query/from/from-table-meta.ts:8](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L8)*

Store the table metadata.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| tableMetadata | [TableMetadata](tablemetadata.md) | - |  Metadata about the table. |
| alias | `string` | - |  An alias for the table. This is needed if, for example, the same table is joined in multiple times. |
| `Default value` parentAlias | `string` |  null |  The alias of the parent table, if any. |
| `Default value` relationshipMetadata | [RelationshipMetadata](relationshipmetadata.md) |  null |  Metadata about the relationship from the parent to the child. |
| `Default value` joinType | [JoinType](../#jointype) |  null |  The type of join (inner/outer) if this table was joined in, or null for the top-level table. |
| `Default value` cond | `object` |  null |  A join condition for the two tables, or a where condition for the base table. |
| `Default value` condStr | `string` |  null |  The compiled condition string as created by a [ConditionCompiler](conditioncompiler.md). |

**Returns:** [FromTableMeta](fromtablemeta.md)

___

## Properties

<a id="alias"></a>

###  alias

**● alias**: *`string`*

*Defined in [query/from/from-table-meta.ts:26](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L26)*

An alias for the table. This is needed if, for example, the same table is joined in multiple times.

___
<a id="cond"></a>

###  cond

**● cond**: *`object`*

*Defined in [query/from/from-table-meta.ts:30](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L30)*

A join condition for the two tables, or a where condition for the base table.

___
<a id="condstr"></a>

###  condStr

**● condStr**: *`string`*

*Defined in [query/from/from-table-meta.ts:31](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L31)*

The compiled condition string as created by a [ConditionCompiler](conditioncompiler.md).

___
<a id="jointype"></a>

###  joinType

**● joinType**: *[JoinType](../#jointype)*

*Defined in [query/from/from-table-meta.ts:29](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L29)*

The type of join (inner/outer) if this table was joined in, or null for the top-level table.

___
<a id="parentalias"></a>

###  parentAlias

**● parentAlias**: *`string`*

*Defined in [query/from/from-table-meta.ts:27](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L27)*

The alias of the parent table, if any.

___
<a id="relationshipmetadata"></a>

###  relationshipMetadata

**● relationshipMetadata**: *[RelationshipMetadata](relationshipmetadata.md)*

*Defined in [query/from/from-table-meta.ts:28](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L28)*

Metadata about the relationship from the parent to the child.

___
<a id="tablemetadata"></a>

###  tableMetadata

**● tableMetadata**: *[TableMetadata](tablemetadata.md)*

*Defined in [query/from/from-table-meta.ts:25](https://github.com/benbotto/formn/blob/f28037b/src/query/from/from-table-meta.ts#L25)*

Metadata about the table.

___


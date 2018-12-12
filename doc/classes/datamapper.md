[formn](../README.md) > [DataMapper](../classes/datamapper.md)

# Class: DataMapper

Class that serializes a [Schema](schema.md) instance in to a normalized document (a series of [Table](../#table)\-decorated Entities).

## Hierarchy

**DataMapper**

## Index

### Methods

* [serialize](datamapper.md#serialize)

---

## Methods

<a id="serialize"></a>

###  serialize

▸ **serialize**<`T`>(query: *`any`[]*, schema: *[Schema](schema.md)*): `T`[]

*Defined in [datamapper/data-mapper.ts:19](https://github.com/benbotto/formn/blob/f28037b/src/datamapper/data-mapper.ts#L19)*

Serialize the query into the an array of objects, as defined by schema.

**Type parameters:**

#### T 
**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| query | `any`[] |  A set of query results, which is an array of objects containing keys as properties and values from a database query. |
| schema | [Schema](schema.md) |  The [Schema](schema.md) instance describing how to serialize the query. |

**Returns:** `T`[]
A normalized document (an array of T instances).

___


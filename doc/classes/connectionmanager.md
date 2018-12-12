[formn](../README.md) > [ConnectionManager](../classes/connectionmanager.md)

# Class: ConnectionManager

Manages database connections.

Connecting
----------

Here's how.

## Type parameters
#### T 
## Hierarchy

**ConnectionManager**

↳  [MySQLConnectionManager](mysqlconnectionmanager.md)

## Index

### Methods

* [connect](connectionmanager.md#connect)
* [end](connectionmanager.md#end)
* [getConnection](connectionmanager.md#getconnection)
* [getConnectionState](connectionmanager.md#getconnectionstate)

---

## Methods

<a id="connect"></a>

### `<Abstract>` connect

▸ **connect**(connOpts: *[ConnectionOptions](connectionoptions.md)*): `Promise`<`T`>

*Defined in [connection/connection-manager.ts:16](https://github.com/benbotto/formn/blob/f28037b/src/connection/connection-manager.ts#L16)*

Connect to the database.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| connOpts | [ConnectionOptions](connectionoptions.md) |  Connection options for setting up a connection to the database. |

**Returns:** `Promise`<`T`>
A promise that will be resolved with this underlying connection
instance.

___
<a id="end"></a>

### `<Abstract>` end

▸ **end**(): `Promise`<`void`>

*Defined in [connection/connection-manager.ts:21](https://github.com/benbotto/formn/blob/f28037b/src/connection/connection-manager.ts#L21)*

End the connection pool.

**Returns:** `Promise`<`void`>

___
<a id="getconnection"></a>

### `<Abstract>` getConnection

▸ **getConnection**(): `T`

*Defined in [connection/connection-manager.ts:32](https://github.com/benbotto/formn/blob/f28037b/src/connection/connection-manager.ts#L32)*

Get the underlying connection object. Its type is database flavor specific.

**Returns:** `T`

___
<a id="getconnectionstate"></a>

### `<Abstract>` getConnectionState

▸ **getConnectionState**(): [ConnectionStateType](../#connectionstatetype)

*Defined in [connection/connection-manager.ts:26](https://github.com/benbotto/formn/blob/f28037b/src/connection/connection-manager.ts#L26)*

Get the connection state.

**Returns:** [ConnectionStateType](../#connectionstatetype)

___


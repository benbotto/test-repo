[formn](../README.md) > [MySQLConnectionManager](../classes/mysqlconnectionmanager.md)

# Class: MySQLConnectionManager

A [ConnectionManager](connectionmanager.md) class specialized for MySQL.

## Hierarchy

 [ConnectionManager](connectionmanager.md)<`Pool`>

**↳ MySQLConnectionManager**

## Index

### Methods

* [connect](mysqlconnectionmanager.md#connect)
* [end](mysqlconnectionmanager.md#end)
* [getConnection](mysqlconnectionmanager.md#getconnection)
* [getConnectionState](mysqlconnectionmanager.md#getconnectionstate)

---

## Methods

<a id="connect"></a>

###  connect

▸ **connect**(connOpts: *[ConnectionOptions](connectionoptions.md)*): `Promise`<`Pool`>

*Overrides [ConnectionManager](connectionmanager.md).[connect](connectionmanager.md#connect)*

*Defined in [connection/mysql-connection-manager.ts:28](https://github.com/benbotto/formn/blob/f28037b/src/connection/mysql-connection-manager.ts#L28)*

Connect to the database.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| connOpts | [ConnectionOptions](connectionoptions.md) |  Connection options for setting up a connection to the database. |

**Returns:** `Promise`<`Pool`>
A promise that will be resolved with this underlying connection
instance.

___
<a id="end"></a>

###  end

▸ **end**(): `Promise`<`void`>

*Overrides [ConnectionManager](connectionmanager.md).[end](connectionmanager.md#end)*

*Defined in [connection/mysql-connection-manager.ts:57](https://github.com/benbotto/formn/blob/f28037b/src/connection/mysql-connection-manager.ts#L57)*

End the connection pool.

**Returns:** `Promise`<`void`>

___
<a id="getconnection"></a>

###  getConnection

▸ **getConnection**(): `Pool`

*Overrides [ConnectionManager](connectionmanager.md).[getConnection](connectionmanager.md#getconnection)*

*Defined in [connection/mysql-connection-manager.ts:80](https://github.com/benbotto/formn/blob/f28037b/src/connection/mysql-connection-manager.ts#L80)*

Get the underlying connection object.

**Returns:** `Pool`

___
<a id="getconnectionstate"></a>

###  getConnectionState

▸ **getConnectionState**(): [ConnectionStateType](../#connectionstatetype)

*Overrides [ConnectionManager](connectionmanager.md).[getConnectionState](connectionmanager.md#getconnectionstate)*

*Defined in [connection/mysql-connection-manager.ts:73](https://github.com/benbotto/formn/blob/f28037b/src/connection/mysql-connection-manager.ts#L73)*

Get the connection state.

**Returns:** [ConnectionStateType](../#connectionstatetype)

___


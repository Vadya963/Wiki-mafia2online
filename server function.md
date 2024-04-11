### Vehicle Functions
- [createVehicle](#createVehicle)
- [destroyVehicle](#destroyVehicle)

### Event Functions
- [triggerClientEvent](#triggerClientEvent)
---

### createVehicle
This function is used to create a vehicle at a 3D position.

#### Syntax
```js
createVehicle(int model, float x, float y, float z, float rx, float ry, float rz)
```

#### Arguments
- **int model**: The model ID of the vehicle you would like to create
- **float x**: The X position to create the vehicle at
- **float y**: The Y position to create the vehicle at
- **float z**: The Z position to create the vehicle at
- **float rx**: The RX (rotation) position to create the vehicle at
- **float ry**: The RY (rotation) position to create the vehicle at
- **float rz**: The RZ (rotation) position to create the vehicle at

#### Return Values
- **int** - vehicleid which was created

#### Example
```js
//SERVER
addCommandHandler( "run",
function( playerid )
{
	local myPos = getPlayerPosition(playerid)
	local vehicleid = createVehicle( 0, myPos[0], myPos[1], myPos[2], 0.0, 0.0, 0.0 );
});
```
---
### destroyVehicle
This function is used to destroy (remove) a created vehicle.

#### Syntax
```js
destroyVehicle(int vehicleid)
```

#### Arguments
- **int vehicleid**: The vehicleid to destroy

#### Return Values
Returns 'true' if successful, 'false' otherwise.

#### Example
```js
//SERVER
addCommandHandler( "run",
function( playerid )
{
	local myPos = getPlayerPosition(playerid)
	local vehicleid = createVehicle( 0, myPos[0], myPos[1], myPos[2], 0.0, 0.0, 0.0 );
	destroyVehicle( vehicleid );
});
```
---
### triggerClientEvent
This function is used to trigger a client event

#### Syntax
```js
triggerClientEvent(int playerid, string event, ...)
```

#### Arguments
- **int playerid**: The ID of the player
- **string event**: The name of the event to trigger
- **...**: (Optional) Arguments to sent to the events function

#### Return Values
Returns 'true' if successful, 'false' otherwise.

#### Example
```js
//SERVER
function playerSpawn( playerid )
{
	triggerClientEvent( playerid, "myEvent", "My String" );
}
addEventHandler( "onPlayerSpawn", playerSpawn );

//CLIENT
addEventHandler("myEvent",
function( str )
{
	log( "Output: " + str );
});
```
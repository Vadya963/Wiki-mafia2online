### Command Functions
- [addCommandHandler](#addCommandHandler)

### Event functions
- [addEventHandler](#addEventHandler)
- [callEvent](#callEvent)

### Blip functions
- [createBlip](#createBlip)
- [destroyBlip](#destroyBlip)
- [attachBlipToPed](#attachBlipToPed)
- [attachBlipToPlayer](#attachBlipToPlayer)
- [attachBlipToVehicle](#attachBlipToVehicle)

### Util functions
- [clamp](#clamp)
- [date](#date)
- [fromRGB](#fromRGB)

### Area Functions
- [getDistanceBetweenPoints2D](#getDistanceBetweenPoints2D)
- [getDistanceBetweenPoints3D](#getDistanceBetweenPoints3D)

### Vehicle functions
- [explodeVehicle](#explodeVehicle)
---

### addCommandHandler
This function is used to add a command handler.

#### Syntax
```js
addCommandHandler(string command, function)
```

#### Arguments
- **string command**: The command which would be typed into the chat
- **function**: The function to call when the command is typed

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//SERVER
addCommandHandler( "run",
function( playerid )
{
	setPlayerHealth( playerid, 720.0 );
});
```
---
### addEventHandler
This function is used to create a function handler for an event.

#### Syntax
```js
addEventHandler(string event, function)
```

#### Arguments
- **string event**: The name of the event
- **function**: The function which will be called when the event is triggered

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//SERVER
function init()
{
	setGameModeText( "My GameMode Name" );
	setMapName( "My Map Name" );
}
addEventHandler( "onScriptInit", init );
```
---
### attachBlipToPed
This function is used to attach a blip to a ped.

#### Syntax
```js
attachBlipToPed(int blipid, int pedid)
```

#### Arguments
- **int blipid**: The ID of the blip you want to establish
- **int pedid**: The ID of the ped

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//CLIENT
addCommandHandler ( "run", 
function ( playerid )
{
	local pedid = createPed( 0, 100.0, 100.0, -20.0, 0.0, 0.0, 0.0 );
	local blipid = createBlip( -300.0, 120.0, 0, 1 );
	attachBlipToPed( blipid, pedid );
	return 1;
});
```
---
### attachBlipToPlayer
This function is used to attach a blip to a player.

#### Syntax
```js
attachBlipToPlayer(int blipid, int playerid)
```

#### Arguments
- **int blipid**: The ID of the blip you want to establish
- **int playerid**: The ID of the player

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//SERVER
addCommandHandler ( "run", 
function ( playerid )
{
	local blipid = createBlip( -300.0, 120.0, 0, 1 );
	attachBlipToPlayer( blipid, playerid );
	return 1;
});
```
---
### attachBlipToVehicle
This function is used to attach a blip to a vehicle.

#### Syntax
```js
attachBlipToVehicle(int blipid, int vehicleid)
```

#### Arguments
- **int blipid**: The ID of the blip you want to establish
- **int vehicleid**: The ID of the vehicle

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//SERVER
addCommandHandler ( "run", 
function ( playerid )
{
	local vehicleid = createVehicle( 0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0 );
	local blipid = createBlip( -300.0, 120.0, 0, 1 );
	attachBlipToVehicle( blipid, vehicleid );
	return 1;
});
```
---
### callEvent
This function is used to call an event created by addEventHandler

#### Syntax
```js
callEvent(string event, ...)
```

#### Arguments
- **string event**: The event name
- **...** : (Optional) Arguments to pass onto the event

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//SERVER
function init()
{
	// Call customEvent and pass 53 as an argument
	callEvent("customEvent", 53);
}
addEventHandler( "onScriptInit", init );

function customEventFnc( total )
{
	// This would output "Total Is: 53"
	log( "Total is: " + total );
}
addEventHandler ( "customEvent", customEventFnc );
```
---
### clamp
This function is used to clamp a value between a minimum float and maximum float value.

#### Syntax
```js
clamp(float minimum, float value, float maximum)
```

#### Arguments
- **float minimum**: The minimum float
- **float value**: The value
- **float maximum**: The maximum float

#### Return Values
- **float** - The clamped value

#### Example
```js
//SERVER
function init()
{
	// This would output: Clamp: 3
	log("Clamp: " + clamp(1.0, 10.0, 3.0) );
}
addEventHandler( "onScriptInit", init );
```
---
### createBlip
This function is used to create a blip on the mini-map.

#### Syntax
```js
createBlip(float x, float y, int library, int icon)
```

#### Arguments
- **float x**: The X position of the blip
- **float y**: The Y position of the blip
- **int library**: The ID of the icon's library
- **int icon**: The ID of the icon

#### Return Values
- **int** - The created blipid

#### Example
```js
//SERVER
function init()
{
	createBlip( -300.0, 120.0, 0, 1 );
}
addEventHandler( "onScriptInit", init );
```
---
### date
This function is used to return the current date.

#### Syntax
```js
date()
```

#### Return Values
- **table** -  day, month, year and yearday

#### Example
```js
//SERVER
function init()
{
	local currentDate = date();
	log( currentDate["day"] + "," + currentDate["month"] + "," + currentDate["year"] + "," +currentDate["yearday"] );
}
addEventHandler( "onScriptInit", init );
```
---
### destroyBlip
This function is used to destroy a blip.

#### Syntax
```js
destroyBlip(int blipid)
```

#### Arguments
- **int blipid**: The ID of the blip you want to destroy

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//SERVER
function init()
{
	local blipid = createBlip( -300.0, 120.0, 0, 1 );
	destroyBlip(blipid)
}
addEventHandler( "onScriptInit", init );
```
---
### explodeVehicle
This function is used to explode vehicle.

#### Syntax
```js
explodeVehicle(int vehicleid)
```

#### Arguments
- **int vehicleid**: The ID of the vehicle

#### Return Values
- **true** - Successfully
- **false** - Incorrect

#### Example
```js
//SERVER
addCommandHandler( "run",
function( playerid )
{
	local myPos = getPlayerPosition(playerid)
	local vehicleid = createVehicle( 0, myPos[0], myPos[1], myPos[2], 0.0, 0.0, 0.0 );
	explodeVehicle( vehicleid );
});
```
---
### fromRGB
This function is used to convert a RGB(A) colour.

#### Syntax
```js
fromRGB(int r, int g, int b[, a = 255])
```

#### Arguments
- **int r**: The red (RGB) colour
- **int g**: The green (RGB) colour
- **int b**: The blue (RGB) colour
- **int a**: (Optional) The alpha, default 255

#### Return Values
- **array** - R, G, B and A colours

#### Example
```js
//CLIENT
addEventHandler( "onClientFrameRender",
function( post )
{
	dxDrawText("hello world", 0.0, 0.0, fromRGB(255, 255, 255, 255), true, "tahoma-bold", 1.0);
});
```
---
### getDistanceBetweenPoints2D
This function is used to return the distance between two 2D points.

#### Syntax
```js
getDistanceBetweenPoints2D(float PointX, float PointY, float pointX2, float pointY2)
```

#### Arguments
- **float PointX**: The X coordinate of the first point
- **float PointY**: The Y coordinate of the first point
- **float pointX2**: The X coordinate of the second point
- **float pointY2**: The Y coordinate of the second point

#### Return Values
- **float** - distance

#### Example
```js
//SERVER
addCommandHandler( "run",
function( playerid )
{
	local myPos = getPlayerPosition(playerid)
	local dis = getDistanceBetweenPoints2D( 400.0, 200.0, myPos[0], myPos[1] );
	sendPlayerMessage( playerid, "Distance between points: " + dis + "." );
});
```
---
### getDistanceBetweenPoints3D
This function is used to return the distance between two 3D points.

#### Syntax
```js
getDistanceBetweenPoints3D(float PointX, float PointY, float PointZ, float pointX2, float pointY2, float pointZ2)
```

#### Arguments
- **float PointX**: The X coordinate of the first point
- **float PointY**: The Y coordinate of the first point
- **float PointZ**: The Z coordinate of the first point
- **float pointX2**: The X coordinate of the second point
- **float pointY2**: The Y coordinate of the second point
- **float pointZ2**: The Z coordinate of the second point

#### Return Values
- **float** - distance

#### Example
```js
//SERVER
addCommandHandler( "run",
function( playerid )
{
	local myPos = getPlayerPosition(playerid)
	local dis = getDistanceBetweenPoints3D( 400.0, 200.0, -14.0, myPos[0], myPos[1], myPos[2] );
	sendPlayerMessage( playerid, "Distance between points: " + dis + "." );
});
```
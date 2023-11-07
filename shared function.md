- [addCommandHandler](#addCommandHandler)
- [addEventHandler](#addEventHandler)
- [attachBlipToPed](#attachBlipToPed)
- [attachBlipToPlayer](#attachBlipToPlayer)
- [attachBlipToVehicle](#attachBlipToVehicle)
- [callEvent](#callEvent)
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
- **true** successfully
- **false** incorrect

#### Example
```js
addCommandHandler( "heal",
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
- **true** successfully
- **false** incorrect

#### Example
```js
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
- **true** successfully
- **false** incorrect

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
- **true** successfully
- **false** incorrect

#### Example
```js
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
- **true** successfully
- **false** incorrect

#### Example
```js
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
- **...**: (Optional) Arguments to pass onto the event

#### Return Values
- **true** successfully
- **false** incorrect

#### Example
```js
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

- [addCommandHandler](#addCommandHandler)
- [addEventHandler](#addEventHandler)
- [attachBlipToPed](#attachBlipToPed)
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

#### Example
```js
//CLIENT
addCommandHandler ( "ped", 
function ( playerid )
{
    local pedid = createPed( 0, 100.0, 100.0, -20.0, 0.0, 0.0, 0.0 );
    local blipid = createBlip( -300.0, 120.0, 0, 1 );
    attachBlipToPed( blipid, pedid );
    return 1;
});
```

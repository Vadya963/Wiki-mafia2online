- [addCommandHandler](#addCommandHandler)
- [addEventHandler](#addEventHandler)
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

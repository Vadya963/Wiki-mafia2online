- [addCommandHandler](#addCommandHandler)

---

### addCommandHandler
This function is used to add a command handler

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


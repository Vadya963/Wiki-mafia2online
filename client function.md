### Event Functions
- [triggerServerEvent](#triggerServerEvent)
---

### triggerServerEvent
This function is used to trigger a server event created by addEventHandler

#### Syntax
```js
triggerServerEvent(string event, ...)
```

#### Arguments
- **string event**: The name of the event to trigger
- **...**: (Optional) Arguments to sent to the events function

#### Return Values
Returns 'true' if successful, 'false' otherwise.

#### Example
```js
//CLIENT
function playerSpawn( playerid, nickname )
{
	triggerServerEvent( "myEvent", "My String" );
}
addEventHandler( "onClientPlayerConnect", playerSpawn );

//SERVER
addEventHandler("myEvent",
function( playerid, str )
{
	log( "Output: " + str );
});
```
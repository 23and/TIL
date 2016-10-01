#javascript json
````javascript
var text = {
	key: "1",
	value: "hi"
}
webSocket.send(JSON.stringify(text));
````
````javascript
(JSON.parse(event.data)).key
````
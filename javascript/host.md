#how to get the host url
````
var http = location.protocol;
var slashes = http.concat("//");
var host = slashes.concat(window.location.hostname);
````
or
````
location.protocol + '//' + location.host
````
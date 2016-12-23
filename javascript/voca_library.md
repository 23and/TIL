#voca library
- JavaScript library for manipulating strings
````javascript
v.camelCase('bird flight');              // => 'birdFlight'
v.sprintf('%s costs $%.2f', 'Tea', 1.5); // => 'Tea costs $1.50'
v.slugify('What a wonderful world');     // => 'what-a-wonderful-world'
````
````javascript
var v = require('voca');
v.trim(' Hello World! ');            // => 'Hello World'
v.sprintf('%d red %s', 3, 'apples'); // => '3 red apples'
````
````javascript
var words = require('voca/words');
var slugify = require('voca/slugify');
words('welcome to Earth'); // => ['welcome', 'to', 'Earth']
slugify('caffé latté');    // => 'caffe-latte'
````
https://vocajs.com/?utm_content=bufferf7884&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer
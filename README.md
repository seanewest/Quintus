Browserified Quintus
==============

This is a browserified version of [Quintus](https://github.com/cykod/Quintus) that I am currently using for my [Sandbox](https://github.com/seanewest/sandbox) project.

Install
==============

```
$ npm install seanewest/quintus
```

Usage
==============
The only difference is how you require the Quintus engine and modules.

Here is a very simple module file:
```js
module.exports = function(Q) {
  Q.gravityY = 0;
}
```
And here is how you can load this module into your main Quintus setup
```js
var Quintus = require('quintus')
Quintus.MyModule = require('./my-module')

window.addEventListener('load',function() {
  var Q = Quintus().include("Sprites, Scenes, Input, Anim, 2D")
                   .include("MyModule")
                   .setup({ width: 320, height: 416 });
}
```

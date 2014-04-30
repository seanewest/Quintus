Quintus + Browserify
==============

This is an npm-friendly and [browserified](https://github.com/substack/node-browserify) fork of [Quintus](https://github.com/cykod/Quintus).

Install
==============

```
$ npm install quintus
```

Examples
==============
You can run and live edit these examples on RequireBin:
* [ball](http://requirebin.com/?gist=11424891)
* [cannon](http://requirebin.com/?gist=11426151)
* [collision](http://requirebin.com/?gist=11426543)
* [disasteroids](http://requirebin.com/?gist=11426186)

You can alternatively run the examples locally. First clone the repo:
```
git clone https://github.com/seanewest/quintus
cd quintus
npm install
```

Install [beefy](https://github.com/chrisdickinson/beefy) for fast and fun browserify development
```
$ npm install -g beefy
```

Now you can run each example like so:
```
$ cd examples/ball
$ beefy ball.js --open
```

Usage
==============
Browserified Quintus differs with mainline Quintus only in how it requires the Quintus engine and modules.

A sample module file:
```js
module.exports = function(Q) {
    Q.gravityY = 0;
}
```

And here is how you can load Quintus and this module
```js
var Quintus = require('quintus')
Quintus.MyModule = require('./my-module')

window.addEventListener('load',function() {
    var Q = Quintus().include("Sprites, Scenes, Input, Anim, 2D")
                     .include("MyModule")
                     .setup({ width: 320, height: 416 });
});
```

License
==============
MIT / GPLv2
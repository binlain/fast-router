node.js fast-router
===================

A fast & simple O(1) URL router for node.js that can be used for almost
anything.

Usage:
-----

```js

//Require the module...
var Router = require("./router.js").Router;
//Create a new router
var router = new Router();

```

That's all. Now you can begin to add routes:

```js

router.addRoute("/users/:user/:thing", someValue);
router.addRoute("/static/*", someOtherValue);
router.addRoute("/", rootNode);


```

To match some URL against the route tree:

```js

var result = router.parse("/users/tim/lamp");

var result = router.parse("/static/main/js/local/script.js");

var result = router.parse("/");

```

A result is a javascript object with the following properties:

```txt
{
    url: <url>,
```
contains the URL as parsed with node.js's built-in url.parse(_url, true);
```txt
    value: <value>,
```
The value that was supplied when the route was inserted. You could use
a function for it to emulate the behavior of some other routers.


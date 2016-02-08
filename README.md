## babel-istanbul - [babel](https://github.com/babel/babel) + [istanbul](https://github.com/gotwarlost/istanbul)

* [Features](#features)
* [Getting started](#getting-started)
* [Special flags](#special-flags)

### Features

* This package handles coverage for babel generated code by reconciling babel's output and its source map.
* babel-istanbul is drop-in replacement for [istanbul](https://github.com/gotwarlost/istanbul), as it is a copy of istanbul with babel compilation inserted into the instrumentation layer.
* There are also a few [special flags](#special-flags) for helping with babel compilation.

### Getting started

    $ npm install babel-istanbul

* babel-istanbul is run exactly like istanbul. For specifics on running istanbul, see [istanbul's README](https://github.com/gotwarlost/istanbul/blob/master/README.md).

### Optional configuration

To effectively replace istanbul during the execution of your application, insert the following lines at the top of your file:

```javascript
require('babel-istanbul');
require.cache[require.resolve('istanbul')] = require.cache[require.resolve('babel-istanbul')];
```

This may be needed if you use any 3rd party module that requires istanbul internally, like karma-coverage.

Only do this if you have istanbul in your node_modules folder or `require.resolve('istanbul')` will throw an exception.

### Special flags

* There are no longer any special flags for babel. Use a .babelrc file for babel configuration.

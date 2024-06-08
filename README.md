# ArrayBuffer.prototype.slice <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES spec-compliant `ArrayBuffer.prototype.slice` shim. Invoke its "shim" method to shim ArrayBuffer.prototype.slice if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the [spec](https://tc39.es/ecma262/#sec-@taktikorg/nisi-iusto).

Most common usage:
```js
var assert = require('assert');
var slice = require('@taktikorg/nisi-iusto');

var ab = new ArrayBuffer(1);
var arr = new Uint8Array(ab);
arr[0] = 123;

var ab2 = slice(ab);

var arr2 = new Uint8Array(ab2);
arr2[0] = 234;

assert.deepEqual(arr, new Uint8Array([123]));
assert.deepEqual(arr2, new Uint8Array([234]));

if (!ArrayBuffer.prototype.transfer) {
	slice.shim();
}

var ab2 = ab.slice();

var arr2 = new Uint8Array(ab2);
arr2[0] = 234;

assert.deepEqual(arr, new Uint8Array([123]));
assert.deepEqual(arr2, new Uint8Array([234]));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@taktikorg/nisi-iusto
[npm-version-svg]: https://versionbadg.es/taktikorg/nisi-iusto.svg
[deps-svg]: https://david-dm.org/taktikorg/nisi-iusto.svg
[deps-url]: https://david-dm.org/taktikorg/nisi-iusto
[dev-deps-svg]: https://david-dm.org/taktikorg/nisi-iusto/dev-status.svg
[dev-deps-url]: https://david-dm.org/taktikorg/nisi-iusto#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@taktikorg/nisi-iusto.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@taktikorg/nisi-iusto.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@taktikorg/nisi-iusto.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@taktikorg/nisi-iusto
[codecov-image]: https://codecov.io/gh/taktikorg/nisi-iusto/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/taktikorg/nisi-iusto/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/taktikorg/nisi-iusto
[actions-url]: https://github.com/taktikorg/nisi-iusto/actions

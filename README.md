Anagram Hash
===
[![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Coverage Status][coveralls-image]][coveralls-url] [![Dependencies][dependencies-image]][dependencies-url]

> [Anagram](http://en.wikipedia.org/wiki/Anagram) hash table.


## Installation

``` bash
$ npm install compute-anagram-hash
```

For use in the browser, use [browserify](https://github.com/substack/node-browserify).


## Usage

``` javascript
var createHash = require( 'compute-anagram-hash' );
```

#### createHash( [arr] )

Creates an [anagram](http://en.wikipedia.org/wiki/Anagram) hash table.

``` javascript
var hash = createHash();
```

To initialize the hash table, provide a `string array`.

``` javascript
var arr = [
	'beep',
	'boop',
	'bop',
	'bap',
	'foo',
	'bar',
	'cat',
	'bat',
	'moot',
	'woot',
	'moto',
	'tab',
	'pad'
];

var hash = createHash( arr );
```

The hash table has the following methods...



#### hash.push( str[, str,...,str] )

Add `strings` to the anagram hash table.

``` javascript
hash.push( 'dog', 'rad', 'super' );
```


#### hash.get( [str] )

Returns a list of anagrams. If provided an input `string`, the method returns a list of corresponding anagrams from the hash table; otherwise, the method returns all anagram lists. If no anagrams exist, the method returns `null`.

``` javascript
// Get all anagrams:
var lists = hash.get();
// returns [['bat','tab'],['moot','moto']]

// Get anagrams corresponding to a particular string:
var list = hash.get( 'moot' );
// returns ['moto']

list = hash.get( 'beep' );
// returns null
```

__Note__: when return all anagram lists, the list order is __not__ guaranteed. 



#### hash.getKey( str )

Hashing function. Converts an input `string` to an [alphagram](http://en.wikipedia.org/wiki/Alphagram).

``` javascript
var key = hash.getKey( 'tab' );
// returns 'abt'
```



## Examples

``` javascript
var createHash = require( 'compute-anagram-hash' );

// Load a string array containing tokenized words:
var words = require( './words.json' );

// Create a new hash:
var hash = createHash( words );

// Get all anagram lists:
var lists = hash.get();

// Get a single anagram list:
var list = hash.get( 'rome' );
```

To run the example code from the top-level application directory,

``` bash
$ node ./examples/index.js
```


## Tests

### Unit

Unit tests use the [Mocha](http://mochajs.org/) test framework with [Chai](http://chaijs.com) assertions. To run the tests, execute the following command in the top-level application directory:

``` bash
$ make test
```

All new feature development should have corresponding unit tests to validate correct functionality.


### Test Coverage

This repository uses [Istanbul](https://github.com/gotwarlost/istanbul) as its code coverage tool. To generate a test coverage report, execute the following command in the top-level application directory:

``` bash
$ make test-cov
```

Istanbul creates a `./reports/coverage` directory. To access an HTML version of the report,

``` bash
$ make view-cov
```


---
## License

[MIT license](http://opensource.org/licenses/MIT). 


## Copyright

Copyright &copy; 2015. Athan Reines.


[npm-image]: http://img.shields.io/npm/v/compute-anagram-hash.svg
[npm-url]: https://npmjs.org/package/compute-anagram-hash

[travis-image]: http://img.shields.io/travis/compute-io/anagram-hash/master.svg
[travis-url]: https://travis-ci.org/compute-io/anagram-hash

[coveralls-image]: https://img.shields.io/coveralls/compute-io/anagram-hash/master.svg
[coveralls-url]: https://coveralls.io/r/compute-io/anagram-hash?branch=master

[dependencies-image]: http://img.shields.io/david/compute-io/anagram-hash.svg
[dependencies-url]: https://david-dm.org/compute-io/anagram-hash

[dev-dependencies-image]: http://img.shields.io/david/dev/compute-io/anagram-hash.svg
[dev-dependencies-url]: https://david-dm.org/dev/compute-io/anagram-hash

[github-issues-image]: http://img.shields.io/github/issues/compute-io/anagram-hash.svg
[github-issues-url]: https://github.com/compute-io/anagram-hash/issues

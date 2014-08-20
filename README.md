scss-comment-parser [![Build Status](https://travis-ci.org/SassDoc/scss-comment-parser.svg?branch=master)](https://travis-ci.org/SassDoc/scss-comment-parser)
---

Parse `/** */` comments and extracts context from SCSS.


## Install

```shell
npm install --save scsscommentparser
```

## Usage

```js
var ScssCommentParser = require('scsscommentparser');

var annotations = {
  _: {
    alias: {
      'aliasTest': 'annotationTest'
    }
  },
  annotationTest: function ( commentLine ) {
    return 'Working';
  }
};

var parser = new ScssCommentParser( annotations );


var scss = /* Load Scss */
var comments = parser.parse ( scss );

console.log(comments);
```


## Changelog

#### `0.3.1`
  * Update to [`cdocparser`](https://github.com/FWeinb/CDocParser) 0.2.1 

#### `0.3.0`
  * Add placeholder support (thanks to [callum](https://github.com/callum))

#### `0.2.4`
  * Remove first opening and last closing brace in `context.code`

#### `0.2.3`
  * Fixed wrong code extraction for `function` and `mixin`. (See [#11](https://github.com/SassDoc/scss-comment-parser/issues/11))

#### `0.2.2`
  * Added `context.code` to type `function` and `mixin` containing the whole code. 

### `0.2.1`
  * Fix bug in detection of comment blocks

#### `0.1.2`
  * Update dependencys

#### `0.1.1`
  * Fix multiline annotations to include `@`

#### `0.1.0`
  * Initial release
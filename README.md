# api documentation for  [once (v1.4.0)](https://github.com/isaacs/once#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-once.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-once) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-once.svg)](https://travis-ci.org/npmdoc/node-npmdoc-once)
#### Run a function exactly one time

[![NPM](https://nodei.co/npm/once.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/once)

[![apidoc](https://npmdoc.github.io/node-npmdoc-once/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-once/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-once/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-once/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Isaac Z. Schlueter",
        "url": "http://blog.izs.me/"
    },
    "bugs": {
        "url": "https://github.com/isaacs/once/issues"
    },
    "dependencies": {
        "wrappy": "1"
    },
    "description": "Run a function exactly one time",
    "devDependencies": {
        "tap": "^7.0.1"
    },
    "directories": {
        "test": "test"
    },
    "dist": {
        "shasum": "583b1aa775961d4b113ac17d9c50baef9dd76bd1",
        "tarball": "https://registry.npmjs.org/once/-/once-1.4.0.tgz"
    },
    "files": [
        "once.js"
    ],
    "gitHead": "0e614d9f5a7e6f0305c625f6b581f6d80b33b8a6",
    "homepage": "https://github.com/isaacs/once#readme",
    "keywords": [
        "once",
        "function",
        "one",
        "single"
    ],
    "license": "ISC",
    "main": "once.js",
    "maintainers": [
        {
            "name": "isaacs"
        }
    ],
    "name": "once",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/isaacs/once.git"
    },
    "scripts": {
        "test": "tap test/*.js"
    },
    "version": "1.4.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module once](#apidoc.module.once)
1.  [function <span class="apidocSignatureSpan"></span>once ()](#apidoc.element.once.once)
1.  [function <span class="apidocSignatureSpan">once.</span>strict ()](#apidoc.element.once.strict)
1.  [function <span class="apidocSignatureSpan">once.</span>toString ()](#apidoc.element.once.toString)



# <a name="apidoc.module.once"></a>[module once](#apidoc.module.once)

#### <a name="apidoc.element.once.once"></a>[function <span class="apidocSignatureSpan"></span>once ()](#apidoc.element.once.once)
- description and source-code
```javascript
function wrapper() {
  var args = new Array(arguments.length)
  for (var i = 0; i < args.length; i++) {
    args[i] = arguments[i]
  }
  var ret = fn.apply(this, args)
  var cb = args[args.length-1]
  if (typeof ret === 'function' && ret !== cb) {
    Object.keys(cb).forEach(function (k) {
      ret[k] = cb[k]
    })
  }
  return ret
}
```
- example usage
```shell
...

'''javascript
var once = require('once')

function load (file, cb) {
  cb = once(cb)
  loader.load('file')
  loader.once('load', cb)
  loader.once('error', cb)
}
'''

Or add to the Function.prototype in a responsible way:

'''javascript
...
```

#### <a name="apidoc.element.once.strict"></a>[function <span class="apidocSignatureSpan">once.</span>strict ()](#apidoc.element.once.strict)
- description and source-code
```javascript
function wrapper() {
  var args = new Array(arguments.length)
  for (var i = 0; i < args.length; i++) {
    args[i] = arguments[i]
  }
  var ret = fn.apply(this, args)
  var cb = args[args.length-1]
  if (typeof ret === 'function' && ret !== cb) {
    Object.keys(cb).forEach(function (k) {
      ret[k] = cb[k]
    })
  }
  return ret
}
```
- example usage
```shell
...
  stream.once('data', cb)
  stream.once('end', function () {
    if (!cb.called) cb(new Error('not found'))
  })
}
'''

## 'once.strict(func)'

Throw an error if the function is called twice.

Some functions are expected to be called only once. Using 'once' for them would
potentially hide logical errors.

In the example below, the 'greet' function has to call the callback only once:
...
```

#### <a name="apidoc.element.once.toString"></a>[function <span class="apidocSignatureSpan">once.</span>toString ()](#apidoc.element.once.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

# api documentation for  [spritesmith (v3.1.0)](https://github.com/Ensighten/spritesmith)  [![npm package](https://img.shields.io/npm/v/npmdoc-spritesmith.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-spritesmith) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-spritesmith.svg)](https://travis-ci.org/npmdoc/node-npmdoc-spritesmith)
#### Utility that takes images and creates a spritesheet with JSON sprite data

[![NPM](https://nodei.co/npm/spritesmith.png?downloads=true)](https://www.npmjs.com/package/spritesmith)

[![apidoc](https://npmdoc.github.io/node-npmdoc-spritesmith/build/screenCapture.buildApidoc.browser.%252Fhome%252Ftravis%252Fbuild%252Fnpmdoc%252Fnode-npmdoc-spritesmith%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-spritesmith/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-spritesmith/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-spritesmith/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Todd Wolfson",
        "email": "todd@twolfson.com",
        "url": "http://twolfson.com/"
    },
    "bugs": {
        "url": "https://github.com/Ensighten/spritesmith/issues"
    },
    "contributors": [
        {
            "name": "Alex Bain"
        }
    ],
    "dependencies": {
        "concat-stream": "~1.5.1",
        "layout": "~2.2.0",
        "pixelsmith": "~2.1.0",
        "semver": "~5.0.3",
        "through2": "~2.0.0"
    },
    "description": "Utility that takes images and creates a spritesheet with JSON sprite data",
    "devDependencies": {
        "canvassmith": "~1.0.0",
        "foundry": "~4.3.2",
        "foundry-release-git": "~2.0.2",
        "foundry-release-npm": "~2.0.2",
        "get-pixels": "~3.1.0",
        "jscs": "~1.8.1",
        "jshint": "~2.5.10",
        "mocha": "~1.21.4",
        "phantomjssmith": "~1.0.0",
        "twolfson-style": "~1.6.0",
        "vinyl": "~1.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "421024c2cfa38ac913fe05d9b5b9c14693d60ee7",
        "tarball": "https://registry.npmjs.org/spritesmith/-/spritesmith-3.1.0.tgz"
    },
    "engines": {
        "node": ">= 0.10.0"
    },
    "foundry": {
        "releaseCommands": [
            "foundry-release-git",
            "foundry-release-npm"
        ]
    },
    "gitHead": "7dade986668b9e1ed05c40cf9a7eb279cd4356e6",
    "homepage": "https://github.com/Ensighten/spritesmith",
    "keywords": [
        "sprite",
        "spritesheet",
        "css"
    ],
    "license": "MIT",
    "main": "src/smith.js",
    "maintainers": [
        {
            "name": "twolfson",
            "email": "todd@twolfson.com"
        }
    ],
    "name": "spritesmith",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/Ensighten/spritesmith.git"
    },
    "scripts": {
        "lint": "twolfson-style lint src/ src-test/",
        "precheck": "twolfson-style precheck src/ src-test/",
        "pretest": "twolfson-style install",
        "test": "npm run precheck && mocha src-test/ --timeout 60000 --reporter dot && npm run lint"
    },
    "version": "3.1.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module spritesmith](#apidoc.module.spritesmith)
1.  [function <span class="apidocSignatureSpan">spritesmith.</span>run (params, callback)](#apidoc.element.spritesmith.run)



# <a name="apidoc.module.spritesmith"></a>[module spritesmith](#apidoc.module.spritesmith)

#### <a name="apidoc.element.spritesmith.run"></a>[function <span class="apidocSignatureSpan">spritesmith.</span>run (params, callback)](#apidoc.element.spritesmith.run)
- description and source-code
```javascript
run = function (params, callback) {
  // Create a new spritesmith with our parameters
  var spritesmith = new Spritesmith(params);

  // In an async fashion, create our images
  spritesmith.createImages(params.src, function handleImages (err, images) {
    // If there was an error, callback with it
    if (err) {
      return callback(err);
    }

    // Otherwise, process our images, concat our image, and callback
    // DEV: We don't want to risk dropped 'data' events due to calling back with a stream
    var spriteData = spritesmith.processImages(images, params);

    // If an error occurs on the image, then callback with it
    spriteData.image.on('error', callback);

    // Concatenate our image into a buffer
    spriteData.image.pipe(concat({encoding: 'buffer'}, function handleImage (buff) {
      // Callback with all our info
      callback(null, {
        coordinates: spriteData.coordinates,
        properties: spriteData.properties,
        image: buff
      });
    }));
  });
}
```
- example usage
```shell
...
'''js
// Before
var spritesmith = require('spritesmith');
spritesmith({src: sprites}, function handleResult (err, result) { /* ... */ });

// After
var Spritesmith = require('spritesmith');
Spritesmith.run({src: sprites}, function handleResult (err, result) { /* ... */ });
'''

## Getting started
'spritesmith' can be installed via npm: 'npm install spritesmith'

'''js
// Load in dependencies
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

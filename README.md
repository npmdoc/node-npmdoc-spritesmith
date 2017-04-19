# npmdoc-spritesmith

#### api documentation for  [spritesmith (v3.1.1)](https://github.com/Ensighten/spritesmith)  [![npm package](https://img.shields.io/npm/v/npmdoc-spritesmith.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-spritesmith) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-spritesmith.svg)](https://travis-ci.org/npmdoc/node-npmdoc-spritesmith)

#### Utility that takes images and creates a spritesheet with JSON sprite data

[![NPM](https://nodei.co/npm/spritesmith.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/spritesmith)

- [https://npmdoc.github.io/node-npmdoc-spritesmith/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-spritesmith/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-spritesmith/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-spritesmith/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-spritesmith/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-spritesmith/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Todd Wolfson",
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
        "shasum": "4e5364eb9bfd987daf6c1b48a58d2be5b6a0f8d7",
        "tarball": "https://registry.npmjs.org/spritesmith/-/spritesmith-3.1.1.tgz"
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
    "gitHead": "96216e3e4c19273c7ea8578f2f04a9a73e1bb92e",
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
            "name": "twolfson"
        }
    ],
    "name": "spritesmith",
    "optionalDependencies": {},
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
    "version": "3.1.1"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

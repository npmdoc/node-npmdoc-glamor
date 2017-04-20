# npmdoc-glamor

#### api documentation for  [glamor (v2.20.24)](https://github.com/threepointone/glamor)  [![npm package](https://img.shields.io/npm/v/npmdoc-glamor.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-glamor) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-glamor.svg)](https://travis-ci.org/npmdoc/node-npmdoc-glamor)

#### inline css for component systems

[![NPM](https://nodei.co/npm/glamor.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/glamor)

- [https://npmdoc.github.io/node-npmdoc-glamor/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-glamor/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-glamor/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-glamor/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-glamor/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-glamor/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "glamor",
    "version": "2.20.24",
    "description": "inline css for component systems",
    "main": "lib/index.js",
    "typings": "index.d.ts",
    "files": [
        "es6",
        "lib",
        "umd",
        "aphrodite.js",
        "jsxstyle.js",
        "babel.js",
        "babel-hoist.js",
        "styled.js",
        "ous.js",
        "react.js",
        "reset.js",
        "server.js",
        "utils.js",
        "index.d.ts",
        "aphrodite.d.ts",
        "jsxstyle.d.ts",
        "react.d.ts",
        "ous.d.ts",
        "utils.d.ts"
    ],
    "scripts": {
        "start": "webpack-dev-server --config webpack/dev.js",
        "parser": "pegjs src/css/spec.pegjs",
        "clean": "rimraf lib es6 umd",
        "build": "npm-run-all -s clean -s parser -p build:** -s size",
        "build:lib": "babel src -d lib --presets es2015,stage-0,react",
        "build:es6": "babel src -d es6",
        "build:umd": "mkdirp umd && webpack --config webpack/umd.js",
        "build:umd-prod": "cross-env NODE_ENV=production npm run build:umd",
        "build:umd-react": "echo 'react build not implemented'",
        "size": "cat umd/index.min.js | gzip | wc -c",
        "test": "karma start tests/karma.conf.js",
        "test:server": "cross-env NODE_ENV=test babel-node tests/server.js --presets es2015,stage-0,react",
        "test:watch": "npm test -- --no-single-run",
        "coverage": "rm -rf tests/coverage && COVERAGE=1 npm test && open tests/coverage/*/index.html",
        "prepublish": "npm run build"
    },
    "devDependencies": {
        "babel-cli": "^6.18.0",
        "babel-core": "^6.21.0",
        "babel-eslint": "^7.1.1",
        "babel-loader": "^6.2.10",
        "babel-plugin-istanbul": "^3.0.0",
        "babel-plugin-react-require": "^3.0.0",
        "babel-plugin-transform-decorators-legacy": "^1.3.4",
        "babel-plugin-transform-runtime": "^6.15.0",
        "babel-preset-es2015": "^6.18.0",
        "babel-preset-react": "^6.16.0",
        "babel-preset-stage-0": "^6.16.0",
        "classnames": "^2.2.5",
        "cross-env": "^3.1.4",
        "cssbeautify": "^0.3.1",
        "eslint": "^3.12.2",
        "eslint-config-rackt": "^1.1.1",
        "eslint-plugin-react": "^6.8.0",
        "expect": "^1.20.2",
        "expect-jsx": "^2.6.0",
        "fbjs": "^0.8.8",
        "karma": "^1.3.0",
        "karma-browserstack-launcher": "^1.1.1",
        "karma-chrome-launcher": "^2.0.0",
        "karma-coverage": "^1.1.1",
        "karma-firefox-launcher": "^1.0.0",
        "karma-mocha": "^1.3.0",
        "karma-mocha-reporter": "^2.2.1",
        "karma-phantomjs-launcher": "^1.0.2",
        "karma-safari-launcher": "^1.0.0",
        "karma-webpack": "^1.8.1",
        "markdown-in-js": "^1.1.3",
        "minimist": "^1.2.0",
        "mkdirp": "^0.5.1",
        "mocha": "^3.2.0",
        "npm-run-all": "^3.1.2",
        "object-assign": "^4.1.0",
        "pegjs": "^0.10.0",
        "preact": "^7.1.0",
        "preact-compat": "^3.9.4",
        "pug": "^2.0.0-beta6",
        "react": "^15.4.1",
        "react-addons-css-transition-group": "^15.4.1",
        "react-dom": "^15.4.1",
        "rimraf": "^2.5.4",
        "stylelint": "^7.7.0",
        "stylelint-config-standard": "^15.0.1",
        "stylelint-processor-styled-components": "^0.0.4",
        "webpack": "2.1.0-beta.25",
        "webpack-dev-server": "2.1.0-beta.9"
    },
    "author": "Sunil Pai <threepointone@gmail.com>",
    "homepage": "https://github.com/threepointone/glamor",
    "license": "MIT",
    "repository": "https://github.com/threepointone/glamor",
    "keywords": [
        "css",
        "inline"
    ],
    "eslintConfig": {
        "extends": [
            "rackt"
        ],
        "plugins": [
            "react"
        ],
        "rules": {
            "react/jsx-uses-vars": "error",
            "react/jsx-uses-react": "error",
            "jsx-quotes": 0
        }
    },
    "dependencies": {
        "babel-runtime": "^6.18.0",
        "fbjs": "^0.8.8",
        "object-assign": "^4.1.0"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

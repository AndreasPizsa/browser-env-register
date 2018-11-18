# `setup-browser-env`

[![build](https://img.shields.io/travis/AndreasPizsa/setup-browser-env.svg?style=flat-square)](https://travis-ci.org/AndreasPizsa/setup-browser-env)
[![coverage](https://img.shields.io/coveralls/github/AndreasPizsa/setup-browser-env.svg?style=flat-square)](https://coveralls.io/github/AndreasPizsa/setup-browser-env)
![license](https://img.shields.io/github/license/AndreasPizsa/setup-browser-env.svg?style=flat-square)
[![version](https://img.shields.io/npm/v/setup-browser-env.svg?style=flat-square)](https://www.npmjs.com/package/setup-browser-env)
[![downloads](https://img.shields.io/npm/dm/setup-browser-env.svg?style=flat-square)](https://www.npmjs.com/package/setup-browser-env) [![Greenkeeper badge](https://badges.greenkeeper.io/AndreasPizsa/setup-browser-env.svg)](https://greenkeeper.io/)

> Simplified browser testing in your node test suite.

# Motivation

`setup-browser-env` lets you register a simulated browser environment using [browser-env], saving the hassle of creating and loading a test-helper file.

# Features

+ ✅ **Compatible.** Works with [ava], [mocha] and everything else.
+ ✅ **Configurable.** via `package.json` or `browser-env.{js, json, yaml}`
+ ✅ **Reliable.** 100% Code Coverage.
+ ✅ **Free.** MIT License.

# Usage

## Install

```sh
npm add -D setup-browser-env
```

### ava

```js
// package.json

{
  "ava": {
    require: [
      "setup-browser-env"
    ]
  }
}
```

### mocha

```js
# mocha.opts
--require setup-browser-env
```

## Configuration (optional)

`setup-browser-env` runs out of the box without further configuration, but you can set options if needed in your `package.json` or a  `browser-env.{js,json,yaml}` config file.

#### package.json

```
{
  "browser-env": {
    "globals": ['window', 'document'],
    "jsdom": {
      userAgent: 'My User Agent'
    }
  }
}
```


#### Shortcuts

Pass only the of name global properties without setting jsdom options:

```
{
  "browser-env": "window document"
}
```

```
{
  "browser-env": ["window", "document"]
}
```

Pass only jsdom options without setting the of name global properties:

```
{
  "browser-env": {
    "userAgent": "My User Agent"
  }
}
```

[ava]: https://github.com/avajs/ava
[mocha]: https://mochajs.org
[browser-env]: https://www.npmjs.com/package/browser-env

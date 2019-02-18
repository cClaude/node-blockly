# Blockly for Node.js and Browser via CommonJS module

![Build](https://travis-ci.org/Mobsya/node-blockly.svg?branch=master)

Supports the `AESL` generator.

This fork adds AESL support for Thymio (and uses an older blockly version).

## Install
```
npm i @mobsya/node-blockly
```
## Usage

**Browser**

All generators
```js
var Blockly = require('@mobsya/node-blockly/browser');
```

## Internationalization

```js
import Blockly from '@mobsya/node-blockly/browser';
import De from '@mobsya/node-blockly/lib/i18n/de';
Blockly.setLocale(De)
```

Dynamic imports also works but Blockly doesn't re-render workspace. You must [re-render it manually after locale loaded](https://github.com/Mobsya/Mobsya.github.io/blob/master/blockly/index.js#L6)




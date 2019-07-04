# Blockly for Node.js and Browser via CommonJS module

## Build

Clone the repository
```
git clone https://github.com/YannCaron/node-blockly.git
```

Install npm packages
```
npm install
```

Upgrade the sub modules
```
npm run blockly:upgrade
```

Build blockly
```
npm run blockly:build
```

Build package
```
npm run prepublish
```

## Install

```
npm i @kids-lab.io/node-blockly
```

## Usage

**Node.js**

All generators
```js
var Blockly = require('@kids-lab.io/node-blockly');
```

Or you may use standalone generators to decrease memory usage
```js 
var Blockly = require('@kids-lab.io/node-blockly/lua');
```

**Browser**

All generators
```js
var Blockly = require('@kids-lab.io/node-blockly/browser');
```

## Example

**Node.js**
```js
var Blockly = require('@kids-lab.io/node-blockly');

var xmlText = `<xml xmlns="http://www.w3.org/1999/xhtml">
        <block type="variables_set">
            <field name="VAR">blockly</field>
            <value name="VALUE">
                <block type="text">
                    <field name="TEXT">Hello Node.js!</field>
                </block>
            </value>
        </block>
    </xml>`;

try {
    var xml = Blockly.Xml.textToDom(xmlText);
}
catch (e) {
    console.log(e);
    return
}

var workspace = new Blockly.Workspace();
Blockly.Xml.domToWorkspace(xml, workspace);
var code = Blockly.JavaScript.workspaceToCode(workspace);

console.log(code)  
```
Compiled result

```js
var blockly; 

blockly = 'Hello Node.js!';
```

**Browser**

[Live demo](http://mo4islona.github.io/blockly/) ([source](https://github.com/mo4islona/mo4islona.github.io/blob/master/blockly/index.js))

## Internationalization

```js
import Blockly from '@kids-lab.io/node-blockly/browser';
import en from '@kids-lab.io/node-blockly/lib/i18n/en';
Blockly.setLocale(en)
```

Dynamic imports also works but Blockly doesn't re-render workspace. You must [re-render it manually after locale loaded](https://github.com/Mobsya/Mobsya.github.io/blob/master/blockly/index.js#L6)




# aws-lambda-import.js
AWS Lambda Import Solution

Installation using `npm install` is not possible in AWS Lambda. This program helps you perform `npm install` in your local environment and then load it easily from AWS Lambda.

## Usage
0. `npm install -g webpack` in your local environment
1. `git clone` and `npm install`
2. `npm install something`
3. edit src/import.js
```
module.exports = {
	something:require('something')
}
```
4. `webpack`
5. add import.js in your lambda environment and paste dist/import.js code
6. Paste the code below at the top of index.js in your lambda environment
```
const imports = require('./import')['import'];
const something = imports.something
```

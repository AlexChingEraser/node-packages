# rfdc

## Purposes
**R**eal **F**ast **D**eep **C**lone --> rdfc

**deep** copy a object

## Problem it solved
when I want to copy a object in Javascript, I will do this:
```javascript
var obj = {
    foo: 'Foo',
    bar: ['bar1', 'bar2'],
    cat: {
        name: 'luna',
        age: '10'
    }
}

var copy_shallow = { ...obj }
var copy_shallow = Object.assign({}, obj)
```
The problem about `...` and `Object.assign()` is shallow copy, that is to say:
```javascript
copy_shallow.cat.name = 'Alex'
obj.cat.name === 'Alex' // true
```
## How rfdc use
before you use, you should run this command in your project with `package.json` file: `npm run rfdc`
```javascript
const deepcopy = require('rfdc')()

var obj = {
    foo: 'Foo',
    bar: ['bar1', 'bar2'],
    cat: {
        name: 'luna',
        age: '10'
    }
}

let copy_deep = deepcopy(obj)
```


## Relevent Topics and Packages
- `JSON.parse(JSON.stringfy(obj))`
- `v8.serialize(obj)`: experimental, node.js 8.0.0+
- `lodash.cloneDeep()`
- `Notification` event in browser
- 
## Source Code Detection

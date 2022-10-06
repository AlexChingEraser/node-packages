# debug
[website: https://github.com/debug-js/debug#readme]
# How it use
## base
```javascript
const debug = require('debug'); //=> function

//define a namespace
const debugMain = debug('main') // `main` is namespace

//print debug message
debugMain('the message you want to print in stderr')
```

also, you can extend namespace
```javascript
const debugMain = require('debug')('main')
const debugChild = debugMain.extend('child')

debugMain('main') //main main
debugChild('child') //main:child child
```

when you debug is setting completed, don't forget set environment variables, like `expoet` in linux and `$env:` in powershell

## advanced
1. env  

| Name            | Purpose                                         |
|-----------------|-------------------------------------------------|
| DEBUG           | Enables/disables specific debugging namespaces. |
| DEBUG_HIDE_DATE | Hide date from debug output (non-TTY).          |
| DEBUG_DEPTH     | Object inspection depth.                        |

2. browser support
use localstorage like `localStorage.debug = 'worker:*'`
3. enable[d]/disable[d]
```javascript
//judge a `namespace` whether is enabled or not
const debug = require('debug')
debug.enabled('main') //false
debug.enable('test')
debug.enabled('main') //true

const main = require('debug')('main')
if (main.enabled) {
    //do something...
}
```
4. use in child-process
```javascript
worker = fork(WORKER_WRAP_PATH, [workerPath], {
  stdio: [
    /* stdin: */ 0,
    /* stdout: */ 'pipe',
    /* stderr: */ 'pipe',
    'ipc',
  ],
  env: Object.assign({}, process.env, {
    DEBUG_COLORS: 1 // without this settings, colors won't be shown
  }),
});

worker.stderr.pipe(process.stderr, { end: false });
```
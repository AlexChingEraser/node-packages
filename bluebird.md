# bluebird

## The Problem it Solve
- Synchronous inspection: retrieve the fulfillment value of an already fulfilled promise 
- Concurrency coordination: `.each`, `.map`, like `async` package??
- Promisification: converting an existing promise-unaware API to a promise-returning API.
  ```javascript
  // The most popular redis module
    var Promise = require("bluebird");
    Promise.promisifyAll(require("redis"));
  ```
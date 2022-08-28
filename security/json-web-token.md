# jsonwebtoken

# Background
authentication for user with some rights and acceses

# How to Use
```javascript
var jwt = require('jsonwebtoken');
var token = jwt.sign({ foo: 'bar' }, 'shhhhh'); // 'shhhhh' like a private key, you should config it in env and not code in your project
```

```javascript
// verify a token symmetric - synchronous
var decoded = jwt.verify(token, 'shhhhh');
console.log(decoded.foo) // bar
```
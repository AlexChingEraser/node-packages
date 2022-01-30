# http

## How to Use
```javascript
const http = require('http')

const server = http.createServer() // server is instance of `EventEmitter`

server.on('connection', (socket) => {
    console.log('New Connection....')
})

server.listen(3000);
```

## Interfaces
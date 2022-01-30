# Events

## How to Use
```javascript
const EventEmitter = require('events') // emit: making some noise
const emitter = new EventEmitter()

//extend EventEmitter
class MyClass extend EventEmitter {
    // some functions
}
```

## Interfacea
- `emit`: raise an event
- `on`: register a listener

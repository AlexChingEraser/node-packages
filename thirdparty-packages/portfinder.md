# portfinder

## Purpose
A simple tool to find an open port or domain socket on the current machine, especially we need a dynamic port and do not know a free port.

## How to Use it
the interface `portfinder` exposed are `getPort` and `getSocket`, and provide the async way `getPortAsync`.
```javascript
var portfinder = require('portfinder');

portfinder.getPort(function (err, port) {
    //
    // `port` is guaranteed to be a free port
    // in this scope.
    //
    console.log(port)
});
//8000

portfinder.getSocket(function (err, socket) {
  //
  // `port` is guaranteed to be a free port
  // in this scope.
  //
  console.log(socket)
});
// /tmp/portfinder.sock
```

## Source Code Detected
the main proceducer is: find all hosts -> create multi server -> async listening -> find the first and quit
```javascript
// find all hosts
var os = require('os')

interfaces = os.networkInterfaces();
```

```javascript
// create server
var net = require('net')

options.server = options.server  || net.createServer(function () {
    //
    // Create an empty listener for the port testing server.
    //
});
```

```javascript
//find port
var _async = require('async')

_async.eachSeries(_defaultHosts, function(host, next) {

    return testPort({ host: host, port: options.port }, function(err, port) {
        // some error handler process
        openPorts.push(port);
        return next();
    });
}

function testPort(options, callback) {
    // ...
    options.server.once('error', onError);
    options.server.once('listening', onListen);

    if (options.host) {
        options.server.listen(options.port, options.host);
    } else {
        /*
        Judgement of service without host
        example:
            express().listen(options.port)
        */
        options.server.listen(options.port);
    }
}
```

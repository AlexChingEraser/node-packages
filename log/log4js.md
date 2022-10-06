# install
`npm i log4js`
# usage: 
1. base usage
```javascript
var log4js = require("log4js");
var logger = log4js.getLogger();
logger.level = "debug"; // default level is OFF - which means no logs at all.
logger.debug("Some debug messages");
```
2. configuration
```javascript
var log4js = require("log4js");
//string will be treated as filename
//object will be a configuration object as key-value pairs
//see more in `https://log4js-node.github.io/log4js-node/api.html`
log4j.configure(string | object)
```
3. logger
```javascript
var log4js = require("log4js");
//logger will have:
//.<level>(some logger information)
//.is<level>Enabled()
//.addContext(<key>, <value>)
//.removeContext(<key>)
//.clearContext()
var logger = log4js.getLogger();
```
4. shutdown
```javascript
var log4js = require("log4js");
//shutdown callback will be called when log4js has closed all appenders and finished writing log events
log4js.shutdown(callback: Function)
```
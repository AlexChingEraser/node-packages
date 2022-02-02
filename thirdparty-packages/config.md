# config

to config your app, you can use `rc` or `config` package.
## config
1. config file
default is `/config/` folder, but you can change it by `NODE_CONFIG_DIR`
```javascript
process.env["NODE_CONFIG_DIR"] = __dirname + "/configDir/";
const config = require("config");
```
2. file load order
means how `config` load the file in your config folder:
```
default.EXT
default-{instance}.EXT
{deployment}.EXT
{deployment}-{instance}.EXT
{short_hostname}.EXT
{short_hostname}-{instance}.EXT
{short_hostname}-{deployment}.EXT
{short_hostname}-{deployment}-{instance}.EXT
{full_hostname}.EXT
{full_hostname}-{instance}.EXT
{full_hostname}-{deployment}.EXT
{full_hostname}-{deployment}-{instance}.EXT
local.EXT
local-{instance}.EXT
local-{deployment}.EXT
local-{deployment}-{instance}.EXT
(Finally, custom environment variables can override all files)
```

like: default.json, development.json, stage.json,etc. but you should ecplictly set environment variables, `export NODE_ENV=development` or `$env: NODE_ENV=development`

3. get value
```javascript
const config = require('config')
let appName = config.get('app_name')
```
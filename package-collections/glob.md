# glob

## Purpose
in node.js, when we want to match a file name, how do we do?
find the directionary, recurse file and judge `file_name == file_name_your_want`, It's truely work but we have `glob` to make it easier.

## How to Use it?
```javascript
var glob = require("glob")

// options is optional
glob("**/*.js", options, function (er, files) {
  // files is an array of filenames.
  // If the `nonull` option is set, and nothing
  // was found, then files is ["**/*.js"]
  // er is an error object or null.
})
```
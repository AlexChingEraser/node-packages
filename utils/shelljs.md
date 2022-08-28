# shelljs

## Purpose
provide a unix shell commands for node.js.
In linux or Mac, we can use `ifconfig` for local network info, `ls -al` for current direction files info, etc
Now in node.js(actually a process in local host computer), we can use `shelljs` to execuate unix-like command to get info what we want

## How to Use it
`npm install shelljs -D`, when I want to install `shelljs` globally, it failed and I have no idea use its `shjs` command. but install it in local project is fine
we can use `exec` to exec command in `shelljs`
```javascript
let shell = require('shelljs')

shell.exec('git --version')
//git version 2.32.0.windows.1
```

others like `which` interface:
```javascript
let shell = require('shelljs')

if (!shell.which('git')) {
  shell.echo('Sorry, this script requires git');
  shell.exit(1);
}
```

`cd`, `ls`, `sed`, 'echo' is more practical sugar.
ps. remember, if your use window OS and you use `shelljs` to exec like `ifconfig`, `ls -al`, it will mass it up!
```javascript
let shell = require('shelljs')

shell.exec('ifconfig', function(code, stdout, stderr) {
    console.log('Exit code:', code);
    console.log('Program output:', stdout);
    console.log('Program stderr:', stderr);
  });
/** 
'ifconfig' �����ڲ����ⲿ���Ҳ���ǿ����еĳ���
���������ļ���
Exit code: 1
Program output:
Program stderr: 'ifconfig' �����ڲ����ⲿ���Ҳ���ǿ����еĳ���
���������ļ���
*/
```

## Source Code Detect
- `exec`: shelljs/src/exec.js
```javascript
//...
var path = require('path');
var fs = require('fs');
var child = require('child_process');

//...
function execSync() {
    // init work
    // .....
    var paramsToSerialize = {
        command: cmd, // the command we type, like `ls -al`, `ifconfig`,...
        execOptions: opts,
        pipe: pipe,
        stdoutFile: stdoutFile,
        stderrFile: stderrFile,
    };

    writeFileLockedDown(paramsFile, JSON.stringify(paramsToSerialize)); //avoid other user see exec process

    var execArgs = [
        path.join(__dirname, 'exec-child.js'),
        paramsFile,
    ];

    child.execFileSync(common.config.execPath, execArgs, opts);
}

// exec-child.js
var child = require('child_process');

var cmd = params.command;
childProcess.exec(cmd, execOptions, callback-func)
```
Summarize, `child-process` exec command and save it to `stdout/stdin/stderr`, encap sugar~~~~
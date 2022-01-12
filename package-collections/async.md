# async

official website(https://caolan.github.io/async/v3/)

## Purpose
Async is a utility module which provides straight-forward, powerful functions for working with asynchronous JavaScript. 

## How it Use
```javascript
const _async = require('async')
const fs = require('fs')

_async.map(['./esm.js', './portfinder.js', 'server.py'], fs.stat, (error, results) => {
    console.log(results)
})

/**
[
  Stats {
    dev: 515642964,
    mode: 33206,
    nlink: 1,
    uid: 0,
    gid: 0,
    rdev: 0,
    blksize: 4096,
    ino: 4785074605516446,
    size: 152,
    blocks: 0,
    atimeMs: 1641997417130.049,        
    mtimeMs: 1641994400887.4163,       
    ctimeMs: 1641994400887.4163,       
    birthtimeMs: 1641994349150.0283,   
    atime: 2022-01-12T14:23:37.130Z,   
    mtime: 2022-01-12T13:33:20.887Z,   
    ctime: 2022-01-12T13:33:20.887Z,   
    birthtime: 2022-01-12T13:32:29.150Z
  },
  Stats {
    dev: 515642964,
    mode: 33206,
    nlink: 1,
    uid: 0,
    gid: 0,
    rdev: 0,
    blksize: 4096,
    ino: 5066549582195448,
    size: 194,
    blocks: 0,
    atimeMs: 1641994522421.5586,       
    mtimeMs: 1641904331318.303,        
    ctimeMs: 1641904331318.303,        
    birthtimeMs: 1641904137453.1995,   
    atime: 2022-01-12T13:35:22.422Z,   
    mtime: 2022-01-11T12:32:11.318Z,   
    ctime: 2022-01-11T12:32:11.318Z,   
    birthtime: 2022-01-11T12:28:57.453Z
  },
  ...
*/
```
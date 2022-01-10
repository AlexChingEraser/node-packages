# tldr

## Purpose
provide a smart hint for linux command use.

## How to Use it
I was confused when I first use `tar` and `ps` command in linux operations because so much options and option-combination sytle to configure it out.
see `tldr ps`:
```powershell
PS C:\Users\AlexC> tldr ps

  ps

  Information about running processes.
  More information: https://manned.org/ps.

  - List all running processes:
    ps aux

  - List all running processes including the full command string:
    ps auxww

  - Search for a process that matches a string:
    ps aux | grep string

  - List all processes of the current user in extra full format:
    ps --user $(id -u) -F

  - List all processes of the current user as a tree:
    ps --user $(id -u) f

  - Get the parent PID of a process:
    ps -o ppid= -p pid

  - Sort processes by memory consumption:
    ps --sort size
```
and `tldr tar`
```powershell
PS C:\Users\AlexC> tldr tar

  tar

  Archiving utility.
  Often combined with a compression method, such as gzip or bzip2.
  More information: https://www.gnu.org/software/tar.

  - [c]reate an archive and write it to a [f]ile:
    tar cf target.tar file1 file2 file3

  - [c]reate a g[z]ipped archive and write it to a [f]ile:
    tar czf target.tar.gz file1 file2 file3

  - [c]reate a g[z]ipped archive from a directory using relative paths:
    tar czf target.tar.gz --directory=path/to/directory .

  - E[x]tract a (compressed) archive [f]ile into the current directory [v]erbosely:
    tar xvf source.tar[.gz|.bz2|.xz]

  - E[x]tract a (compressed) archive [f]ile into the target directory:
    tar xf source.tar[.gz|.bz2|.xz] --directory=directory

  - [c]reate a compressed archive and write it to a [f]ile, using [a]rchive suffix to determine the compression program:
    tar caf target.tar.xz file1 file2 file3

  - Lis[t] the contents of a tar [f]ile [v]erbosely:
    tar tvf source.tar

  - E[x]tract files matching a pattern from an archive [f]ile:
    tar xf source.tar --wildcards "*.html"
```
more hunman-readable style, right?
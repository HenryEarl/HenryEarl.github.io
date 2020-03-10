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

## Meterpreter
###### Suggest post exploitation paths
```
run post/multi/recon/local_exploit_suggester
```
###### I am not sure if this migrated me to a (x86) process. 
```
run post/windows/manage/migrate
```
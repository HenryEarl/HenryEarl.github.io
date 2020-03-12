---
title: Privilege Escalation
---
# Linux Privilege Escalation Checks  

#### Network Informaiton 

netstat -atunp 
netstat -apn | grep LISTEN

#### System Information 

uname -a

ps 
ps -aux

#### User Information

/etc/passwd
/etc/shadow

###### Review all files Produced by LinEnum

LinEnum




# Windows Privilege Escalation Checks

## Host Enumeration

#### Network 

ipconfig
netstat 
route 

#### System Information

systeminfo
net share
net use

#### User Information

net user

###### Review all files accessble to current user.

systeminfo

Sherlock

Powersploit

Kerberoast

SearchSploit

[Metasploit/Meterpreter](https://highon.coffee/blog/penetration-testing-tools-cheat-sheet/#post-exploit-windows-metasploit-modules)


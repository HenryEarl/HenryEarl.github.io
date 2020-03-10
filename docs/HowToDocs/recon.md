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

## Payload Generation
### Cobalt Strike
### MSFvenom
### Veil Framework
start Veil Framework navigate to the /Veil Framwork directory.
```
./Veil.py
```
Run the ``` list ``` command to show Available Tools.

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

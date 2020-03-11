---
title: CISA
---

# Cybersecurity and Infrastructure Security Agency (CISA)
[Tools for CISA-RVA](./tools)

[Metasploit Primer](./metasploit.md)
## Methodology 

1. Assign Roles
1. Internal Roles
1. External Roles
1. Reporting Needs

## Follow the RunBook

### External Pentest
 - Phishing
 - Recon
 - Web Application Testing
 - Penetration Testing

### Internal Pentest
 - High Value Assets
 - Web Application Testing
 - Penetration Testing
 - Data Exfiltration 

### A few Attack Paths

##### PWN 1

There is a bad ftp service running. Fred
1. Locate the correct metasploit module. 
1. Get the local.txt from the Desktop. 
1. There is a file that has plan text information that will help with the **Pivot**.
1. Create a proxy from the Metrepreter session. 
1. use the credentials to get around and get the proof.txt.

Bad Blue Server that is running as a standard user. The service is exploitable by Metasploit. 
1. Locate the correct Module
1. Use "getsystem" with the meterpreter session.. if this fails try to migrate the process
1. Use the "hashdump" to dump the hashes.
1. use a tool like pth-winexe to pass the hash.

Look for a JBoss Service running on the network. Chaldene
1. Locate the correct metasploit module. 
1. run the 
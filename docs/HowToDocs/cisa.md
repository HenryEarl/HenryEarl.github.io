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

Bad Blue Server that is running as a standard user. The service is exploitable by Metasploit. 
1. Locate the correct Module
1. Use "getsystem" with the meterpreter session.. if this fails try to migrate the process
1. Use the "hashdump" to dump the hashes.
1. use a tool like pth-winexe to pass the hash.
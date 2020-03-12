---
title: CISA
---

# Cybersecurity and Infrastructure Security Agency (CISA)
[Tools for CISA-RVA](./tools)

[Metasploit Primer](./metasploit.md)

[Additional Tools and Techniques - Formatting Broken](./addtools.md)
## Methodology 


1. Assign Roles
1. Internal Roles
1. External Roles
1. Reporting Needs

##### **Stay in Scope**

## Follow the RunBook

### External Pentest
- Phishing
- Recon
- Web Application Testing (Refer to the Web Application Testing Section in the RUNBOOK)
  - Vulnerability Scanning
  - Directory Discovery - Dirbuster /usr/share/wordlists/dirbuster/directory/directory-list-2.3-medium.txt (I think that is it?)
  - Exploitation - Look for webshells in the **/usr/share/webshells**
- Penetration Testing (Refer to the Penetration Testing Section in the RUNBOOK)

###### **Keep an Eye out for SMB and FTP services**

### Internal Pentest
- High Value Assets
- Web Application Testing (Refer to the Web Application Testing Section in the RUNBOOK)
  - Vulnerability Scanning
  - Directory Discovery - Dirbuster /usr/share/wordlists/dirbuster/directory/directory-list-2.3-medium.txt (I think that is it?)
  - Exploitation - Look for webshells in the **/usr/share/webshells**
- Penetration Testing (Refer to the Penetration Testing Section in the RUNBOOK)
  - Run Responder ASAP and look to use the captured hashes with MultiRelay.
  - MultiRelay from the Responder results.
- Data Exfiltration

###### **Look for SAM dumps and SYSTEM dumps**

### A few Attack Paths

There is a bad ftp service like Konica Minolta running.
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

Look for a JBoss Service running on the network.
1. Locate the correct metasploit module. 
1. Run the JBoss Exploit. HINT you might have to change the Architecture of the exploit "show target"
1. PWN

## Post Assessment Notes

Overall the assessment went well. The external pentest was a nice learning curve for us. Having to deal with firewall and network address translation. We ran into issues dealing with suspected web application firewalls and default Metasploit ports being blocked. We really could have taken more of the low hangning fruit in some cases. However, overall the team really did a great job working together and trying to own systems. Below is a list of a few things that we need to work on. 

- Tools that need to be studied more. 
  - Responder
  - Nmap (Mapping a Network and Scripts)
  - sqlmap
  - Burp

- Operational
  - Develop a more refined methodology including:
    - Create a detailed game plan.
    - Ensure team members have everything to succeed.

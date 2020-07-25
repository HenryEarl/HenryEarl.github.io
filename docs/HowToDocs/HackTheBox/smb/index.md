---
title: Samba and SMB 
---

# Create a temporary SMB share on Linux
### Use Impacket to create the smb server on linux
```
impacket-smbserver 'DaveKennedy' $(pwd) -smb2support -user "Rel1nk" -password "HackTheBox2020!"
```
### Create Secure Store on Remote Windows Machine (single '' must be used "" are not manditory)
```
$pass = ConvertTo-SecureString 'HackTheBox2020!' -AsPlainText -Force
```
### Create credentials
```
$cred = New-Object System.Management.Automation.PSCredential('Rel1nk',$pass)
```
### Create Mounted Drive in powershell
```
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Credential $cred -Root "\\IpAddress\DaveKennedy"
```
### Navigate to temporary directory
```
cd Public:
```

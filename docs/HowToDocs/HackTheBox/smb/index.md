---
title: Samba and SMB 
---

Create a teporary SMB share on Linux
'''
impacket-smbserver 'DaveKennedy' $(pwd) -smb2support -user "Rel1nk" -password "HackTheBox2020!"
'''
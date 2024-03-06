
## Possible Manipulation of Tokens on a Windows Computers Remotely Detected via Impersonate
Detects execution of the Impersonate tool. Which can be used to manipulate tokens on a Windows computers remotely (PsExec/WmiExec) or interactively

### Index patterns

 1. `*:winlogbeat-*`
 2. `*:logs*`

### Query
	process.command_line.text :"impersonate.exe" and process.command_line.text :("list" or "exec" or "adduser" or "help")


### Reference
https://sensepost.com/blog/2022/abusing-windows-tokens-to-compromise-active-directory-without-touching-lsass/

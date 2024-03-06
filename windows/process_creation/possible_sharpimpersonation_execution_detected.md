## SharpImpersonation Execution


### About
Detects execution of the SharpImpersonation tool. Which can be used to manipulate tokens on a Windows computers remotely (PsExec/WmiExec) or interactively

### References
https://github.com/S3cur3Th1sSh1t/SharpImpersonation

### Index Patterns

 1. `*:winlogbeat-*`
 2. `*:logs*`

###  Query

    ((process.executable.text:"SharpImpersonation.exe") or (process.pe.original_file_name:"SharpImpersonation.exe") and (process.command_line.text:(*user* or *technique* or *shellcode* or *ImpersonateLoggedOnuser* )))


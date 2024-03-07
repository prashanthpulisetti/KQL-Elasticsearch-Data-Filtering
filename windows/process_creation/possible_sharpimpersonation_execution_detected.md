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

### Investigation
If your KQL query reveals any activity related to SharpImpersonation, it’s important to take immediate action. Here are some steps you might consider:

1. **Isolate the affected system**: If possible, disconnect the system from the network to prevent any potential spread of malicious activity.
2. **Preserve logs and evidence**: Make sure to preserve any relevant logs or other evidence. This could include network logs, system logs, or file system logs.
3. **Analyze the SharpImpersonation tool**: If you’ve identified the use of the SharpImpersonation tool, try to understand what it was used for. The tool can be used for various purposes, such as manipulating tokens on Windows computers.
4. **Identify the source of the tool**: Try to identify where the SharpImpersonation tool came from. This could involve analyzing network logs to identify any suspicious downloads or connections.
5. **Check for other signs of compromise**: The use of the SharpImpersonation tool could be part of a larger attack. Check for other signs of compromise on your network.
6. **Engage your incident response team**: If you have an incident response team, engage them as soon as possible. They can help to contain the incident and start the recovery process.
7. **Report the incident**: Depending on the nature of your organization and the incident, you may need to report the incident to law enforcement or a relevant regulatory body.
   
Remember, these steps are just a starting point. Every situation is unique, so you’ll need to adjust your response based on the specifics of your case.

## Possible Credential Dumping via Mimikatz

### About
The `sekurlsa::logonpasswords` command in Mimikatz is infamous for being able to "dump plaintext passwords from memory". Having a users password has clear advantages (see **Make Token**) and was a lucrative tactic for a long time. However, Microsoft have implemented a lot of mitigations in Windows 10 and above (e.g. by disabling [wdigest](https://stealthbits.com/blog/wdigest-clear-text-passwords-stealing-more-than-a-hash/) by default), so happening across plaintext passwords is certainly less common. This module is still capable of retrieving NTLM hashes which is useful for pairing with the **Pass the Hash** or even cracking to recover the plaintext.

### Definition
Index patterns
`*:winlogbeat-*`
`*:logs-windows*`
`*:logs-system*`

### Custom query
```sql
process.command_line.text : "sekurlsa::LogonPasswords" or process.command_line.text :"sekurlsa::logonpasswords"
```

### Custom query language KQL

Author : Sai Prashanth Pulisetti
Severity : Critical
Risk score :  99
MITRE ATT&CK™
Execution (TA0002)(external, opens in a new tab or window)
Max alerts per run : 100

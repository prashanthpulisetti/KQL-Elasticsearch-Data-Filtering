## Possible Credential Dumping via Mimikatz

### Description  
The `sekurlsa::logonpasswords` command in Mimikatz is infamous for being able to "dump plaintext passwords from memory". Having a user's password has clear advantages (see **Make Token**) and was a lucrative tactic for a long time. However, Microsoft has implemented a lot of mitigations in Windows 10 and above (e.g., by disabling wdigest by default), so happening across plaintext passwords is certainly less common. This module is still capable of retrieving NTLM hashes which is useful for pairing with the **Pass the Hash** or even cracking to recover the plaintext.

### Index Patterns  
- `*:winlogbeat-*`  
- `*:logs-windows*`  
- `*:logs-system*`

### Query  
```kql
process.command_line.text : "sekurlsa::LogonPasswords" or process.command_line.text :"sekurlsa::logonpasswords"
```

### Reference
https://www.ired.team/offensive-security/credential-access-and-credential-dumping

### Investigation
The sekurlsa::logonpasswords command in Mimikatz is infamous for being able to "dump plaintext passwords from memory". Having a users password has clear advantages (see Make Token) and was a lucrative tactic for a long time. However, Microsoft have implemented a lot of mitigations in Windows 10 and above (e.g. by disabling wdigest(external, opens in a new tab or window) by default), so happening across plaintext passwords is certainly less common.

This module is still capable of retrieving NTLM hashes which is useful for pairing with the Pass the Hash or even cracking to recover the plaintext.

### Notes

- Author: Sai Prashanth Pulisetti
- Severity: Critical
- Risk Score: 99
- MITRE ATT&CK: Execution (TA0002)
- Max Alerts per Run: 100
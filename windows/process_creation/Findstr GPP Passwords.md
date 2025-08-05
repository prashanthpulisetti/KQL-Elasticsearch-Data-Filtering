## Findstr GPP Passwords

### Description  

Look for the encrypted cpassword value within Group Policy Preference files on the Domain Controller. This value can be decrypted with gpp-decrypt.

### Index Patterns  

List the index patterns the query applies to:

- `*:winlogbeat-*`  
- `*:logs*`  


### Query  

```kql
process.name:"findstr.exe" AND process.command_line.text :("cpassword" OR "\\sysvol\\" OR "*.xml")
```

### Reference
https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1552.006/T1552.006.md#atomic-test-1---gpp-passwords-findstr

### Notes
- Author: Saiprashanth Pulisetti
- Severity : Low
- Risk score : 21
- MITRE ATT&CK™ : 
- Credential Access (TA0006)
    - Credentials from Password Stores (T1555)
- Max alerts per run: 100

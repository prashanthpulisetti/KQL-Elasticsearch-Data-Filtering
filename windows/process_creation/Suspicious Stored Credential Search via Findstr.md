## Suspicious Stored Credential Search via Findstr

### Description  

The file findstr is often used by pentesters to find insecurely stored passwords in clear text.

### Index Patterns  

List the index patterns the query applies to:

- `*:winlogbeat-*`  
- `*:logs-windows*`
- `*:logs-system*`

### Query  

```kql
process.name.text : "findstr.exe" AND process.command_line.text : ("password" OR "admin" OR "passwd" OR "credentials" OR "keypass" OR "keystore")

```

### Reference
https://www.hacking.land/2021/08/process-dump-windows-tool-for-dumping.html

### MITRE ATT & CK

- Credential Access (TA0006)
    - Credentials from Password Stores (T1555)

## Notes
- Author : Saiprashanth Pulisetti
- Severity: Low
- Risk score: 21
- Max alerts per run: 100
## Possible Sharphound Tool Patterns (via cmdline)  

### Description  
SharpHound is the official data collector for BloodHound, written in C# and uses Windows API functions and LDAP namespace functions to collect data from domain controllers and domain-joined Windows systems.

### Index Patterns  
- `*:winlogbeat-*`  
- `*:logs*`  

### Query  

```kql
process.command_line.text:("CollectionMethod" OR "Loopduration" OR "LoopInterval" OR "LDAPFilter" OR "SearchBase" OR "RealDNSName" OR "OutputPrefix" OR "PortScanTimeout" OR "CacheFileName")

```

### Reference
https://github.com/Neo23x0/sigma/blob/master/LICENSE.Detection.Rules.md

### Notes
Author : Sai Prashanth Pulisetti
Severity : High
Risk score : 73
MITRE ATT&CK™ :
 - Discovery (TA0007)
    - Group Policy Discovery (T1615)

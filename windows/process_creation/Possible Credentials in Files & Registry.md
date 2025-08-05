## Possible Credentials in Files & Registry

### Description  
Adversaries may search the Windows Registry on compromised systems for insecurely stored credentials for credential access. This can be accomplished using the query functionality of the reg.exe system utility, by looking for keys and values that contain strings such as "password". In addition, adversaries may use toolkits such as PowerSploit in order to dump credentials from various applications such as IIS.Accordingly, this analytic looks for invocations of reg.exe in this capacity as well as that of several powersploit modules with similar functionality.

### Index Patterns  

List the index patterns the query applies to:

- `*:winlogbeat-*`  
- `*:logs*`  

### Query  

```kql
event.code: ("1" or "4688") and (process.command_line.text:("reg") and process.command_line.text:("password")) or process.command_line.text:("Get-SiteListPassword" or "Get-RegistryAutoLogon" or "Get-CachedGPPPassword" or "Get-ApplicationHost" or "Get-UnattendedInstallFile" or "Get-Webconfig")
```

### Reference

### Notes
- Author: Sai Prashanth Pulisetti
- Severity: Medium
- MITRE ATT&CK™: 
  - Credential Access (TA0006)
    - Credentials from Password Stores (T1555)

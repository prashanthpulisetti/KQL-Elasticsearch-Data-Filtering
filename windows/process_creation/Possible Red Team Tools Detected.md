## Possible Red Team Tools Detected

### Description  

The red team is considered the offensive side of the security. Red teams think like the attacker, they imitate real-world attacks and mimic adversary techniques and methods, uncover vulnerabilities in an organization’s infrastructure, launch exploits, and report on their findings.

### Index Patterns  

List the index patterns the query applies to:

- `*:winlogbeat-*`  
- `*:logs*`  

*(Add or remove as needed)*

### Query  

```kql
process.command_line.text:("invoke-atomicredteam" or "Recon.psm1" or "Recon.psd1" or "PowerView.ps1" or "Invoke-ReverseDnsLookup.ps1" or "Invoke-Portscan.ps1" or "Invoke-Portscan.ps1" or "Invoke-Portscan.ps1" or "Get-ComputerDetail.ps1" or "Invoke-//ShareFinder" or "Adfind.exe" or "coldcryptor.exe" or "adsisearcher" or "SharpShares.exe") or process.pe.original_file_name :"SharpView.exe"  or process.name.text :"goransom-windows.exe"  or ( file.name:("redline.exe" or "Seatbelt.exe"  or "sharpu.exe") and not process.executable.text:("SentinelAgent.exe" or "MsMpEng.exe")) and file.name:("stepFourteen_credDump.ps1") or (process.command_line.text :("iex") and process.command_line.text:("Get\\-CreateProcessSystemBind.ps1" or "NamedPipeSystem.ps1" or "Inveigh.ps1"))

```
### Notes

- Author Saiprashanth
Severity : Critical
Risk score:  99

MITRE ATT&CK™ :
 - Reconnaissance (TA0043)
  - Active Scanning (T1595)
 - Command and Control (TA0011)
    - Remote Access Software (T1219)
Max alerts per run : 100

#### title: Suspicious UI Automation Named Pipe Creation
#### status: experimental
### description: |
    Detects creation of named pipes with UIA_PIPE_ prefix, which are used by Microsoft's UI Automation framework.
    This activity may indicate malicious use of UI Automation for credential theft or unauthorized UI interaction.
    Coyote malware has been observed using UI Automation to extract credentials from banking applications.

#### references:
    - https://www.akamai.com/blog/security-research/active-exploitation-coyote-malware-first-ui-automation-abuse-in-the-wild#detect
    - https://docs.microsoft.com/en-us/windows/win32/winauto/uiauto-intro

#### author: Saiprashanth Pulisetti
#### date: '2025-07-29'
#### modified: '2025-07-29'
#### tags:
    - attack.credential-access
    - attack.t1555
    - attack.t1056.002
    - attack.collection
    - attack.t1113
#### logsource:
    category: pipe_created
    product: windows
    definition: Requires Sysmon Event ID 17 (Pipe Created) to be configured in Sysmon configuration

query: 
```sql
file.name : "*\\UIA_PIPE_*" and not (process.executable : "*\\Narrator.exe" or  "*\\osk.exe" or  "*\\magnify.exe" or "*\\utilman.exe" or "*\\sethc.exe" or  "*\\atbroker.exe" or "*\\displayswitch.exe" or "*\\dwm.exe" or "*\\explorer.exe")
```


#### falsepositives:
    - Legitimate Windows accessibility applications
    - Screen readers and assistive technology software
    - Legitimate UI automation testing tools
    - Windows system processes using UI Automation
    
level: medium

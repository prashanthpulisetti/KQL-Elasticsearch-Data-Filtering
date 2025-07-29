title: Suspicious UIAutomationCore.dll Loading By Process
description: |
  Detects when a process loads UIAutomationCore.dll, which may indicate abuse of Microsoft's UI Automation framework.
  This technique has been observed in Coyote malware for credential theft from banking applications and cryptocurrency exchanges.
  The rule monitors for processes that load the UI Automation Core library, which enables automated interaction with UI elements.
query: 
  "event.action : ```IMAGE LOADED ( Rule:IMGLOAD)" or event.action : "LOAD" and  (dll.path : "*\\UIAutomationCore.dll" or file.path : "*\\UIAutomationCore.dll") and  not ( dll.path : "C:\\Windows\\System32\\*" or dll.path : "C:\\Windows\\SysWOW64\\*" or file.path : "C:\\Windows\\System32\\*" or  file.path : "C:\\Windows\\SysWOW64\\*" or process.executable:(*\\Narrator.exe or *\\osk.exe or *\\magnify.exe or *\\utilman.exe or *\\sethc.exe or *\\atbroker.exe or *\\displayswitch.exe))```
tags:
    - attack.credential-access
    - attack.t1555
    - attack.t1056.002
    - attack.collection
    - attack.t1113
logsource:
    product: windows
    category: image_load
falsepositives:
    - Legitimate accessibility applications
    - Screen readers and assistive technology
    - Automation tools and testing frameworks
    - Administrative scripts using UI automation
level: medium

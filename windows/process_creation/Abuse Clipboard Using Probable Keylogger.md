## Abuse Clipboard Using Probable Keylogger

### Description  

A keylogger is an insidious form of spyware. when we enter sensitive data onto keyboard, believing nobody is watching. In fact, keylogging software is hard at work logging everything that you type. Keyloggers are activity-monitoring software programs that give hackers access to your personal data. The passwords and credit card numbers you type, the webpages you visit – all by logging your keyboard strokes. The software is installed on your computer, and records everything you type. Then it sends this log file to a server, where cybercriminals wait to make use of all this sensitive information.

### Index Patterns  
- `*:winlogbeat-*`  
- `*:logs*`  

*(Add or remove as needed)*

### Query  

```kql
process.name.text:"clip.exe" and (process.parent.command_line.text :("Get-Clipboard" or "keyboardState" or "hideKeyboardState" or "GetAsyncKeyState")) or process.command_line.text : ("Get-Clipboard" or "keyboardState" or "hideKeyboardState" or "GetAsyncKeyState")
```

### Reference

### Notes

- Author: Sai Prashanth Pulisetti
- Severity: High
- Risk score: 73
- MITRE ATT&CK™: 
    - Credential Access (TA0006)
        - Credentials from Password Stores (T1555)
- Max alerts per run: 100

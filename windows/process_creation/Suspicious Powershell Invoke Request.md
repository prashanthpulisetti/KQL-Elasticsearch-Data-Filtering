## Suspicious Powershell Invoke Request

### Description  

Detected logs are related to powershell executable invoking methods related to penetration testing.

### Index Patterns  

List the index patterns the query applies to:

- `*:winlogbeat-*`  
- `*:logs*`  

*(Add or remove as needed)*

### Query  

```kql
process.args: "Invoke-Tasksbackdoor" and process.name.text: powershell.exe

```

### Reference

### Investigation

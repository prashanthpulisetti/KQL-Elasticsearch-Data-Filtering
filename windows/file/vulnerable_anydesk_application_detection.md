# Vulnerable AnyDesk Application Detection

## About

This use case is designed to detect the presence and usage of the    AnyDesk application with version less than 8.0.8 in your environment.    AnyDesk is a remote desktop software that allows users to connect to    computers remotely. While it has legitimate uses, it can also be    exploited for malicious activities such as unauthorized access or    data exfiltration. In the light of recent Anydesk data breach, though    there are no evidence that any end-user devices have been affected    and the situation is under control & it is safe to use AnyDesk.    However, please ensure that latest version 8.0.8 of the software is    being used which comes with the new code signing certificate. This is    an informational alert. We will not call or communicate any further    regarding this incident, and the ticket will be closed automatically.    If you need assistance, please respond to this e-mail incase if you    have any further queries or to investigate further.

## Author:
 1. Sai Prashanth Pulisetti

## Index Patterns

 1. `*:winlogbeat-*`
 2. `*:logs*`

## Query:
    (process.pe.original_file_name :"Anydesk.exe" or process.executable:"anydesk.exe" or process.name.text :"anydesk.exe") and not process.command_line.text :"--uninstall" and not file.name:AnyDeskUninst*.exe and process.pe.file_version < "8.0.8"

## Reference
  https://www.bleepingcomputer.com/news/security/anydesk-says-hackers-breached-its-production-servers-reset-passwords/

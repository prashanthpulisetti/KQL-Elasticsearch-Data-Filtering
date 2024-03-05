# Torrent Downloads Detected

## Description

The  **Torrent Downloads Detected**  rule identifies activities related to the downloading of torrent files. These files are often associated with malware distribution. Cyber espionage groups, including APT37 and KARAE, exploit torrent file-sharing sites to indiscriminately disseminate malware to unsuspecting victims.

## Index Patterns:

- `*:winlogbeat-*`
- `*:logs*`
## Author

-   **Author:**  Sai Prashanth Pulisetti

## Detection Query

Use the following query to detect torrent-related activities:

```kql
rule.name: Downloads and (file.path.text: torrent or file.extension:torrent)
```

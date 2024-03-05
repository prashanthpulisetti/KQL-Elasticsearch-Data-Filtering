## DNS Query for Anonfiles.com Domain - Sysmon

### About
Detects DNS queries for "anonfiles.com", which is an anonymous file upload platform often used for malicious purposes references

### Query

    dns.question.name: *.anonfiles.com or dns.query.name: *.anonfiles.com
## references
https://www.trendmicro.com/vinfo/us/security/news/ransomware-spotlight/ransomware-spotlight-blackbyte

## DNS Query for Anonfiles.com Domain - Sysmon

### About
Detects DNS queries for "anonfiles.com", which is an anonymous file upload platform often used for malicious purposes references

### Query

    dns.question.name: *.anonfiles.com or dns.query.name: *.anonfiles.com

## Investigation

When you detect DNS queries for "anonfiles.com", it's important to conduct a thorough investigation to understand the context and potential impact. Here are some steps you might consider:

1. **Identify the source of the query**: Determine the system or user that initiated the DNS query. This could involve checking system logs or network traffic data.

2. **Check for file downloads**: If "anonfiles.com" is being used, there might be file downloads involved. Check your network logs for any file download activity. 

3. **Analyze the downloaded files**: If any files were downloaded, conduct a malware analysis. This could involve checking the file's hash against known malware databases, or conducting a static or dynamic analysis of the file.

4. **Understand the context**: Try to understand why "anonfiles.com" was accessed. Was it a user downloading a file they were sent? Or is it a sign of an automated process, like malware beaconing?

5. **Look for other signs of malicious activity**: A DNS query to "anonfiles.com" could be one part of a larger attack. Look for other signs of suspicious activity on your network.

Remember, these steps are just a starting point. Every situation is unique, so you'll need to adjust your investigation based on the specifics of your case.

## references
https://www.trendmicro.com/vinfo/us/security/news/ransomware-spotlight/ransomware-spotlight-blackbyte

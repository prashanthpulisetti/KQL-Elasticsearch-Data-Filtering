## Possible Akira Ransomware Extensions Detected

### About
Akira Ransomware encrypts a victim's files and demands a ransom for a decryption key. The encrypted files are often renamed by adding a specific extension to the original filename, like many ransomware strains. As a result, the ransomware is able to identify which files have been encrypted and also provides a clear indication to victim that their files are compromised. 

### Author
	
 1. Sai Prashanth Pulisetti

### Index Patterns

 1. `*:winlogbeat-*`
 2. `*:logs*`

###  Query

    file.name: akira*.txt
### Reference
https://eventlogs.in/akira-ransomware-analysis-recommendations/

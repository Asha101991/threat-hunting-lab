# Threat Hunting Lab

A hands-on Cyber Security Threat Hunting Lab built using Splunk, Sysmon, Windows Event Logs, Sigma Rules, and MITRE ATT&CK.

## Objectives

- Hunt for malicious activity
- Detect PowerShell abuse
- Investigate persistence mechanisms
- Analyze authentication attacks
- Detect lateral movement
- Practice SOC workflows

## Tools

- Splunk Enterprise
- Sysmon
- Windows Event Logs
- Sigma
- MITRE ATT&CK
- YARA

## Skills Demonstrated

- Threat Hunting
- Log Analysis
- Detection Engineering
- IOC Analysis
- MITRE ATT&CK Mapping
- SOC Investigation

## Example SPL Searches

### Failed Logons

index=wineventlog EventCode=4625

### Successful Logons

index=wineventlog EventCode=4624

### Encoded PowerShell

index=sysmon EventCode=1 powershell.exe "*EncodedCommand*"

### Suspicious Parent Processes

index=sysmon EventCode=1 ParentImage="*winword.exe"

### New Local Administrator

index=wineventlog EventCode=4728

## MITRE ATT&CK

| Technique | ID |
|------------|----|
| PowerShell | T1059.001 |
| Command Shell | T1059 |
| Valid Accounts | T1078 |
| Lateral Movement | T1021 |
| Credential Access | T1003 |

## Author

Ashaar Leacock-Thomas

Cybersecurity Graduate Student

Security Operations Center (SOC) Analyst

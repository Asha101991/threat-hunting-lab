# Threat Hunt Report

## Hunt Name
PowerShell Abuse Detection

## Analyst
Ashaar Leacock-Thomas

## Date
YYYY-MM-DD

## Objective
Identify suspicious PowerShell execution that may indicate malware execution, phishing payloads, or attacker activity.

## Hypothesis
An attacker may use PowerShell with encoded commands or execution policy bypasses to execute malicious payloads.

## Data Sources
- Sysmon Event ID 1: Process Creation
- Windows PowerShell Logs
- Windows Security Logs

## Hunt Query

```spl
index=sysmon EventCode=1 Image="*powershell.exe"
| search CommandLine="*EncodedCommand*" OR CommandLine="*Bypass*" OR CommandLine="*DownloadString*" OR CommandLine="*IEX*"
| table _time, Computer, User, ParentImage, Image, CommandLine
```

## Findings

| Finding | Details |
|---|---|
| Suspicious command line | Example encoded PowerShell command detected |
| Parent process | WINWORD.exe spawned PowerShell |
| User context | Standard user account |
| Host | Windows workstation |

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---|---|---|
| Execution | PowerShell | T1059.001 |
| Defense Evasion | Obfuscated Files or Information | T1027 |

## Risk Rating
High

## Recommendations

- Enable PowerShell Script Block Logging
- Monitor Event ID 4104
- Restrict PowerShell execution policy where possible
- Alert on encoded commands and suspicious parent processes
- Review endpoint for additional indicators of compromise

## Conclusion
Suspicious PowerShell activity was identified and should be investigated further. Additional endpoint triage is recommended.

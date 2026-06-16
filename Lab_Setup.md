# Lab Setup Guide

## Requirements

- Windows 10/11 test machine or virtual machine
- Splunk Enterprise or Splunk Free
- Sysmon
- Sysmon configuration file
- Sample Windows Event Logs or live endpoint logs

## Steps

1. Install Splunk.
2. Create indexes named `wineventlog` and `sysmon`.
3. Install Sysmon on the Windows endpoint.
4. Forward logs into Splunk using Splunk Universal Forwarder or upload sample data.
5. Run SPL searches from the `splunk-searches/` folder.
6. Document findings in `reports/Threat_Hunt_Report.md`.

## Recommended Splunk Indexes

```text
wineventlog
sysmon
network
endpoint
```

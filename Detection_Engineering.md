# Detection Engineering Notes

## Detection Workflow

1. Define the behavior to detect.
2. Identify relevant log sources.
3. Write a hypothesis.
4. Build an SPL query.
5. Test the query against sample data.
6. Reduce false positives.
7. Map the detection to MITRE ATT&CK.
8. Document investigation steps.

## Good Detection Questions

- What user ran the command?
- What process launched it?
- Was the command encoded or obfuscated?
- Was the activity seen on multiple systems?
- Does the activity match known attacker behavior?

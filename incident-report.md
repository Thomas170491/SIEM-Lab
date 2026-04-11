# Incident Report: Suspicious PowerShell Execution

## Summary
Suspicious PowerShell activity was detected through process creation logs in the SIEM lab, triggering an investigation into potential malicious behaviour.

Example observed command:
powershell.exe -NoProfile -ExecutionPolicy Bypass -File script.ps1

## Context
- Log source: Sysmon Event ID 1
- Tooling: ELK Stack, WinlogbeatThe PowerShell process was analyzed in Kibana using Sysmn Event ID 1 logs, focusing on process nam, comand-line arguments and parent process relationships. 

- Environment: Windows VM

## Investigation

Fields analyzed:

- process.name
- process.agrs
- process.parent.name

The command line and parent process were reviewed to determine whether the activity was legitimate.

Additional context was gathered by examining related events and user behavior.

## Findings
- PowerShell execution successfully detected
- Command-line analysis provided visibility into behavior
- No additional malicious activity observed 
- No suspicious indicators such as encoded commands (-enc), obfuscation or abnormal parent-child relationships were observed.

## Conclusion
This event demonstrates how process creation logs, particularly Sysmon Event ID 1, can be leveraged in a SIEM to detect and investigate suspicious activity in a SOC environment.

## Analyst Decision
Benign

## Justification
The PowerShell execution was triggered by a known user on a legitimate workstation.

The command-line arguments were simple and not obfuscated, and no suspicious flags were identified.

The activity occurred during normal working hours and no additional suspicious events (such as unusual network connections or repeated executions) were observed.

Based on this context, the activity is considered consistent with normal system or user behavior.

## Limitations

This analysis is limited to available logs data and would benefit from additional context such as network telemetry or EDR alerts.

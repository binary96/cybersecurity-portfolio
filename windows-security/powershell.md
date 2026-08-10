# PowerShell Logging Basics

## Objective

Investigate how Windows records harmless PowerShell activity.

## Lab Environment

- Operating system: Windows 10
- Computer:
- User:
- PowerShell host: powershell.exe
- Log channel: Microsoft-Windows-PowerShell/Operational

## Commands Executed

- Get-Date
- Get-Process
- Get-Service
- Get-LocalUser
- Get-NetTCPConnection

## Event Investigated

- Date and time: 8.32
- Event ID:4104
- User:
- Computer:
- PowerShell host process:
- Complete command visible: Yes/No
- Log channel:

## Findings

Describe what information was recorded and whether the complete command was visible.

## Logging Configuration

- Script Block Logging: Enabled
- Module Logging: Enabled
- Module names: *

## Analyst Interpretation

The observed commands were deliberately executed as harmless lab activity. PowerShell use is not automatically malicious; the commands and surrounding context determine whether investigation is required.

## Visibility Limitations

Basic PowerShell logs may show that the engine started without recording every command. Script Block Logging improves command visibility, while process-creation auditing can provide additional information about powershell.exe and its parent process.

## Security Consideration

Detailed PowerShell logging may capture sensitive information entered into commands. Passwords, tokens and other secrets should not be placed directly in PowerShell command lines.

## Conclusion

PowerShell telemetry is valuable because it can show which commands were executed, when they ran and which account was involved. However, effective investigation usually requires correlation with process, authentication and network events.

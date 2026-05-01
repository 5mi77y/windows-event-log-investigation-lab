# Windows Event Log Investigation Lab

## Overview

This project is a beginner SOC-style lab using Windows Event Viewer to investigate successful logon activity on a Windows virtual machine.

The goal was to review Windows Security logs, identify Event ID 4624 successful logon events, and document the difference between Remote Desktop logon activity and session unlock activity.

## Tools Used

- Microsoft Azure
- Windows Virtual Machine
- Windows Event Viewer
- Remote Desktop / Windows App
- GitHub

## Skills Demonstrated

- Navigating Windows Event Viewer
- Reviewing Windows Security logs
- Identifying successful logon events
- Understanding Windows logon types
- Documenting investigation findings
- Creating a simple security investigation report

## Key Findings

During the investigation, I reviewed Windows Security logs and identified successful logon events for the account `connoradmin`.

| Event ID | Logon Type | Account | Source IP | Meaning |
|---|---:|---|---|---|
| 4624 | 10 | connoradmin | 50.92.120.215 | Successful Remote Desktop logon |
| 4624 | 7 | connoradmin | 50.92.120.215 | Session unlock / resumed session |

## Evidence

Screenshots were captured showing:

- Event ID 4624 successful logon activity
- Logon Type 10 Remote Desktop login
- Logon Type 7 session unlock activity
- Account name, workstation name, and source network address

Evidence files:

- `event-4624-logon-type-10-rdp-success.png`
- `event-4624-logon-type-7-session-unlock.png`

## Report

The full investigation report is available here:

[`analysis.md`](analysis.md)

## What I Learned

Through this lab, I learned how Windows records successful logon activity and how Event Viewer can be used to investigate user access.

I also learned that different logon types provide important context about how access occurred, such as Remote Desktop logons versus session unlocks.

## Next Steps

In a real-world investigation, I would continue by:

- Reviewing failed logon events using Event ID 4625
- Checking for unusual source IP addresses
- Reviewing other events around the same timeframe
- Escalating unexpected access to an IT or security team

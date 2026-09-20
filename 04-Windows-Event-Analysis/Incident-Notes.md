# 📝 Incident Notes — Windows Event Analysis

## Investigation Date
20 September 2026

## Environment
Windows workstation — `Dev`

## Event 4625 — Failed Logon
- Total observed: 9
- Investigated Logon Type: 2 (Interactive)
- Status: `0xc000006d`
- SubStatus: `0xc000006a` (incorrect password)
- IP Address: `-`

The observed event represents an interactive logon failure caused by an incorrect password.

The nine events were distributed across different times:
- 4 around 7 PM
- 2 around 9 PM
- 2 around 10 PM
- 1 at another time

This distribution does not by itself establish a brute-force attack.

## Event 4624 — Successful Logon
- Target: SYSTEM
- Logon Type: 5 (Service)
- Process: `services.exe`
- IP Address: `-`

This represents service activity rather than evidence of a successful interactive user login.

## Event 4688 — Process Creation
- New Process: `C:\Windows\System32\lsass.exe`
- Parent Process: `C:\Windows\System32\wininit.exe`
- User context: SYSTEM
- Command Line: blank

The observed process and parent process are consistent with expected Windows system activity. No malicious conclusion was made from this event alone.

## Event 4104 — PowerShell
No matching events were found.

## Event 4672 — Special Privileges
No matching events were found.

## Event 4648 — Explicit Credentials
- Target server: `localhost`
- Process: `lsass.exe`
- IP Address: `-`

Explicit credential usage was observed in a local context. The event alone does not establish credential theft or malicious activity.

## Overall Assessment
The investigation identified multiple failed interactive logons but did not establish a remote brute-force attack or successful compromise from the reviewed evidence.

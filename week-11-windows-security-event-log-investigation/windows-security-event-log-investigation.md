
CYBERSECURITY PROJECT 11
Windows Security
Event Log Investigation
A hands-on inspection of Windows authentication and logon-related security events using Event
Viewer.
AUTHOR  | DATE             | PLATFORM
Madhuri |26 November 2026 | Windows
INVESTIGATION TOOL LOG INVESTIGATED PRACTICAL TYPE
Windows Event Viewer Windows Security Log Hands-on inspection
PROJECT SCOPE
Event IDs examined
Event ID Recorded activity
4624 Successful Logon
4625 Failed Logon
4634 Logoff
4648 Logon Using Explicit Credentials
Investigation approach
Inspect existing Security log records, filter by Event ID, review General and XML details, and interpret the available
evidence without assuming that an individual event proves malicious activity.
PROJECT 11 / WINDOWS SECURITY EVENT LOG INVESTIGATION
CYBERSECURITY PRACTICAL REPORT • MADHURI 2
01 Project Overview
This project involves inspecting real Windows Security events using Event Viewer to understand authentication-related
activities and investigate account logon sessions.
Four important Windows Security Event IDs were examined: 4624, 4625, 4634 and 4648. The practical also includes
filtering event records and inspecting their General and XML details.
02 Objective
• Inspect real Windows Security event records.
• Filter events using specific Event IDs.
• Understand successful and failed logon activities.
• Examine logoff and explicit credential events.
• Inspect event details using General and XML views.
• Understand how Windows Security logs support basic cybersecurity investigations.
03 System Environment
Component Details
Operating System Windows
Investigation Tool Windows Event Viewer
Log Source Windows Security
Event Provider Microsoft-Windows-Security-Auditing
Practical Type Hands-on inspection
04 Tools and Technologies
Windows Event Viewer — A built-in Windows utility used to view and investigate recorded system and security events.
Windows Security Log — Stores security-related event records, including authentication and account activity,
depending on the configured audit policies.
XML View — Displays structured event information, including provider details, timestamps and event data.
05 Practical Methodology
• Opened Event Viewer using eventvwr.msc.
• Navigated to Windows Logs → Security.
• Inspected the available Security event records.
• Used Filter Current Log to filter the selected Event IDs.
• Examined Event IDs 4624, 4625, 4634 and 4648.
• Opened individual event records.
• Inspected the General tab for readable event descriptions.
• Examined the Details tab and XML View for structured information.
• Recorded actual observations from the available event records.
PROJECT 11 / WINDOWS SECURITY EVENT LOG INVESTIGATION
CYBERSECURITY PRACTICAL REPORT • MADHURI 3
06 Observations and Findings
6.1 Event ID 4624 — Successful Logon
Observed message: An account was successfully logged on.
Observed details
Field Observed value
Event ID 4624
Source Microsoft Windows security auditing
Task Category Logon
Keywords Audit Success
Logon Type 5
Additional details Account and Logon ID information were visible.
Event analysis
• Event ID 4624 records the successful creation of a logon session.
• Logon Type 5 represents a service logon, meaning the inspected event was associated with a service rather than a
normal interactive desktop sign-in.
Security relevance
Helps investigate successful account access and identify the type of logon session created.
6.2 Event ID 4625 — Failed Logon
Observed message: An account failed to log on.
Observed details
Field Observed value
Event ID 4625
Filtered matching records displayed 6
Source Microsoft Windows security auditing
Task Category Logon
Keywords Audit Failure
Logon Type 2
Event analysis
• Event ID 4625 records an unsuccessful logon attempt.
• Logon Type 2 represents an interactive logon attempt.
• The six matching records represent six failed logon events, not necessarily six different users or people.
Security relevance
Helps investigate repeated failed logon activity and possible password-guessing attempts.
PROJECT 11 / WINDOWS SECURITY EVENT LOG INVESTIGATION
CYBERSECURITY PRACTICAL REPORT • MADHURI 4
6.3 Event ID 4634 — Logoff
Observed message: An account was logged off.
Observed details
Field Observed value
Event ID 4634
Filtered matching records displayed 36
Source Microsoft Windows security auditing
Task Category Logoff
Keywords Audit Success
Logon Type 2
Additional details Account and Logon ID information were visible.
Event analysis
• Event ID 4634 records the termination of a logon session.
• The Logon ID can help correlate the session with a related successful logon event.
Security relevance
Helps establish session activity timelines and understand when logon sessions ended.
6.4 Event ID 4648 — Logon Using Explicit Credentials
Observed message: A logon was attempted using explicit credentials.
Observed details
Field Observed value
Event ID 4648
Filtered matching records displayed 26
Source Microsoft Windows security auditing
Task Category Logon
Keywords Audit Success
Additional details Subject account information and Account Whose Credentials Were Used information
were visible.
Event analysis
• Event ID 4648 records an attempt to use explicitly supplied credentials.
• It does not independently confirm that the resulting logon was successful.
Security relevance
Helps investigate alternate credential usage and identify the account and process involved when available.
PROJECT 11 / WINDOWS SECURITY EVENT LOG INVESTIGATION
CYBERSECURITY PRACTICAL REPORT • MADHURI 5
07 XML Event Inspection
The XML View of Event ID 4648 was inspected through Details → XML View. The following fields were visible in the
inspected record:
XML field Observed value
Provider Name Microsoft-Windows-Security-Auditing
Event ID 4648
Version 0
Level 0
Task 12544
Opcode 0
Event Record ID 207021
Process ID 764
Thread ID 5492
Channel Security
Computer Local computer identifier
TimeCreated 2026-11-25T11:23:52.6314242Z
XML View provides structured event information. It helps examine event metadata and detailed records beyond the
readable General tab.
08 Event Comparison
Event ID Activity Investigation purpose
4624 Successful Logon Investigate successful access
4625 Failed Logon Investigate unsuccessful access
4634 Logoff Examine session termination
4648 Explicit Credentials Investigate explicit credential usage
09 Cybersecurity Significance
Windows Security events provide useful evidence for basic security monitoring and investigation.
• Successful logon events help identify account access.
• Failed logon events help identify unsuccessful authentication attempts.
• Logoff events help establish session timelines.
• Explicit credential events help investigate the use of alternate credentials.
• Event correlation helps connect related activities using timestamps, account information and Logon IDs.
PROJECT 11 / WINDOWS SECURITY EVENT LOG INVESTIGATION
CYBERSECURITY PRACTICAL REPORT • MADHURI 6
Interpretation note
An individual event does not automatically prove malicious activity. Additional context and related records are required
before drawing conclusions.
10 Limitations
• Only event records available on the inspected Windows system were examined.
• Event fields may vary depending on the event type and available information.
• The presence of an event does not automatically indicate suspicious activity.
• The practical was limited to inspecting existing records; no event records or security settings were modified.
• The investigation does not establish that an attack occurred.
11 Key Learnings
Through this practical, I learned how to:
• Navigate Windows Security logs using Event Viewer.
• Filter event records using multiple Event IDs.
• Inspect successful and failed logon events.
• Understand logoff and explicit credential events.
• Examine General and XML event information.
• Interpret important event fields.
• Understand the role of Windows Security logs in basic cybersecurity investigations.
12 Conclusion
This practical provided hands-on experience in inspecting real Windows Security events using Event Viewer.
By examining Event IDs 4624, 4625, 4634 and 4648, I developed a better understanding of authentication activities,
logon sessions and explicit credential usage.
The exercise also demonstrated how event filtering, event details and XML inspection can support basic security
monitoring, troubleshooting and cybersecurity investigations.
13 Project Evidence
The following screenshots document the practical work:
• Security Event Log
• Filtered Security Events
• Event ID 4624 — Successful Logon
• Event ID 4625 — Failed Logon
• Event ID 4634 — Logoff
• Event ID 4648 — Explicit Credentials
• Event ID 4648 — XML View

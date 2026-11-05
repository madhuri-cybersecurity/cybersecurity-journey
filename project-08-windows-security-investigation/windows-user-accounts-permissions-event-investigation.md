# Project 08 – Windows User Accounts, Permissions & Security Event Investigation

**Date:** 6/11/2026

## 1. Objective

To investigate Windows user account privileges, examine file and folder permissions, and understand security-related activity recorded in Windows Event Viewer.

## 2. Environment and Tools

- Operating System: Microsoft Windows
- User Account: Madhu
- Account Type: Administrator
- Tools Used:
  - Windows Settings
  - Folder Properties
  - Security Tab
  - Advanced Security Settings
  - Event Viewer

## 3. Practical 1 – Windows User Account Inspection

### Procedure

1. Opened Windows Settings.
2. Navigated to Accounts → Your info.
3. Inspected the current Windows user account and its account type.

### Observations

- Account Name: MADHU
- Account Type: Administrator
- Microsoft Account: Linked

### Result

The current Windows account was identified as an Administrator account. Administrator accounts have elevated privileges to perform system-level administrative tasks.

## 4. Practical 2 – File and Folder Permission Inspection

### Procedure

1. Located the Cybersecurity Journey folder.
2. Opened Properties → Security.
3. Selected the Madhu user account.
4. Examined the displayed permissions.

### Observations

The following permissions were displayed as Allow for the Madhu account:

- Modify
- Read & Execute
- List folder contents
- Read
- Write

### Result

The folder permissions were successfully inspected. The selected user account had permissions to read, write, execute and modify files and folder contents.

## 5. Practical 3 – Advanced Security Settings Inspection

### Procedure

1. Opened the folder's Properties → Security tab.
2. Selected Advanced.
3. Examined the owner and permission entries.

### Observations

- Owner: Madhu
- Principals observed:
  - SYSTEM
  - Administrators
  - Madhu
- Permission Type: Allow
- Access: Full Control for all three displayed entries
- Applies To: This folder, subfolders and files
- Permissions were shown as inherited from the parent folder.

### Result

Advanced Security Settings were inspected successfully. The inspection helped identify the folder owner, permission principals, access levels and inheritance information.

## 6. Practical 4 – Windows Security Event Investigation

### Procedure

1. Opened Event Viewer using `eventvwr.msc`.
2. Navigated to Windows Logs → Security.
3. Inspected a security-related event.
4. Examined its General and Details information.

### Observed Event

- Event ID: 4798
- Event Description: A user's local group membership was enumerated.
- Account Name: Madhu
- Caller Process: `C:\Windows\explorer.exe`

### Analysis

Event ID 4798 records an operation in which Windows enumerates the local group membership information associated with a user account.

In this observation, the caller process was Windows Explorer (`explorer.exe`).

This event records group membership enumeration. It does not indicate that the user's group membership was changed.

A security event should be interpreted using its event details, account information, process information and surrounding activity rather than assuming that every logged event represents an attack.

## 7. Cybersecurity Relevance

- User account inspection helps identify account types and administrative privileges.
- Permission inspection helps understand access control over files and folders.
- NTFS permission inheritance helps explain how permissions can be applied to subfolders and files.
- Event Viewer provides security-related records that help investigate system activity.
- Event analysis helps distinguish normal system operations from potentially suspicious activity.

## 8. Conclusion

This project provided practical experience in inspecting Windows user accounts, examining file and folder permissions, understanding advanced security settings, and investigating a Windows Security event.

These activities helped develop a foundational understanding of Windows access control, user privileges and security event analysis.

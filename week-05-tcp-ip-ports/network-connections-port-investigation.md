````markdown
# Week 5 — TCP/IP + Ports

## Network Connections & Port Investigation

**Prepared By:** Madhuri Londhe  
**Domain:** Cybersecurity Fundamentals  
**Report Type:** Practical Investigation Project  
**Month:** October 2026  
**Date:** 04 October 2026

---

## 1. Objective

The objective of this project was to investigate active network connections and listening ports on a Windows system using built-in command-line tools.

The investigation focused on:

- Identifying TCP and UDP network activity
- Identifying listening ports
- Mapping network connections to Process IDs (PIDs)
- Mapping PIDs to processes
- Investigating executable paths
- Investigating process command lines
- Reviewing selected network connections from a cybersecurity perspective

---

## 2. Tools Used

- Windows Command Prompt
- `netstat -ano`
- `tasklist`
- `wmic`
- Windows Task Manager

---

## 3. Investigation Workflow

The investigation followed this workflow:

**Network Connections → PID → Process → Executable Path → Command Line → Security Observation**

---

## 4. Network Connection Collection — netstat -ano

The following command was used:

```cmd
netstat -ano
````

The command was used to collect:

* Protocol
* Local address
* Local port
* Remote address
* Remote port
* Connection state
* Process ID (PID)

Connection states observed during the investigation included:

* LISTENING
* ESTABLISHED
* CLOSE_WAIT
* LAST_ACK

---

## 5. PID → Process Identification

Selected Process IDs were investigated using the `tasklist` command.

The investigation identified the following processes:

| PID  | Process       |
| ---- | ------------- |
| 4492 | postgres.exe  |
| 3936 | Rave.exe      |
| 3040 | Rave.exe      |
| 2768 | SearchApp.exe |
| 8556 | chrome.exe    |

The PID was used to connect network activity with the corresponding running process.

---

## 6. Executable Path Investigation

Executable paths were investigated for selected processes.

| PID  | Process       | Executable Location                  |
| ---- | ------------- | ------------------------------------ |
| 3936 | Rave.exe      | User application directory           |
| 3040 | Rave.exe      | User application directory           |
| 2768 | SearchApp.exe | Windows SystemApps directory         |
| 8556 | chrome.exe    | Google Chrome installation directory |
| 4492 | postgres.exe  | Path was not returned by the command |

Executable path investigation helps determine whether a process is running from an expected application or system location.

---

## 7. Command-Line Investigation

Selected process command lines were investigated.

The investigation showed:

| PID  | Process    | Command-Line Observation       |
| ---- | ---------- | ------------------------------ |
| 3936 | Rave.exe   | `repocket.child.js`            |
| 3040 | Rave.exe   | `honeygain.child.js`           |
| 8556 | chrome.exe | Chrome Network Service process |

Command-line information provided additional context about how the selected processes were running.

---

## 8. Selected Connection Analysis

Selected PIDs were investigated using targeted `netstat` filtering.

The investigation showed:

| PID  | Process       | Network Observation                                         | Security Observation                                                                                                                  |
| ---- | ------------- | ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| 4492 | postgres.exe  | Listening on port 5432                                      | A database service was listening locally. Further firewall and application configuration review would be required to assess exposure. |
| 3936 | Rave.exe      | Established network connections                             | Network activity was associated with the Rave process.                                                                                |
| 3040 | Rave.exe      | Multiple established connections including ports 80 and 443 | Multiple external connections were associated with the application.                                                                   |
| 2768 | SearchApp.exe | Network connection observed                                 | The connection was associated with the Windows Search process.                                                                        |
| 8556 | chrome.exe    | Multiple network connections                                | Network activity was associated with the Chrome browser.                                                                              |

**Important:** The presence of a network connection or listening port alone does not prove malicious activity.

---

## 9. PostgreSQL Listening Port Observation

The following command was used:

```cmd
netstat -ano | findstr ":5432"
```

The result showed PostgreSQL associated with PID 4492 listening on port 5432.

This indicates that a PostgreSQL process was listening on the system.

This observation does not by itself prove that PostgreSQL was exposed to the Internet or vulnerable. Further investigation would require firewall and PostgreSQL configuration review.

---

## 10. Security Investigation Approach

A network connection should not be considered malicious based only on its IP address, port number, or connection state.

A basic investigation should correlate:

**Network Connection → PID → Process → Executable Path → Command Line → Expected Behavior**

This correlation provides stronger context for identifying unexpected activity.

---

## 11. Practical Findings

| Investigation Step            | Purpose                              | Result                                                       |
| ----------------------------- | ------------------------------------ | ------------------------------------------------------------ |
| `netstat -ano`                | Collect network connections and PIDs | TCP/UDP connections and listening ports were identified.     |
| `tasklist`                    | Map PID to process                   | Selected PIDs were mapped to processes.                      |
| Executable path investigation | Identify process location            | Application and system executable locations were identified. |
| Command-line investigation    | Understand process execution         | Additional process context was obtained.                     |
| Targeted `netstat`            | Investigate selected processes       | Network activity was correlated with selected processes.     |
| Port 5432 investigation       | Review PostgreSQL listener           | PostgreSQL listening activity was identified.                |

---

## 12. Cybersecurity Relevance

Network connection investigation is useful for:

* Identifying unexpected listening ports
* Identifying processes communicating over the network
* Correlating PIDs with applications
* Investigating suspicious processes
* Supporting incident investigation
* Understanding endpoint network activity
* Identifying potentially unnecessary exposed services

This practical exercise demonstrates basic endpoint network investigation skills.

---

## 13. Investigation Summary

The investigation used Windows built-in tools to move from raw network connection information to process-level analysis.

The investigation demonstrated:

**Network Connection → PID → Process → Executable Path → Command Line → Security Observation**

This provides a practical foundation for future topics such as network monitoring, security logs, firewall analysis, and incident investigation.

---

## 14. Conclusion

The project demonstrated how Windows network connections can be investigated using built-in command-line tools.

The investigation showed that `netstat -ano` can provide the starting point for identifying network activity, while PID mapping and process investigation provide additional context.

A connection or listening port should always be evaluated in context rather than automatically classified as malicious.

---

## Skills Demonstrated

* TCP/IP fundamentals
* Port identification
* Network connection analysis
* Windows command-line investigation
* PID-to-process correlation
* Process investigation
* Basic endpoint security analysis
* Security-oriented observation

```
```

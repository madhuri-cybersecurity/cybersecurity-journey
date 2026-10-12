# Project 06 — Network Protocols & Communication Models Investigation

## Objective
To investigate DNS resolution and HTTPS communication using Windows command-line tools, then relate the observed activity 
to the OSI and TCP/IP models.

## Tools Used
- `nslookup`
- `curl -I`
- `curl -v`
- Windows Command Prompt

## Practical Activities
1. Performed a DNS lookup for `google.com`.
2. Examined HTTPS response headers.
3. Investigated connection establishment and a connection-reset error.
4. Retested HTTPS using a HEAD request.
5. Mapped the observed activities to relevant OSI and TCP/IP layers.

## Key Findings
- DNS resolution returned IP addresses.
- An HTTPS HEAD request returned `200 OK`.
- A verbose GET request established a connection but encountered a reset while receiving the response.
- A subsequent HEAD request returned `200 OK`.
- These observations alone do not establish malware or system compromise.

## Project Files
- Investigation report (PDF and Word)
- Practical observations
- OSI/TCP-IP layer mapping
- Sanitized screenshots

## Conclusion
This investigation provided practical experience examining DNS resolution, HTTPS responses, connection behavior, and how 
network communication relates to layered models.

# Windows Security Settings & Firewall Inspection

**Author:** Madhuri  
**Date:** 16 November 2026  
**Project Category:** Windows Security | Cybersecurity Practical

## 1. Objective

To inspect Windows Security settings, Microsoft Defender Antivirus status, account protection, Windows Firewall profiles and firewall rules.

The objective was to understand how Windows protects a computer against security threats and unauthorized network connections through its built-in security features.

All activities were performed for inspection only. No security configurations were modified.

## 2. Environment and Tools

- **Operating System:** Microsoft Windows 10
- **Security Application:** Windows Security
- **Antivirus:** Microsoft Defender Antivirus
- **Firewall:** Windows Defender Firewall
- **Firewall Management Console:** Windows Defender Firewall with Advanced Security
- **Command:** `wf.msc`

## 3. Microsoft Defender Inspection

**Location:** Windows Security → Virus & threat protection

| Parameter | Observed Result |
|---|---|
| Current Threat Status | No current threats |
| Last Recorded Scan | 17 October 2026 |
| Scan Type | Quick Scan |
| Threats Found | 0 |
| Files Scanned | 59,526 |
| Scan Duration | 49 minutes 53 seconds |
| Protection Settings | No action needed |
| Security Intelligence | Up to date |
| Last Update | 14 November 2026 |

**Understanding:**

Microsoft Defender Antivirus provides built-in protection against malware and other security threats. The recorded scan detected zero threats. However, a clean scan does not guarantee that a device is completely free from threats.

## 4. Account Protection Inspection

**Location:** Windows Security → Account protection

- Microsoft account: Not signed in.
- Dynamic Lock feature: Available.
- Dynamic Lock configuration status: Not set up.

**Understanding:**

Account protection provides security features related to Windows accounts and sign-in. Dynamic Lock can automatically lock a Windows device when a paired Bluetooth device moves out of range.

## 5. Firewall & Network Protection

**Location:** Windows Security → Firewall & network protection

### Network Profile Status

| Network Profile | Firewall Status |
|---|---|
| Domain Network | ON |
| Private Network | ON |
| Public Network | ON |

### Active Network Profile

- Active Profile: Public Network
- Network Name: Active Wi-Fi Network
- Microsoft Defender Firewall: ON
- Incoming connections: Restricted
- Block all incoming connections, including allowed apps: Unchecked

### Firewall Properties

The properties of all three firewall profiles were inspected.

| Configuration | Observed Value |
|---|---|
| Firewall State | ON (Recommended) |
| Inbound Connections | Block (Default) |
| Outbound Connections | Allow (Default) |

**Understanding:**

The active Public Network page displayed that incoming connections were restricted. The Firewall Properties page showed the default inbound policy as Block and the default outbound policy as Allow.

Windows Firewall monitors network traffic and controls incoming and outgoing connections.

- **Domain Profile:** Used in domain-managed organizational networks.
- **Private Profile:** Used in trusted private networks.
- **Public Profile:** Used in public or untrusted networks.

## 6. Inbound and Outbound Firewall Rules

**Tool:** Windows Defender Firewall with Advanced Security  
**Command:** `wf.msc`

### Inbound Rules — Observations

- Application-specific firewall rules.
- Enabled and disabled entries.
- Allow and Block actions.
- Private and Public profile assignments.
- Application entries such as Eclipse and Java.

### Outbound Rules — Observations

- Windows system and application rules.
- Application-specific network permissions.
- Enabled and disabled entries.
- Allow actions.
- Different network profile configurations.

**Understanding:**

Inbound rules control incoming network connections to a computer. Outbound rules control outgoing network connections from a computer.

These rules help administrators manage network communication based on applications, ports, protocols and network profiles.

## 7. App & Browser Control

**Location:** Windows Security → App & browser control

- Reputation-based protection was available.
- Potentially unwanted app blocking: OFF.
- Microsoft Defender Application Guard: Not installed.
- Exploit protection: Available.

**Understanding:**

App & browser control helps protect against potentially malicious applications, files and websites.

Reputation-based protection and SmartScreen help identify suspicious or untrusted content. Exploit protection provides built-in security mitigations against certain software vulnerabilities.

## 8. Device Security

**Location:** Windows Security → Device security

- Security processor (TPM): Available.
- TPM was available on the device.
- Standard hardware security: Not supported.
- Secure Boot status: Not displayed in the inspected screenshot.

**Understanding:**

A Trusted Platform Module (TPM) is a hardware-based security component that supports cryptographic operations and protects security-related keys.

TPM provides hardware-based security capabilities. Its availability alone does not confirm that device encryption or BitLocker is enabled.

## 9. Windows Update

**Location:** Settings → Update & Security → Windows Update

- Windows displayed an end-of-support warning.
- The device was no longer receiving regular security updates.
- Important security and quality fixes were reported as missing.
- The device did not meet the displayed minimum hardware requirements for upgrading to Windows 11.
- Extended Security Updates (ESU) enrollment was offered.
- ESU enrollment status was not verified.

**Understanding:**

Windows 10 reached the end of regular support on 14 October 2025. Extended Security Updates provide an option for eligible devices to continue receiving security updates for a limited period.

Using a supported operating system and installing available security updates are important security practices.

## 10. Key Findings

- Microsoft Defender displayed no current threats.
- The last recorded quick scan detected zero threats.
- All three Windows Firewall profiles were enabled.
- Public Network was the active network profile.
- The active Public Network page showed restricted incoming connections.
- Default inbound connections were blocked, while outbound connections were allowed.
- Application-specific inbound and outbound firewall rules were present.
- TPM was available on the device.
- Potentially unwanted app blocking was turned off.
- Windows displayed an end-of-support warning and offered ESU enrollment.

## 11. Security Recommendations

- Keep Microsoft Defender security intelligence updated.
- Review potentially unwanted application protection settings.
- Maintain Windows Firewall protection across network profiles.
- Periodically review application-specific firewall rules.
- Verify whether the device is enrolled in Extended Security Updates (ESU), or upgrade to a supported Windows version.
- Review account protection and available sign-in security features.
- Verify device encryption and Secure Boot status separately where supported.

## 12. Conclusion

This practical provided hands-on experience inspecting Windows Security settings and Windows Defender Firewall.

I examined Microsoft Defender Antivirus, account protection, network profiles, inbound and outbound firewall rules, application protection, device security and Windows Update status.

The practical helped me understand how Windows security features protect a computer, how firewall rules control network communication and how to identify security configuration concerns.

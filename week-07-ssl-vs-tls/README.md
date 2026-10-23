# Project 07 — SSL vs TLS: HTTPS Connection and Certificate Investigation

## 1. Objective

The objective of this project is to understand the differences between SSL and TLS, inspect an HTTPS connection, investigate a digital certificate, and examine TLS protocol support using Chrome Developer Tools and Qualys SSL Labs.

This project provides practical experience in understanding how secure web connections work and how TLS configuration can be investigated from a cybersecurity perspective.

## 2. SSL vs TLS Comparison

| SSL | TLS |
|---|---|
| SSL stands for Secure Sockets Layer. | TLS stands for Transport Layer Security. |
| SSL is an older security protocol. | TLS is the successor to SSL. |
| SSL 2.0 and SSL 3.0 are obsolete and insecure. | TLS 1.2 and TLS 1.3 are widely used modern versions. |
| SSL should not be used to protect modern connections. | Supported TLS versions help protect data transmitted over a network. |
| SSL has known security weaknesses. | Modern TLS versions provide stronger security when configured correctly. |
| SSL is no longer recommended. | TLS is used to secure modern HTTPS connections. |

**Important:** SSL and TLS are related, but they are not the same protocol. The term “SSL certificate” is still commonly used, even though modern HTTPS connections use TLS.

## 3. HTTPS and the TLS Handshake

HTTPS stands for Hypertext Transfer Protocol Secure. It uses TLS to help protect communication between a browser and a web server.

TLS helps provide:

- **Confidentiality:** Encryption helps prevent unauthorized parties from reading transmitted data.
- **Integrity:** Security mechanisms help detect unauthorized modification of data.
- **Authentication:** A digital certificate helps the browser verify the server's identity.

### Simplified TLS Handshake

1. The client and server begin negotiating the connection's security parameters.
2. The server provides its digital certificate when required.
3. The browser validates the certificate and the server's identity.
4. The client and server establish the cryptographic keys needed to protect communication.
5. Encrypted application data is exchanged.

The exact handshake differs depending on the TLS version and connection configuration.

## 4. Practical 1 — HTTPS Connection Inspection

**Aim:** To inspect the security information of an HTTPS connection using Chrome Developer Tools.

**Website tested:** https://www.google.com

**Tools used:** Google Chrome Developer Tools — Security panel.

### Procedure

1. Open Google Chrome.
2. Visit https://www.google.com.
3. Open Developer Tools.
4. Select the **Security** tab.
5. Inspect the connection security and certificate information.

### Observations

- **HTTPS connection status:** Secure.
- **Certificate status:** Valid and trusted.
- **TLS version:** Not displayed in the Security overview.
- **Connection protocol displayed:** QUIC.
- **Key exchange information displayed:** X25519MLKEM768.
- **Cipher information displayed:** AES_128_GCM.

### Result

Chrome's Security panel showed that the website had a secure HTTPS connection and a valid, trusted certificate. The connection details displayed QUIC, X25519MLKEM768 and AES_128_GCM.

**Security lesson:** A browser's Security panel can provide useful information about a website's connection. The displayed connection details should be recorded accurately rather than assuming that the TLS version is visible.

## 5. Practical 2 — Digital Certificate Investigation

**Aim:** To inspect a website's digital certificate and identify its issuer and validity period.

**Website tested:** https://www.google.com

### Certificate Details

- **Certificate Common Name (CN):** `*.google.com`
- **Certificate issuer:** Google Trust Services (WE2)
- **Issued on:** 29 September 2026
- **Expires on:** 22 December 2026
- **Subject Alternative Name (SAN):** Not recorded in this investigation.
- **Browser certificate status:** Valid and trusted.

### Observations

The certificate details displayed `*.google.com` as the Common Name and Google Trust Services (WE2) as the issuer. Chrome reported the certificate as valid and trusted.

The certificate's validity dates indicate the period during which it is intended to be valid, subject to the relevant certificate and browser validation requirements.

### Result

The investigation demonstrated how to identify a certificate's Common Name, issuer and validity period in a browser.

**Security lesson:** Certificate validity, hostname matching and trust-chain validation are important when verifying a website's identity. A valid certificate alone does not guarantee that a website is legitimate or safe.

## 6. Practical 3 — TLS Configuration Using Qualys SSL Labs

**Aim:** To examine the TLS protocol support and security grades reported for a public website.

**Website tested:** `google.com`

**Tool used:** Qualys SSL Labs — SSL Server Test.

**Assessment date:** 23 October 2026

### Observations

- **Server entries listed:** 10
- **Grade observed:** B for all 10 listed entries.

| Protocol | Reported support |
|---|---|
| TLS 1.3 | Yes |
| TLS 1.2 | Yes |
| TLS 1.1 | Yes |
| TLS 1.0 | Yes |
| SSL 3 | No |
| SSL 2 | No |

### Result

The report listed support for TLS 1.0, TLS 1.1, TLS 1.2 and TLS 1.3. SSL 2 and SSL 3 were not supported. All 10 server entries displayed a B grade in the report I inspected.

### Security Analysis

TLS 1.2 and TLS 1.3 are modern protocol versions. TLS 1.0 and TLS 1.1 are deprecated and should generally be disabled where they are not required.

The observed B grade indicates that the tested configuration did not receive the highest available grade. The exact reasons for the grade should be determined by reviewing the detailed findings in the report rather than guessing.

**Important limitation:** SSL Labs examines the public server's TLS configuration. Its results do not necessarily identify the exact protocol version negotiated by my own browser connection.

## 7. Cybersecurity Lessons Learned

1. SSL is obsolete and should not be used for modern secure connections.
2. TLS is used to help protect data transmitted over HTTPS.
3. Encryption helps maintain the confidentiality of data in transit.
4. Integrity protection helps detect unauthorized changes to transmitted data.
5. Digital certificates help browsers verify server identity.
6. Certificate validity dates, hostname matching and trust-chain validation are important.
7. Chrome Developer Tools can help investigate HTTPS connection security.
8. Qualys SSL Labs can help identify supported protocols and assess a public server's TLS configuration.
9. Deprecated protocols such as TLS 1.0 and TLS 1.1 can indicate configuration issues that need review.
10. HTTPS and a valid certificate do not guarantee that a website is free from phishing, scams or malware.

## 8. Conclusion

In this project, I compared SSL and TLS, inspected an HTTPS connection in Chrome Developer Tools, investigated a digital certificate, and reviewed the TLS configuration of `google.com` using Qualys SSL Labs.

The browser inspection showed a secure HTTPS connection and a valid, trusted certificate. The certificate investigation identified its issuer and validity period. The SSL Labs report listed support for TLS 1.2 and TLS 1.3, as well as the deprecated TLS 1.0 and TLS 1.1 protocols, and displayed a B grade for all 10 listed server entries.

This practical investigation improved my understanding of HTTPS, digital certificates, TLS protocol versions and the importance of secure configuration during cybersecurity assessments.

## 9. Tools and Resources

- **Google Chrome Developer Tools:** HTTPS connection and certificate inspection.
- **Qualys SSL Labs:** Public server TLS configuration assessment.
- **Website tested:** https://www.google.com
- **SSL Labs:** https://www.ssllabs.com/ssltest/

## 10. Project Scope and Limitations

- This project involved observing a public website's connection and certificate details.
- The SSL Labs results represent the report observed on 23 October 2026 and may change when the server configuration changes.
- The exact TLS version negotiated by Chrome was not recorded in the Security overview.
- The certificate's Subject Alternative Name (SAN) was not recorded.
- No penetration testing, exploitation or unauthorized security testing was performed.

This project is for cybersecurity learning and documentation purposes.

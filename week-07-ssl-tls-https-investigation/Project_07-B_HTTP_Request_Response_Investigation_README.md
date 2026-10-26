# Project 07-B — HTTP Request & Response Investigation

## 1. Project Overview

This project investigates HTTP communication between a web browser and a web server using Chrome DevTools Network panel.

The objective is to understand HTTP request methods, response status codes, request and response headers, redirects, and the security relevance of HTTP communication through practical observation.

## 2. Objectives

- Inspect HTTP requests and server responses.
- Understand the difference between GET and POST methods.
- Observe HTTP status codes: 200 OK, 302 Found, and 404 Not Found.
- Examine request and response headers.
- Understand the role of redirects and response metadata.
- Identify security considerations relevant to web traffic analysis.

## 3. Tools and Environment

- **Browser:** Google Chrome
- **Tool:** Chrome DevTools — Network panel
- **Testing endpoints:** HTTPBin and Example Domain
- **Analysis method:** Browser-based HTTP request and response inspection

## 4. Practical 1 — GET Request Investigation

**Test URL:** `https://httpbin.org/get`

### Observed Results

| Field | Result |
|---|---|
| Request Method | GET |
| Status Code | 200 OK |
| Content-Type | application/json |
| Content-Length | 992 bytes |
| Server | gunicorn/19.9.0 |
| Referrer Policy | strict-origin-when-cross-origin |

### Observation

The browser sent a GET request to the server. The server returned a successful response containing JSON data.

The request headers included browser-related information such as `Accept`, `Accept-Encoding`, `Accept-Language`, and `User-Agent`.

### Conclusion

The practical demonstrated how to inspect a GET request, its status code, and selected response headers using Chrome DevTools.

## 5. Practical 2 — POST Request Investigation

**Form page:** `https://httpbin.org/forms/post`

**Observed request URL:** `https://httpbin.org/post`

### Observed Results

| Field | Result |
|---|---|
| Request Method | POST |
| Status Code | 200 OK |
| Request Content-Type | application/x-www-form-urlencoded |
| Request Content-Length | 189 bytes |
| Response Content-Type | application/json |
| Response Content-Length | 1544 bytes |
| Server | gunicorn/19.9.0 |

### Observation

The browser submitted form data using the POST method. The server returned a JSON response containing the submitted form fields.

The report intentionally excludes submitted personal information.

### Conclusion

The practical demonstrated how form data can be submitted in an HTTP request body and how the server's response can be inspected.

## 6. Practical 3 — HTTP Redirect Investigation

**Test URL:** `https://httpbin.org/redirect/1`

### Observed Results

| Field | Result |
|---|---|
| Initial Request Method | GET |
| Initial Status Code | 302 Found |
| Location Header | /get |
| Response Content-Type | text/html; charset=utf-8 |
| Response Content-Length | 215 bytes |
| Final Destination | `https://httpbin.org/get` |
| Final Response Status | 200 OK |

### Request Flow

`GET /redirect/1` → `302 Found` → `Location: /get` → `GET /get` → `200 OK`

### Observation

The server returned a 302 redirect response and specified `/get` in the `Location` header. The browser followed the redirect and reached the destination, which returned 200 OK.

### Security Relevance

Redirect destinations should be checked to ensure that users are not unexpectedly sent to untrusted websites. Redirects are not inherently malicious.

## 7. Practical 4 — HTTP 404 Status Code Investigation

**Test URL:** `https://example.com/this-page-does-not-exist-404`

### Observed Results

| Field | Result |
|---|---|
| Request Method | GET |
| Status Code | 404 Not Found |
| Content-Type | text/html; charset=utf-8 |
| Server | cloudflare |
| Request Path | /this-page-does-not-exist-404 |

### Observation

The server returned `404 Not Found` for the requested path, indicating that the requested resource was not available at that location.

### Security Relevance

Repeated 404 responses in web-server logs may indicate broken links, automated scanning, or attempts to discover hidden paths. A 404 response alone does not prove malicious activity.

## 8. Practical 5 — Response Headers and Security Analysis

The following headers were observed during the investigation.

| Header | Purpose | Security Relevance |
|---|---|---|
| `Content-Type` | Identifies the response media type | Helps the browser interpret content correctly |
| `Content-Length` | Indicates the message content length when provided | Useful for understanding response metadata |
| `Date` | Indicates the response date and time | Helps with traffic and event analysis |
| `Server` | May identify server software | May disclose implementation details |
| `Location` | Specifies a redirect destination | Helps analysts inspect redirect behaviour |

### Security Considerations

- Unnecessary server software disclosure should be minimized.
- Content types should be configured appropriately.
- Redirect destinations should be validated where applicable.
- Security headers such as `Content-Security-Policy`, `X-Content-Type-Options`, and `Strict-Transport-Security` provide protections against specific risks when correctly configured.
- The presence or absence of these security headers must be verified on the relevant response before drawing conclusions.

**Limitation:** This analysis documents the headers actually observed. It does not claim that unverified security headers were present or absent.

## 9. Practical 6 — GET vs POST Comparison

| Feature | GET | POST |
|---|---|---|
| Common purpose | Retrieve a resource | Submit data for processing |
| Typical data location | URL parameters may be used | Request body commonly carries submitted data |
| Form submission | Can submit data through query parameters | Commonly used for form submissions |
| Request body | Not used in the observed GET test | Form data was present in the observed POST test |
| Observed status | 200 OK | 200 OK |
| Observed response | JSON | JSON |
| Security | Does not provide encryption by itself | Does not provide encryption by itself |

### Key Findings

- GET and POST serve different purposes.
- POST does not automatically make submitted data secure.
- HTTPS protects data in transit when TLS is correctly configured.
- Status codes describe the outcome of an HTTP request; they do not independently establish whether a website is trustworthy.

## 10. HTTP Status Codes — Summary

| Status Code | Meaning | Investigation |
|---|---|---|
| 200 OK | Request succeeded | Observed with GET and POST |
| 302 Found | Temporary redirect | Observed with `/redirect/1` |
| 404 Not Found | Resource not found at the requested path | Observed with a non-existent Example Domain path |

## 11. Overall Security Analysis

This investigation demonstrated how browser-based HTTP traffic can be examined without specialized network-monitoring software.

Inspecting request methods, response codes, headers, and redirects helps analysts understand normal web communication and recognize activity that may require further investigation.

However, a single status code or header is not sufficient to determine whether a request or website is malicious. Findings must be interpreted in context.

## 12. Skills Practised

- HTTP request and response inspection
- GET and POST method comparison
- HTTP status code interpretation
- Request and response header analysis
- Redirect investigation
- Basic web traffic security analysis
- Chrome DevTools Network panel usage

## 13. Conclusion

The project provided practical experience in investigating HTTP communication between a browser and web servers. GET and POST requests, a 302 redirect, and a 404 response were observed and documented.

The investigation strengthened the understanding of HTTP methods, status codes, response headers, and their relevance to cybersecurity analysis.

## 14. Scope and Limitations

This was a basic browser-based investigation using public testing endpoints. It was not a penetration test or a comprehensive security assessment of any website.

No real user credentials or sensitive form values are included in this report.

**Project:** Project 07-B — HTTP Request & Response Investigation  
**Learning Area:** Week 7 — HTTP, HTTPS, and Web Communication  
**Portfolio Repository:** `cybersecurity-journey`

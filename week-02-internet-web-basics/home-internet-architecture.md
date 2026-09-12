# Week 2 Mini Project: My Home Internet Architecture – Browser Investigation

## Objective

To understand what happens when a website is opened from my laptop through my home network.

## My Network

- Connection Type: Wi-Fi
- Wi-Fi Protocol: Wi-Fi 4 (802.11n)
- Security Type: WPA2-Personal
- Network Band: 2.4 GHz
- Network Channel: 1
- IPv4 Address: Private IP address observed
- Default Gateway: Private network gateway observed
- DNS Server: Private DNS server observed

## Website Access Flow

Laptop → Wi-Fi → Gateway/Router → ISP → Internet → Web Server

## Step-by-Step Process

1. I enter a website address in a web browser on my laptop.
2. The laptop sends the request through the Wi-Fi connection.
3. The request is forwarded through the network gateway/router.
4. The ISP provides connectivity to the Internet.
5. The request travels through the Internet to the web server.
6. The web server processes the request and sends the website content back.
7. The browser receives the response and displays the webpage.

## Response Flow

Web Server → Internet → ISP → Gateway/Router → Wi-Fi → Laptop

## Browser Investigation

The web browser acts as the client.

The web server provides the requested website content to the client.

## Cybersecurity Relevance

Understanding the normal flow of a website request helps a cybersecurity analyst understand where security issues can occur.

Potential security concerns include:

- Compromised client devices
- Unauthorized Wi-Fi access
- Insecure network configuration
- Malicious network traffic
- Web server vulnerabilities
- Unauthorized access to web servers

## Conclusion

I investigated how a website opens through my network. The browser on my laptop acts as the client and sends a request 
through Wi-Fi, the network gateway, ISP and Internet to the web server. The web server sends a response back, which is 
displayed in the browser.

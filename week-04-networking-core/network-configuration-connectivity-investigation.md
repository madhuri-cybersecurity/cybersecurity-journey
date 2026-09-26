# Week 4 Mini Project: Network Configuration & Connectivity Investigation

## Objective

The objective of this project is to investigate my Windows network configuration and basic network connectivity using built-in command-line tools.

## Tools Used

* ipconfig
* nslookup
* ping
* tracert

## 1. IP Configuration — ipconfig

I used ipconfig to check my computer's network configuration.

### Observation

* Wi-Fi adapter was active.
* IPv4 address was assigned.
* Subnet mask was assigned.
* Default gateway was present.
* IPv6 was also configured.

### Finding

My laptop was connected to the network through Wi-Fi and had valid IP configuration.

## 2. DNS Investigation — nslookup

I used nslookup google.com to check DNS resolution.

### Observation

* DNS server responded successfully.
* google.com was resolved to multiple IP addresses.
* Both IPv4 and IPv6 addresses were returned.

### Finding

DNS resolution was working successfully.

## 3. Connectivity Test — ping

I used ping google.com to test network connectivity.

### Observation

* 4 packets were sent.
* 3 packets were received.
* 1 packet was lost.
* Packet loss was 25%.
* Average response time was 88 ms.

### Finding

The destination was reachable, but the short test showed 25% packet loss. This single test is not enough to conclude that there is a persistent network problem.

## 4. Network Path Investigation — tracert

I used tracert google.com to observe the network path toward the destination.

### Observation

* The destination was reached after 13 hops.
* Some intermediate hops returned Request timed out.
* The trace completed successfully.

### Finding

Traffic passed through multiple network hops before reaching the destination. Intermediate timeouts do not necessarily indicate a network failure because some devices may not respond to traceroute probes.

## Conclusion

I investigated my Windows network configuration and basic network connectivity using ipconfig, nslookup, ping, and tracert.

This practical helped me understand IP configuration, DNS resolution, network connectivity testing, and network path investigation.

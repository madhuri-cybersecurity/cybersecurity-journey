# Week 3 Mini Project: IP Addressing Investigation

## Objective

To understand the basic concepts of IP addressing and identify how IPv4, Public IP, Private IP, MAC Address, Localhost, 
Default Gateway, and Subnet Mask are used in network communication.

## 1. IP Address and IPv4

An IP address is a numerical address used to identify a device or network interface for network communication.

IPv4 is Internet Protocol version 4 and uses 32-bit addresses.

An IPv4 address contains four octets.

Example:

`192.168.1.10`

Each octet can have a value from 0 to 255.

## 2. IPv4 Structure

IPv4:

- 32 bits
- 4 octets
- 8 bits per octet
- Each octet ranges from 0 to 255

Example:

`192.168.1.10`

- 192 → 1st octet
- 168 → 2nd octet
- 1 → 3rd octet
- 10 → 4th octet

## 3. Public IP vs Private IP

A Public IP is an Internet-facing IP address used for communication with systems on the public Internet.

A Private IP is used within a private/local network.

### Private IPv4 Ranges

- `10.0.0.0 – 10.255.255.255`
- `172.16.0.0 – 172.31.255.255`
- `192.168.0.0 – 192.168.255.255`

### Basic Difference

| Public IP | Private IP |
|---|---|
| Internet-facing | Used inside private networks |
| Used for public Internet communication | Used for local network communication |
| Assigned to the Internet-facing side of a network | Used by devices inside a private network |

## 4. MAC Address

A MAC (Media Access Control) address is a hardware-level address associated with a network interface.

Example format:

`00:1A:2B:3C:4D:5E`

MAC addresses are mainly relevant to communication within a local network.

## 5. Localhost

Localhost refers to the same computer on which the communication or application is running.

The commonly used IPv4 loopback address is:

`127.0.0.1`

Localhost is used for communication with the same computer.

## 6. Default Gateway

A Default Gateway is the device or network address used to send traffic to other networks.

In a typical home network, the router usually acts as the default gateway.

Basic flow:

Laptop → Default Gateway → Other Network → Internet

## 7. Basic Subnet Mask Concept

A subnet mask is used with an IPv4 address to determine the network portion and host portion of the address.

Example:

IP Address: `192.168.1.10`

Subnet Mask: `255.255.255.0`

The subnet mask helps determine whether a destination belongs to the local network or another network.

## 8. Practical Investigation

The `ipconfig` command can be used in Windows to view network configuration information.

Important fields include:

- IPv4 Address
- Subnet Mask
- Default Gateway

The `ipconfig /all` command provides additional network interface information, including the Physical Address (MAC address).

## 9. Cybersecurity Relevance

Understanding IP addressing is important for cybersecurity because IP and network information can appear in:

- Firewall logs
- Security alerts
- Network traffic
- Incident investigations
- Network monitoring
- Packet captures

A cybersecurity analyst can use this information to understand the source, destination, and network location of communication.

## Security Note

Actual IP addresses, MAC addresses, and other personal network information should not be published in a public GitHub repository.

## Conclusion

This project helped me understand the basic structure and purpose of IP addressing.

I learned how IPv4 addresses are structured, the difference between Public and Private IP addresses, the purpose of MAC addresses and Localhost, and the role of the Default Gateway and Subnet Mask in network communication.

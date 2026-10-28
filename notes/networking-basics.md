# Networking Basics Lab

- **Type:** Beginner Cybersecurity / Networking
- **Environment:** Windows PowerShell
- **Tools:** `ipconfig`, `ping`
- **Status:** Completed

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Core Concepts](#2-core-concepts)
3. [Network Configuration](#3-network-configuration)
4. [Connectivity Tests](#4-connectivity-tests)
5. [Commands Used](#5-commands-used)
6. [Key Takeaways](#6-key-takeaways)
7. [Cybersecurity Relevance](#7-cybersecurity-relevance)
8. [Conclusion](#8-conclusion)

---

## 1. Introduction

Networking is a fundamental concept in cybersecurity. A computer network allows devices to communicate, exchange data, and access shared resources.

Understanding networking is important for cybersecurity because many security events occur through network communication.

---

## 2. Core Concepts

### Computer Network

A computer network is a group of computers and devices connected together so they can communicate and share information.

**Examples of network devices:**

- Computers
- Smartphones
- Servers
- Routers
- Printers
- Access points

### IP Address

An IP (Internet Protocol) address is a numerical address used to identify a device on a network. It allows devices to communicate with each other.

### Subnet Mask

A subnet mask determines which part of an IP address represents the network and which part represents the host.

### Default Gateway

The default gateway is usually the router or network device that allows a computer to communicate with networks outside its local network.

### Ping

`ping` is a network diagnostic command used to test whether a device can communicate with another device. It sends packets to a destination and measures whether the destination responds.

Ping can provide information such as:

- Packet loss
- Response time
- Network connectivity
- Latency

---

## 3. Network Configuration

The following configuration was observed during the lab:

| Parameter | Value |
|---|---|
| IPv4 Address | `172.16.107.127` |
| Subnet Mask | `255.255.248.0` |
| Default Gateway | `172.16.104.1` |
| Network Connection | Wi-Fi |

The IPv4 address identifies the computer on the local network.

---

## 4. Connectivity Tests

### Results Summary

| Test | Command | Sent | Received | Lost | Packet Loss | Average Time |
|---|---|---|---|---|---|---|
| Localhost | `ping 127.0.0.1` | 4 | 4 | 0 | 0% | 0 ms |
| Default Gateway | `ping 172.16.104.1` | 4 | 3 | 1 | 25% | 1155 ms |
| Internet | `ping google.com` | 4 | 3 | 1 | 25% | 234 ms |

### 4.1 Localhost Test

```powershell
ping 127.0.0.1
```

**Result:** 4 packets sent, 4 received, 0 lost (0% loss). Average time: 0 ms.

**Analysis:** The localhost test was successful. The address `127.0.0.1` refers to the local computer itself. A successful response indicates that the computer's local TCP/IP networking stack is functioning correctly.

### 4.2 Default Gateway Test

```powershell
ping 172.16.104.1
```

**Result:** 4 packets sent, 3 received, 1 lost (25% loss). Average time: 1155 ms.

**Analysis:** The computer was able to communicate with the default gateway, but the test showed packet loss and relatively high latency. This may indicate temporary network congestion, wireless interference, or other network conditions. A single four-packet test is not enough to determine the exact cause.

### 4.3 Internet Connectivity Test

```powershell
ping google.com
```

**Result:** 4 packets sent, 3 received, 1 lost (25% loss). Average time: 234 ms.

**Analysis:** The computer received responses from Google, which confirms that it was able to reach an Internet destination during the test. The test also showed 25% packet loss and some latency.

---

## 5. Commands Used

The following Windows commands were used during this lab:

| Purpose | Command |
|---|---|
| Display network configuration | `ipconfig` |
| Test local connectivity | `ping 127.0.0.1` |
| Test gateway connectivity | `ping 172.16.104.1` |
| Test Internet connectivity | `ping google.com` |

---

## 6. Key Takeaways

- Computer networks and how devices communicate
- IPv4 addresses, subnet masks, and default gateways
- The localhost address and what it tests
- Network connectivity, packet loss, and latency
- How to use `ping` for basic Windows network troubleshooting

---

## 7. Cybersecurity Relevance

Networking knowledge is essential in cybersecurity. Security professionals need to understand how devices communicate before they can effectively analyze network traffic, identify suspicious connections, investigate incidents, or secure systems.

This lab provides a foundation for future cybersecurity labs involving:

- Network scanning
- DNS
- TCP/IP
- Ports and protocols
- Packet analysis
- Network security
- Incident investigation

---

## 8. Conclusion

This lab provided practical experience with basic network configuration and connectivity testing on Windows.

The exercises demonstrated how to identify a computer's IP address, subnet mask, and default gateway, and how to use the `ping` command to test local, gateway, and Internet connectivity.

This is the first step toward developing practical networking and cybersecurity skills.

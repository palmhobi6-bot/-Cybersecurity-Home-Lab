Networking Basics

1. Introduction

Networking is a fundamental concept in cybersecurity. A computer network allows devices to communicate, exchange data, and access shared resources.

Understanding networking is important for cybersecurity because many security events occur through network communication.

---

2. What is a Computer Network?

A computer network is a group of computers and devices connected together so they can communicate and share information.

Examples of Network Devices

- Computers
- Smartphones
- Servers
- Routers
- Printers
- Access points

---

3. What is an IP Address?

An IP (Internet Protocol) address is a numerical address used to identify a device on a network.

An IP address allows devices to communicate with each other.

Example

172.16.107.127

This is the IPv4 address assigned to my computer during this lab.

---

4. IPv4 Address

During this lab, the computer was assigned the following IPv4 address:

172.16.107.127

The IPv4 address identifies my computer on the local network.

---

5. Subnet Mask

The subnet mask used during this lab was:

255.255.248.0

A subnet mask helps determine which part of an IP address represents the network and which part represents the host.

---

6. Default Gateway

The default gateway identified during the lab was:

172.16.104.1

The default gateway is usually the router or network device that allows a computer to communicate with networks outside its local network.

---

7. Network Configuration

The network configuration observed during the lab was:

Parameter| Value
IPv4 Address| "172.16.107.127"
Subnet Mask| "255.255.248.0"
Default Gateway| "172.16.104.1"
Network Connection| Wi-Fi

---

8. Ping

"ping" is a network diagnostic command used to test whether a device can communicate with another device.

It sends packets to a destination and measures whether the destination responds.

Ping can provide information such as:

- Packet loss
- Response time
- Network connectivity
- Latency

---

9. Localhost Test

Command

ping 127.0.0.1

Result

Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
Average = 0ms

Analysis

The localhost test was successful.

The address "127.0.0.1" refers to the local computer itself. A successful response indicates that the computer's local TCP/IP networking stack is functioning correctly.

---

10. Default Gateway Test

Command

ping 172.16.104.1

Result

Packets: Sent = 4
Received = 3
Lost = 1
Packet Loss = 25%
Average = 1155ms

Analysis

The computer was able to communicate with the default gateway, but the test showed packet loss and relatively high latency.

This may indicate temporary network congestion, wireless interference, or other network conditions.

A single four-packet test is not enough to determine the exact cause.

---

11. Internet Connectivity Test

Command

ping google.com

Result

Packets: Sent = 4
Received = 3
Lost = 1
Packet Loss = 25%
Average = 234ms

Analysis

The computer successfully received responses from Google, which confirms that the computer was able to reach an Internet destination during the test.

The test also showed 25% packet loss and some latency.

---

12. Commands Used

The following Windows commands were used during this laboratory exercise:

Display Network Configuration

ipconfig

Test Local Connectivity

ping 127.0.0.1

Test Gateway Connectivity

ping 172.16.104.1

Test Internet Connectivity

ping google.com

---

13. Key Concepts Learned

During this lab, I learned the basic concepts of:

- Computer networks
- IPv4 addresses
- Subnet masks
- Default gateways
- Localhost
- Network connectivity
- Ping
- Packet loss
- Latency
- Basic Windows network troubleshooting

---

14. Cybersecurity Relevance

Networking knowledge is essential in cybersecurity.

Security professionals need to understand how devices communicate before they can effectively analyze network traffic, identify suspicious connections, investigate incidents, or secure systems.

This laboratory exercise provides a foundation for future cybersecurity labs involving:

- Network scanning
- DNS
- TCP/IP
- Ports and protocols
- Packet analysis
- Network security
- Incident investigation

---

15. Conclusion

This laboratory provided practical experience with basic network configuration and connectivity testing on Windows.

The exercises demonstrated how to identify a computer's IP address, subnet mask, and default gateway, as well as how to use the "ping" command to test local, gateway, and Internet connectivity.

This is the first step toward developing practical networking and cybersecurity skills.

---

Lab Type: Beginner Cybersecurity / Networking
Environment: Windows PowerShell
Tools: "ipconfig", "ping"
Status: Completed

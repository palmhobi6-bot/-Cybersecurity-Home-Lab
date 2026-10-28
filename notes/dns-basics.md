# DNS Basics Lab

- **Type:** Beginner Cybersecurity / Networking
- **Environment:** Windows PowerShell
- **Tools:** `nslookup`, `ipconfig`
- **Status:** Completed

---

## 1. Introduction

DNS (Domain Name System) translates human-readable domain names, such as `google.com`, into IP addresses that computers use to communicate.

DNS matters in cybersecurity because many attacks involve it: phishing domains, DNS spoofing, and malware contacting suspicious domains.

---

## 2. Core Concepts

| Term | Meaning |
|---|---|
| Domain name | A readable name for a service (example: `google.com`) |
| DNS server | A server that answers name-resolution requests |
| A record | Maps a domain name to an IPv4 address |
| CNAME record | An alias that points one domain name to another |
| MX record | Identifies the mail servers of a domain |
| TTL (Time To Live) | How long, in seconds, an answer can stay in the cache |
| DNS cache | Local storage of recent DNS answers |

---

## 3. DNS Lookup Tests

### 3.1 Basic lookup

```powershell
nslookup google.com
```

**Result:**

- DNS server used: `ns1.aeronetonline.in` (`103.143.168.2`)
- Answer type: non-authoritative
- Domain: `google.com`
- IPv4 addresses returned: `142.250.143.100`, `142.250.143.113`, `142.250.143.101` (and 3 more)
- IPv6 addresses returned: `2404:6800:4000:100c::64`, `2404:6800:4000:100c::71` (and 2 more)

**Analysis:** The computer asked its configured DNS server to resolve the domain name and received several IPv4 and IPv6 addresses. The answer is non-authoritative, which means it came from a server that holds a cached copy, not from Google's own DNS server.

### 3.2 Mail server lookup

```powershell
nslookup -type=MX google.com
```

**Result:**

- DNS server used: `ns1.aeronetonline.in` (`103.143.168.2`)
- Answer type: non-authoritative
- MX record: preference `10`, mail exchanger `smtp.google.com`

**Analysis:** MX records show which servers receive email for a domain. The preference value (10) indicates the priority of the mail server: lower values are tried first. Security analysts check these records when investigating phishing or email spoofing.

### 3.3 Using a different DNS server

```powershell
nslookup google.com 8.8.8.8
```

**Result:**

- DNS server used: `dns.google` (`8.8.8.8`)
- Answer type: non-authoritative
- IPv4 addresses returned: `142.250.143.102`, `142.250.143.113`, `142.250.143.101` (and 3 more)
- IPv6 addresses returned: `2404:6800:4000:100c::64`, `2404:6800:4000:100c::71` (and 2 more)
- The same addresses were returned as with the default DNS server, in a different order

**Analysis:** The same request was sent to a public DNS server instead of the default one. Both servers returned the same set of addresses, which shows the default DNS server was not altering the answer for this domain. Comparing answers from different servers helps detect DNS problems or tampering.

### 3.4 DNS cache

```powershell
ipconfig /displaydns
```

This command requires an administrator PowerShell window.

**Result (extract):**

| Record name | Type | TTL (seconds) | Data |
|---|---|---|---|
| `time.windows.com` | CNAME (5) | 52 | `twc.trafficmanager.net` |
| `twc.trafficmanager.net` | A (1) | 52 | `40.81.94.65` |
| `a.nel.cloudflare.com` | A (1) | 13999 | `35.190.80.1` |

**Analysis:** Windows keeps recent DNS answers in a local cache to speed up future requests. The cache shows an alias (CNAME) pointing to another name, which in turn resolves to an IPv4 address (A record). The TTL value shows how long each entry stays valid before the computer must ask the DNS server again. Reading the cache is also a way to see which domains a machine has recently contacted, which is useful during an investigation.

---

## 4. Commands Used

| Purpose | Command |
|---|---|
| Resolve a domain name | `nslookup google.com` |
| Find mail servers | `nslookup -type=MX google.com` |
| Query a specific DNS server | `nslookup google.com 8.8.8.8` |
| View the local DNS cache (administrator) | `ipconfig /displaydns` |

---

## 5. Key Takeaways

- DNS translates domain names into IP addresses
- How to query A and MX records with `nslookup`
- The difference between the default DNS server and a public one
- What a CNAME record and a TTL are
- How to read the local DNS cache

---

## 6. Cybersecurity Relevance

DNS is a common target and a common source of evidence. Understanding it helps with:

- Identifying suspicious or newly registered domains
- Recognizing DNS spoofing and cache poisoning
- Investigating phishing and malware communication
- Analyzing network traffic

---

## 7. Conclusion

This lab provided hands-on practice with DNS name resolution on Windows, using `nslookup` and `ipconfig` to query records, compare DNS servers, and inspect the local cache.

It builds on the previous Networking Basics lab and prepares the ground for packet analysis and network scanning labs.

# 📝 Notes 018 – Linux Networking Fundamentals II
### Quick Revision Guide

---

# 1. Network Interface

A Network Interface is the communication point through which Linux sends and receives packets.

Types:

- Loopback (lo)
- Ethernet (eth0)
- Wi-Fi (wlan0)
- Virtual Interfaces

Useful Command

```bash
ip link
```

Shows

- Interface Name
- MAC Address
- State
- MTU

---

# 2. Loopback Interface

Interface

```
lo
```

Address

```
127.0.0.1
```

Purpose

Allows the computer to communicate with itself.

Packets never leave the machine.

---

# 3. MAC Address

Example

```
00:15:5d:a6:8d:ee
```

Characteristics

- Physical Hardware Address
- Unique for every Network Card
- Layer 2 Address

---

# 4. IP Address

Example

```
172.20.136.56
```

Purpose

Identifies a device on a network.

Types

- Private
- Public
- IPv4
- IPv6

Command

```bash
ip addr
```

---

# 5. Hostname

Displays system name.

Command

```bash
hostname
```

Display local IP

```bash
hostname -I
```

---

# 6. Routing Table

Command

```bash
ip route
```

Purpose

Determines where packets are sent.

Important Entry

```
default via <gateway>
```

Meaning

Unknown destinations are forwarded to the Default Gateway.

---

# 7. Default Gateway

Acts as the router between different networks.

Without a gateway,

devices cannot access the internet.

---

# 8. DNS (Domain Name System)

Purpose

Converts

```
google.com
```

into

```
IP Address
```

Command

```bash
getent hosts google.com
```

---

# 9. DNS Configuration

File

```bash
cat /etc/resolv.conf
```

Contains

```
nameserver
```

which Linux uses for DNS lookups.

---

# 10. Hosts File

Location

```bash
/etc/hosts
```

Purpose

Local hostname mappings.

Linux checks this file before querying DNS.

---

# 11. curl

Purpose

Communicates with web servers.

Useful Commands

```bash
curl https://example.com
```

```bash
curl -I https://example.com
```

---

# 12. wget

Purpose

Downloads files from servers.

Example

```bash
wget https://example.com
```

Automatically saves downloaded content.

---

# 13. HTTP Response

Contains

- Status Code
- Headers
- Content

Example

```
HTTP/2 200 OK
```

---

# 14. Common Status Codes

200 → Success

301 → Permanent Redirect

302 → Temporary Redirect

403 → Forbidden

404 → Not Found

500 → Internal Server Error

---

# 15. Networking Workflow

```
Application

↓

Network Interface

↓

IP Address

↓

Routing Table

↓

Gateway

↓

DNS

↓

HTTP Request

↓

HTTP Response
```

---

# Commands Learned

```bash
ip link
ip addr
hostname
hostname -I
ip route
route -n
cat /etc/resolv.conf
cat /etc/hosts
getent hosts google.com
curl -I
curl
wget
```

---

# Key Takeaways

- Linux communicates using Network Interfaces.
- Every device requires an IP Address.
- Routers forward packets outside the local network.
- DNS converts names into IP addresses.
- curl is used for communication.
- wget is used for downloading.
- HTTP Responses always contain headers before content.
- Understanding Linux networking is essential before learning SSL/TLS, Wireshark, APIs, Web Security and Penetration Testing.

---

**Status:** ✅ Revision Notes Completed
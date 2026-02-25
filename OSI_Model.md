# 🧠 OSI Model – 7 Layers Overview

The OSI (Open Systems Interconnection) Model is a conceptual framework used to understand and standardize how different networking systems communicate.

It consists of **7 layers**, each responsible for a specific part of communication.

---

## 📊 OSI Model Layers Summary

| Layer | Name          | Main Purpose                         |
|-------|--------------|--------------------------------------|
| 7     | Application  | User-level protocols                 |
| 6     | Presentation | Encryption / Encoding                |
| 5     | Session      | Session management                   |
| 4     | Transport    | End-to-end communication & ports     |
| 3     | Network      | Routing & IP addressing              |
| 2     | Data Link    | MAC addressing & local delivery      |
| 1     | Physical     | Hardware transmission of bits        |

---

# 🔹 Layer 1 – Physical Layer

### 🎯 Purpose
Moves raw bits (0s and 1s) through a physical medium.

This layer deals only with electrical signals, voltages, cables, and hardware transmission.

👉 No logical addressing exists here — only signals.

### 🔌 Technologies

- Ethernet Physical Standards (100BASE-TX, 10GBASE-SR)
- DSL
- ISDN
- Bluetooth (physical component)
- USB
- Fiber optics
- RS-232

---

# 🔹 Layer 2 – Data Link Layer

### 🎯 Purpose
Handles MAC addressing and local network communication.

It ensures reliable communication within the same local network (LAN).

### 📡 Protocols & Technologies

- Ethernet (IEEE 802.3)
- Wi-Fi (IEEE 802.11)
- ARP
- RARP
- VLAN (802.1Q)
- STP
- CDP
- LLDP
- PPP
- Frame Relay
- MPLS (between Layer 2 and Layer 3)

---

# 🔹 Layer 3 – Network Layer

### 🎯 Purpose
Handles logical addressing and routing between networks.

This is where IP addressing exists.

### 🌍 Core Protocols

- IP (IPv4 / IPv6)
- ICMP
- IPsec
- IGMP
- RIP
- OSPF
- BGP
- EIGRP

---

# 🔹 Layer 4 – Transport Layer

### 🎯 Purpose
Provides end-to-end communication and manages ports.

Responsible for:
- Reliability
- Flow control
- Error handling

### 🔁 Protocols

- TCP
- UDP
- SCTP
- DCCP

---

# 🔹 Layer 5 – Session Layer

### 🎯 Purpose
Manages sessions between applications.

Responsible for:
- Session establishment
- Session maintenance
- Session termination

### 🔗 Protocols

- NetBIOS Session Service
- RPC
- PPTP
- SIP (session control component)

> Note: In modern systems, Layers 5–7 are often merged practically.

---

# 🔹 Layer 6 – Presentation Layer

### 🎯 Purpose
Handles encryption, compression, and encoding.

Ensures data is properly formatted for the application layer.

### 🔐 Protocols & Formats

- SSL
- TLS
- MIME
- JPEG / PNG
- ASCII
- UTF-8

---

# 🔹 Layer 7 – Application Layer

### 🎯 Purpose
Provides user-level communication protocols.

This is the largest and most visible layer.

---

## 🌐 Web Protocols

- HTTP
- HTTPS
- WebSocket

---

## 📁 File Transfer

- FTP
- FTPS
- SFTP
- TFTP

---

## 📧 Email

- SMTP
- POP3
- IMAP

---

## 💻 Remote Access

- SSH
- Telnet
- RDP

---

## 📊 Network Management

- SNMP
- NTP
- LDAP

---

## 🌎 Name Resolution

- DNS
- mDNS

---

## 📂 File Sharing

- SMB
- NFS

---

## 🔐 Others

- DHCP
- Kerberos
- MQTT
- CoAP

---

# ✅ Conclusion

The OSI Model provides a structured way to understand how networks operate, from physical hardware transmission (Layer 1) up to user-level application protocols (Layer 7).

Understanding these layers is fundamental for:

- Networking
- Cybersecurity
- Penetration Testing
- System Administration
- Cloud Engineering

---

## ✍ Author

Muhammad Usman  
Cybersecurity Learner | Networking Enthusiast

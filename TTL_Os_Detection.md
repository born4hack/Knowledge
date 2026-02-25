# TTL-Based Operating System Detection

## Introduction

TTL (Time To Live) analysis is a reconnaissance technique used in penetration testing and Capture The Flag (CTF) platforms such as Hack The Box (HTB) to estimate a target system's operating system.

When a host responds to an ICMP (ping) request or TCP packet, it includes a TTL value in the IP header. Since different operating systems use different default TTL values, this information can be used to make an educated guess about the target OS during initial enumeration.

---

## What is TTL?

TTL (Time To Live) is an 8-bit field in the IPv4 header.

### Technical Definition

TTL defines the maximum number of routing hops a packet can traverse before being discarded. It is designed to prevent packets from circulating indefinitely due to routing loops.

### How TTL Works

1. The sender sets an initial TTL value (based on the operating system default).
2. Each router that forwards the packet decreases the TTL value by 1.
3. If TTL reaches 0, the packet is dropped.
4. The receiving system replies with its own TTL value.

---

## Why TTL is Useful in OS Detection

Different operating systems assign different default TTL values when sending packets.

By observing the TTL value in a response packet, we can estimate:

- The likely operating system
- The approximate number of hops between attacker and target

---

## Default TTL Values by Operating System

| Operating System | Default TTL |
|------------------|------------|
| Linux / Unix     | 64         |
| Windows          | 128        |
| Network Devices (Routers, Cisco) | 255 |

These values represent the initial TTL set by the OS before the packet travels across the network.

---

## Example: Nmap Host Discovery

Run a host discovery scan:

```bash
sudo nmap 10.129.2.18 -sn -PE --packet-trace --disable-arp-ping
```

Example response:

```text
RCVD ICMP Echo reply ... ttl=128
```

---

## OS Guessing Logic

Observed value:

```text
ttl=128
```

### Analysis

- Windows default TTL = 128  
- Linux default TTL = 64  

### Conclusion

> The target system is likely running Windows.

---

## Accounting for Hop Count

Since TTL decreases by 1 per router hop, the observed TTL may be slightly lower than the original value.

### Common Scenarios

| Observed TTL | Likely Original TTL | Likely OS |
|--------------|--------------------|-----------|
| 128          | 128                | Windows   |
| 127          | 128                | Windows   |
| 64           | 64                 | Linux     |
| 63           | 64                 | Linux     |

In Hack The Box environments, typical observations are:

- TTL ≈ 127–128 → Windows  
- TTL ≈ 63–64 → Linux  

---

## Verification with Nmap OS Detection

For more reliable OS fingerprinting:

```bash
sudo nmap -O 10.129.2.18
```

Or perform an aggressive scan:

```bash
sudo nmap -A 10.129.2.18
```

TTL analysis should be combined with:

- Open port enumeration  
- Service version detection  
- Banner grabbing  
- SMB or SSH fingerprinting  

---

## Limitations of TTL-Based Detection

TTL-based OS detection is not 100% accurate because:

- Firewalls may modify TTL values  
- Custom OS configurations may change defaults  
- Network routing distance affects observed TTL  
- Some systems randomize or normalize TTL values  

TTL provides an estimation, not definitive proof.

---

## Quick Reference (HTB Style)

- TTL around 128 → Likely Windows  
- TTL around 64 → Likely Linux  
- TTL around 255 → Likely Network Device  

---

## Conclusion

TTL analysis is a fast and practical technique for estimating a target operating system during early reconnaissance. While it should not be relied upon as the sole method of OS detection, it is widely used in penetration testing and CTF environments for quick identification.

---

## Author

Muhammad Usman  
Cybersecurity Learner | Penetration Testing Enthusiast

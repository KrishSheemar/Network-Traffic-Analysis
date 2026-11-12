# Network Traffic Analysis & Packet Inspection

A hands-on cybersecurity lab project focused on network traffic capture, packet inspection, DNS analysis and TCP communication using Wireshark, tcpdump, Kali Linux and Metasploitable 2.

## Project Overview

This project involved capturing and analysing network traffic between Kali Linux and Metasploitable 2 in an isolated Oracle VirtualBox lab environment.

The objective was to understand network communication by examining DNS queries and responses, TCP three-way handshakes, IP addresses, port numbers and packet-level details.

## Tools & Technologies

- Kali Linux
- Wireshark
- tcpdump
- Metasploitable 2
- Oracle VirtualBox
- TCP/IP
- DNS, UDP, TCP and ICMP

## Lab Environment

| **Component** | **Configuration** |
| -------------- | ----------------- |
| Analysis Machine | Kali Linux |
| Target | Metasploitable 2 |
| Virtualisation | Oracle VirtualBox |
| Kali IP | 192.168.56.102 |
| Target IP | 192.168.56.103 |
| Network Interface | eth1 |
| Assessment | Network traffic analysis |

## Tasks Performed

1. Captured network traffic using Wireshark and tcpdump.
2. Analysed DNS queries and responses between the lab machines.
3. Inspected DNS resolution failure (`SERVFAIL`).
4. Examined TCP communication on port 80.
5. Analysed the TCP three-way handshake (SYN, SYN-ACK and ACK).
6. Identified source and destination IP addresses, port numbers and protocols.
7. Documented packet-level observations and findings.

## Key Findings

- Captured network traffic between Kali Linux and Metasploitable 2.
- Identified DNS communication over UDP port 53.
- Observed a DNS `SERVFAIL` response with no answer records.
- Captured the TCP three-way handshake on port 80.
- Confirmed successful TCP connection establishment.
- Observed additional network protocols, including ARP, ICMPv6 and DHCP.

## Example Commands

```bash
# Start packet capture using tcpdump
sudo tcpdump -i any -nn -s 0 -w network-traffic.pcap

# Perform DNS lookup
nslookup example.com 192.168.56.103

# Test TCP port 80 connectivity
nc -vn 192.168.56.103 80

# Start Wireshark
sudo wireshark
```

**Wireshark Display Filters**

```text
# DNS traffic
dns

# TCP traffic on port 80
tcp.port == 80

# TCP SYN packets
tcp.flags.syn == 1

# Traffic involving the target
ip.addr == 192.168.56.103
```

## Security & Troubleshooting Insights

- DNS response codes help identify name resolution problems.
- TCP flags help understand connection establishment and termination.
- Source and destination ports help identify communicating services.
- Packet inspection helps investigate network connectivity issues.
- Network traffic monitoring supports troubleshooting and security analysis.

## Project Documentation

See the `screenshots/` directory for DNS analysis and TCP handshake evidence.

See the `captures/` directory for saved packet capture files, if included.

## Scope & Disclaimer

This project was conducted in an isolated, authorised VirtualBox lab using Kali Linux and Metasploitable 2.

The assessment covered packet capture, DNS analysis and TCP handshake inspection only. Successful external DNS resolution and TLS analysis are not claimed.

Educational purposes only.

# Lab Report — Tcpdump Packet Capture

**Title:** Network Packet Capture & Analysis (DNS + IPv6)  
**Author:** Damilola Yusuf Atobiloye  
**Date:** 2025-10-31

---

## Objective
Capture DNS and IPv6 neighbor discovery packets.

## Environment
- Kali Linux (tcpdump)
- Capture file: dns-ndisc.pcap (500 packets)

---

## Commands & Outputs
sudo tcpdump -i eth0 -n -vv 'port 53 or ip6' -w dns-ndisc.pcap -c 500

Output:
500 packets captured, 0 dropped.

sudo tcpdump -r dns-ndisc.pcap -n -vv | sed -n '1,200p' > dns-ndisc-snippet.txt

Excerpt:
ICMP6 router advertisement advertising prefix fd17:625c:f037:2::/64

---

## Analysis
Contains DNS queries/responses and IPv6 advertisements. Use Wireshark/tshark for deeper analysis.

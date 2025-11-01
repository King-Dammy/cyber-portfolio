# Lab Report — Nmap Scans

**Title:** Nmap Host Discovery & Service Enumeration  
**Author:** Damilola Yusuf Atobiloye  
**Date:** 2025-10-31

---

## Objective
Use Nmap to discover live hosts on the lab subnet and enumerate services, focusing on DNS (port 53) and common service checks.

## Environment
- Kali Linux (Nmap 7.95)
- Target network: 10.0.2.0/24 (VirtualBox lab)

---

## Commands & Outputs

### 1) Host discovery (ping scan)
sudo nmap -sn 10.0.2.0/24

Excerpt:
Nmap scan report for 10.0.2.2 — Host is up  
Nmap scan report for 10.0.2.3 — Host is up  
Nmap scan report for 10.0.2.15 — Host is up

### 2) TCP service detection — DNS
sudo nmap -sV -p 53 10.0.2.3 -vv

Excerpt:
53/tcp open domain dnsmasq 2.78

### 3) UDP DNS scan
sudo nmap -sU -p 53 10.0.2.3 -vv

Excerpt:
53/udp open domain

### 4) IPv6 discovery
sudo nmap -6 -sn fd17:625c:f037:2::/120

Excerpt:
Two IPv6 hosts responded.

---

## Analysis
Host discovery shows three live addresses; service enumeration confirmed dnsmasq on 10.0.2.3 (TCP/UDP 53). IPv6 neighbor discovery found two responsive addresses.

## Recommendations
Run scheduled Nmap scans, correlate with tcpdump and logs, and harden DNS services.

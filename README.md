# Task 4 - Firewall Setup and Testing (Kali Linux)

## Objective
Configure and test firewall rules on Kali Linux using UFW (Uncomplicated Firewall). Block/allow specific ports, verify the changes, and document the process.

## Steps Performed
1. Installed and enabled UFW.
2. Listed current firewall rules.
3. Blocked inbound Telnet (port 23).
4. Allowed SSH (port 22) to prevent lockout.
5. Tested the Telnet block using `telnet`.
6. Removed the Telnet block to restore original settings.
7. Documented commands used.
8. Summarized how firewall filters traffic.

## Commands Used
```bash
sudo apt update
sudo apt install ufw -y
sudo ufw enable
sudo ufw status numbered
sudo ufw deny 23/tcp
sudo ufw allow 22/tcp
telnet localhost 23
sudo ufw delete deny 23/tcp
```

## Summary
A firewall monitors and controls network traffic based on predefined rules. In this task, we used UFW to block an insecure service (Telnet) and allow a secure service (SSH). Blocking unused and unsafe ports reduces the attack surface and improves network security.

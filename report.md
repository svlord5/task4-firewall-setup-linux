# Firewall Configuration Report - Kali Linux (Task 4)

## Tools Used
- **Kali Linux**
- **UFW (Uncomplicated Firewall)**

## Procedure
1. **Open firewall configuration tool**
   - Installed and enabled UFW.
2. **List current firewall rules**
   - Used `sudo ufw status numbered`.
3. **Block inbound traffic on port 23 (Telnet)**
   - `sudo ufw deny 23/tcp`.
4. **Test the block**
   - Verified with `telnet localhost 23` (connection refused).
5. **Allow SSH (Port 22)**
   - `sudo ufw allow 22/tcp`.
6. **Remove test block rule**
   - `sudo ufw delete deny 23/tcp`.
7. **Document commands used**
   - All commands listed in the [**command.txt**](https://github.com/svlord5/task4-firewall-setup-linux/blob/main/commands.txt)
8. **Summarize firewall filtering**
   - Firewalls act as gatekeepers, inspecting packets and allowing/blocking based on rules.

## Commands and Their Purpose

| Command | Description |
|---------|-------------|
| `sudo apt update` | Updates the package list from repositories. |
| `sudo apt install ufw -y` | Installs UFW without prompting for confirmation. |
| `sudo ufw enable` | Activates UFW firewall protection. |
| `sudo ufw status numbered` | Shows the current firewall rules with numbering. |
| `sudo ufw deny 23/tcp` | Blocks inbound TCP traffic on port 23 (Telnet). |
| `sudo ufw allow 22/tcp` | Allows inbound TCP traffic on port 22 (SSH). |
| `telnet localhost 23` | Tests the Telnet connection to verify block status. |
| `sudo ufw delete deny 23/tcp` | Removes the deny rule for port 23. |

## Port Details and Action

| Port | Service | Action Taken | Reason |
|------|---------|--------------|--------|
| 23 | Telnet | Blocked | Telnet is insecure and sends data in plaintext. |
| 22 | SSH | Allowed | SSH is secure and needed for remote access. |

## Observations
- Blocking Telnet was successful — connection attempts were denied.
- SSH remained accessible after allowing it explicitly.
- Removing the deny rule restored normal functionality.

## Conclusion
Firewalls are critical for security. Using UFW, even beginners can configure basic rules to protect their systems.

# Home-lab-setup
# 🧪 Home Cybersecurity Lab Setup

## 🔧 Overview

This document describes my local virtual lab built for hands-on cybersecurity practice. The lab is fully isolated and designed to simulate real-world offensive and defensive scenarios, including pentesting, scanning, exploitation, traffic capture, and network analysis.

---

## 💻 Host System

- **OS**: Windows 11 Pro
- **Processor**: Intel i7 / AMD Ryzen (8+ cores)
- **RAM**: 32 GB
- **Hypervisor**: VMware Workstation Pro 17
- **Network Mode**: NAT (isolated lab, no internet exposure)

---

## 🖥️ Virtual Machines

| VM Name         | OS/Platform      | Role        | Notes |
|------------------|------------------|-------------|-------|
| Kali Linux       | Debian-based     | Attacker    | Nmap, Metasploit, Hydra, Wireshark |
| Metasploitable 2 | Ubuntu (legacy)  | Vulnerable Target | Contains known vulnerabilities for exploitation |
| Windows 11       | Windows          | Target / Analyst | Modern OS to test against, or use for Wireshark analysis |

---

## 🌐 Network Configuration

- All machines are on the **same NAT virtual network**.
- Static or DHCP-assigned IPs in the range `192.168.X.X`.
- Internet access is disabled to avoid real-world exposure.

---

## 🧰 Tools Installed

### Kali Linux
- Nmap
- Metasploit Framework
- Hydra
- Wireshark
- Netcat

### Metasploitable 2
- Open vulnerable services (FTP, SSH, Apache, MySQL, etc.)

### Windows 11
- Wireshark (for passive analysis)
- Standard Windows Firewall enabled
- No antivirus, but patched and snapshot for safety

---

## 🗺️ Network Diagram
[Kali Linux VM] ─┐
│ (192.168.88.X subnet via NAT)
[Windows 11 VM] ─┼──> Virtual Network (NAT)
│
[Metasploitable] ┘

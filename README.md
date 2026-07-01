# 🔍 Task 1: Scan Your Local Network for Open Ports

![Ubuntu](https://img.shields.io/badge/OS-Ubuntu%2026.04-E95420?logo=ubuntu\&logoColor=white)
![Nmap](https://img.shields.io/badge/Tool-Nmap-00457C)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Cybersecurity](https://img.shields.io/badge/Domain-Cyber%20Security-blue)

## 📌 Objective

The objective of this task is to perform **basic network reconnaissance** by scanning the local network for active hosts and open TCP ports using **Nmap**. This exercise helps identify exposed network services and understand potential security risks associated with open ports.

---

## 🛠️ Tools Used

* **Operating System:** Ubuntu 26.04 LTS
* **Network Scanner:** Nmap
* **Packet Analyzer (Optional):** Wireshark
* **Terminal:** Bash

---

## 📋 Task Steps

### 1. Install Nmap

```bash
sudo apt update
sudo apt install nmap -y
```

Verify installation:

```bash
nmap --version
```

---

### 2. Find the Local Network Range

```bash
ip addr
```

or

```bash
ip route
```

Example:

```text
192.168.1.0/24
```

---

### 3. Perform a TCP SYN Scan

```bash
sudo nmap -sS 192.168.1.0/24
```

---

### 4. Save Scan Results

```bash
sudo nmap -sS 192.168.1.0/24 -oN scan_results.txt
```

Optional (save all output formats):

```bash
sudo nmap -sS 192.168.1.0/24 -oA network_scan
```

---

## 📊 Sample Scan Output

```text
Starting Nmap 7.97

Nmap scan report for 192.168.1.1
Host is up.

PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
443/tcp  open  https

Nmap scan report for 192.168.1.10
Host is up.

PORT     STATE SERVICE
445/tcp  open  microsoft-ds

Nmap done: 256 IP addresses (2 hosts up)
```

---

## 📌 Common Ports and Services

| Port | Service | Description          |
| ---: | ------- | -------------------- |
|   22 | SSH     | Secure remote login  |
|   53 | DNS     | Domain Name System   |
|   80 | HTTP    | Web server           |
|  443 | HTTPS   | Secure web server    |
|  445 | SMB     | Windows file sharing |
| 3306 | MySQL   | Database server      |
| 3389 | RDP     | Remote Desktop       |

---

## ⚠️ Security Risks

* Open SSH (Port 22) can be targeted by brute-force attacks if weak credentials are used.
* HTTP (Port 80) transmits data without encryption.
* SMB (Port 445) may expose file-sharing services if misconfigured.
* Unnecessary open ports increase the attack surface.
* Systems should expose only the services required for normal operation.

---

## 📈 Outcome

* Successfully installed and configured **Nmap** on Ubuntu 26.04.
* Identified active hosts on the local network.
* Detected open TCP ports and associated services.
* Understood how TCP SYN scanning works.
* Learned how exposed services can introduce security risks.
* Developed practical **network reconnaissance** and **service enumeration** skills.

---

## 🎯 Skills Gained

* Network Reconnaissance
* Nmap Usage
* TCP SYN Scanning
* IP Addressing & Subnetting
* Service Enumeration
* Basic Network Security Assessment
* Packet Analysis with Wireshark (Optional)

---

## 📂 Repository Structure

```text
Task-1-Network-Scan/
├── README.md
├── scan_results.txt
├── network_scan.nmap
├── network_scan.xml
├── network_scan.gnmap
└── screenshots/
    ├── nmap_scan.png
    └── wireshark_capture.png
```

---

## 📝 Conclusion

This task demonstrated how **Nmap** can be used to perform basic network reconnaissance by identifying active hosts and open TCP ports. The exercise provided practical experience in discovering exposed network services, understanding common ports, and recognizing potential security risks. Regular network scanning is an important security practice for identifying unnecessary services and reducing an organization's attack surface.

---

> **Note:** This scan was performed only on an authorized local network for educational and cybersecurity training purposes.

# 🔍 Network Reconnaissance & Enumeration

## 📌 Objective

To perform network scanning and service enumeration on a target machine in order to identify open ports, running services, and potential security weaknesses.

---

## 🛠️ Tools Used

* Nmap
* Metasploit Framework
* Kali Linux

---

## 🌐 Target Information

* Target IP: 192.168.1.11
* Environment: Local Lab (Metasploitable VM)

---

## 🔎 Methodology

### Step 1: Network Scanning using Nmap

Performed TCP SYN scan and service version detection:

```
nmap -sS -sV 192.168.1.11
```

---

### Step 2: Service Enumeration

Identified multiple open ports and services running on the target machine.

---

## 📊 Findings

### 🔓 Open Ports & Services

| Port    | Service    | Version         |
| ------- | ---------- | --------------- |
| 21      | FTP        | vsftpd 2.3.4    |
| 22      | SSH        | OpenSSH 4.7p1   |
| 23      | Telnet     | Linux telnetd   |
| 25      | SMTP       | Postfix smtpd   |
| 53      | DNS        | ISC BIND 9.4.2  |
| 80      | HTTP       | Apache 2.2.8    |
| 139/445 | SMB        | Samba 3.x - 4.x |
| 3306    | MySQL      | 5.0.51a         |
| 5432    | PostgreSQL | 8.3.x           |
| 5900    | VNC        | Protocol 3.3    |
| 8180    | HTTP       | Apache Tomcat   |

---

## ⚠️ Key Observations

* Multiple outdated services detected (Apache, Samba, vsftpd)
* Presence of **Telnet (port 23)** — insecure protocol (plaintext credentials)
* **FTP service (vsftpd 2.3.4)** known for backdoor vulnerability
* **SMB services exposed** — potential for enumeration and exploitation
* **Bind shell detected on port 1524** — indicates possible prior compromise
* Large attack surface due to many open ports

---

## 💥 Potential Risks

* Unauthorized access via weak or vulnerable services
* Credential interception via Telnet
* Remote exploitation through outdated software
* Database exposure (MySQL, PostgreSQL)
* Remote shell access (bind shell)

---

## 📸 Proof of Work

<img width="1187" height="748" alt="Screenshot 2026-05-01 161821" src="https://github.com/user-attachments/assets/b3804b08-cdd3-4f44-b6c1-cf70f27558fd" />



---

## 🛡️ Mitigation

* Disable unnecessary services (Telnet, FTP, etc.)
* Replace insecure protocols with secure alternatives (SSH instead of Telnet)
* Update all outdated software
* Restrict access using firewall rules
* Monitor unusual open ports (e.g., bind shell)

---

## 📚 Learning Outcome

* Learned how to perform network scanning using Nmap
* Understood service enumeration and version detection
* Identified real-world vulnerabilities in exposed services
* Gained insight into attack surface analysis

---

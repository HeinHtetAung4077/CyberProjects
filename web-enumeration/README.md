# 🌐 Web Application Enumeration using WMAP

## 📌 Objective

To perform web application reconnaissance on a target system using Metasploit’s WMAP module in order to identify exposed endpoints, directories, and potential vulnerabilities.

---

## 🛠️ Tools Used

* Metasploit Framework (WMAP plugin)
* Kali Linux

---

## 🌐 Target Information

* Target: testphp.vulnweb.com (44.228.249.3)
* Protocol: HTTP
* Port: 80
* SSL: Disabled

---

## 🔎 Methodology

### Step 1: Launch Metasploit

```bash
msfconsole
```

### Step 2: Load WMAP Module

```bash
load wmap
```

### Step 3: Add Target Site

```bash
wmap_sites -a http://testphp.vulnweb.com
```

### Step 4: Define Target Paths

```bash
wmap_targets -t http://testphp.vulnweb.com
```

### Step 5: Execute Web Scan

```bash
wmap_run -t
```

---

## 📊 Findings

### 🔍 Scan Summary

* 39 WMAP modules loaded and executed
* Target does not support SSL (HTTP only)
* Multiple web-based scanning modules applied

---

### 🧪 Modules Executed

#### Web Server Testing

* HTTP version detection
* Open proxy detection
* Host header injection checks
* Robots.txt analysis
* WebDAV scanning
* Virtual host scanning

#### File & Directory Testing

* Directory brute-forcing
* Backup file detection
* Directory listing checks
* File upload (HTTP PUT) testing
* WebDAV bypass techniques

#### Vulnerability Testing

* SQL Injection (error-based & blind)
* Directory traversal testing
* Authentication bypass checks
* CMS-related vulnerability checks

---

## ⚠️ Key Observations

* Target runs on **HTTP without SSL**, making data transmission insecure
* Multiple attack surfaces identified via automated modules
* Directory and file enumeration modules indicate potential exposure of hidden resources
* SQL injection testing modules were triggered, indicating possible database interaction points

---

## 💥 Potential Risks

* Sensitive data exposure due to lack of HTTPS
* SQL Injection vulnerabilities may allow database compromise
* Directory traversal could expose restricted files
* Misconfigured web services may allow unauthorized access

---

## 📸 Proof of Work

<img width="1257" height="922" alt="1" src="https://github.com/user-attachments/assets/f29c7d36-3e30-4f67-9ecd-77d761e90ea7" />

<img width="1252" height="931" alt="2" src="https://github.com/user-attachments/assets/66900962-4939-430e-9fb1-4ae787a74c88" />

<img width="1257" height="912" alt="3" src="https://github.com/user-attachments/assets/05f759b7-47d4-49ca-a57c-393e2dd10848" />


---

## 🛡️ Mitigation

* Enable HTTPS and enforce secure communication
* Validate and sanitize all user inputs
* Disable directory listing
* Restrict access to sensitive endpoints
* Regularly update web server and dependencies

---

## 📚 Learning Outcome

* Learned how to perform automated web enumeration using WMAP
* Understood how different modules test for web vulnerabilities
* Gained practical experience in identifying web attack surfaces
* Improved understanding of real-world web security risks

---
## 🧠 Analyst Insight
The scan indicates a broad attack surface with multiple vectors such as SQL injection and directory exposure. Further manual testing is recommended to validate exploitability.

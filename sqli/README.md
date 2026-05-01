# 💉 SQL Injection Assessment using SQLMap

## 📌 Objective

To identify and assess SQL Injection vulnerabilities in a web application by analyzing input parameters and extracting database information.

---

## ⚠️ Disclaimer

This assessment was performed in a controlled lab environment for educational purposes only.

---

## 🛠️ Tools Used

* SQLMap
* Kali Linux

---

## 🌐 Target Information

* Target URL: https://hack-yourself-first.com/?id=1
* Parameter Tested: id (GET parameter)

---

## 🔎 Methodology

### Step 1: Identify Injection Point

* Observed dynamic parameter:

```text
?id=1
```

* Suspected user input is directly used in database query

---

### Step 2: Automated Testing using SQLMap

```bash
sqlmap -u "https://hack-yourself-first.com/?id=1" --batch --dbs
```

---

### Step 3: Injection Detection

SQLMap performed:

* Boolean-based testing
* Error-based testing

Detected:

* SQL Injection vulnerability in parameter `id`

---

## 📊 Findings

* Target parameter is vulnerable to SQL Injection
* Web Application Firewall (WAF) detected (Cloudflare)
* SQLMap successfully bypassed protections
* Database enumeration possible

---

## ⚠️ Key Observations

* Input validation is not properly implemented
* Application is vulnerable despite WAF presence
* Parameter-based queries are directly exposed

---

## 💥 Potential Risks

* Unauthorized database access
* Extraction of sensitive data (usernames, passwords)
* Authentication bypass
* Full application compromise

---

## 📸 Proof of Work

<img width="1261" height="842" alt="image" src="https://github.com/user-attachments/assets/a304d19e-89bd-4e06-acd4-7a9d4cf9d261" />


* SQLMap execution
* Injection detection
* Database listing

---

## 🛡️ Mitigation

* Use prepared statements (parameterized queries)
* Implement strong input validation
* Use ORM frameworks
* Improve WAF configuration
* Apply least privilege to database access

---

## 📚 Learning Outcome

* Learned SQL Injection detection techniques
* Understood automated exploitation using SQLMap
* Gained insight into database attack vectors
* Learned importance of secure coding practices

---

## 🧠 Analyst Insight

Even with a Web Application Firewall in place, improper input validation can still lead to SQL Injection. Security must be implemented at the application level rather than relying solely on external protections.

---

# linux-log-analysis-bruteforce-detection
Linux authentication log analysis and brute-force attack detection project.
# 🐧 Linux Log Analysis – Brute Force Detection

## 📌 Scenario

A Linux server showed unusual login activity. The Security Team was asked to investigate possible brute-force attempts using authentication logs.

---

## 📂 Log File Analyzed

File: `/var/log/auth.log`

### Sample Log Entries:

```
Mar 5 10:15:01 server sshd[2021]: Failed password for invalid user admin from 192.168.1.45 port 53421 ssh2
Mar 5 10:15:05 server sshd[2021]: Failed password for invalid user admin from 192.168.1.45 port 53421 ssh2
Mar 5 10:15:09 server sshd[2021]: Failed password for invalid user admin from 192.168.1.45 port 53421 ssh2
Mar 5 10:15:15 server sshd[2021]: Accepted password for user john from 192.168.1.45 port 53421 ssh2
```

---

## 🔎 Step 1: Indicators of Compromise (IOCs)

* Multiple failed login attempts
* Same source IP address
* Rapid sequence attempts (automation suspected)
* Successful login after repeated failures

Conclusion: Possible brute-force attack.

---

## 🛠 Step 2: Commands Used for Investigation

Example commands:

```
grep "Failed password" /var/log/auth.log
grep "Accepted password" /var/log/auth.log
grep "192.168.1.45" /var/log/auth.log
```

Purpose:

* Identify number of failed attempts
* Detect successful compromise
* Track suspicious IP behavior

---

## ⚠ Risk Assessment

Threat Type: SSH Brute Force Attack
Impact: High
Likelihood: Medium to High

Potential Impact:

* Unauthorized server access
* Data exfiltration
* Privilege escalation

---

## 🔐 Mitigation Actions

1. Blocked malicious IP via firewall
2. Disabled password authentication
3. Enforced SSH key-based authentication
4. Enabled Fail2Ban
5. Enabled Multi-Factor Authentication (MFA)

---

## 🎯 Outcome

Attack was identified and contained. Additional security hardening measures were implemented to prevent future brute-force attempts.

---

## 💡 Skills Demonstrated

* Linux log analysis
* Command-line investigation
* Threat detection
* Incident documentation
* Security hardening practices

---

## 👩‍💻 Author

Cybersecurity professional in training
Google Cybersecurity Certified
Aspiring SOC Analyst (USA 2026)


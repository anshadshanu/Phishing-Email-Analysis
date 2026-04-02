# Phishing Email Analysis
## Identifying Malicious Emails & Indicators of Compromise

![TryHackMe](https://img.shields.io/badge/Platform-TryHackMe-red)
![Status](https://img.shields.io/badge/Status-Completed-green)

---

## Project Overview

Analyzed real phishing email samples to identify malicious indicators of compromise. 
Phishing is one of the most common alerts SOC analysts investigate daily. This project 
covers the complete phishing investigation workflow from email header analysis to 
malicious URL detection and credential harvesting identification.

---

## TryHackMe Rooms Completed

| Room | Status |
|------|--------|
| Phishing Emails 1 | ✅ 100% |
| Phishing Emails in Action | ✅ 100% |

---

## Screenshots

### Room 1 – Completed
![Room 1](screenshots/6_room1_completed.png)
*Phishing Emails 1 completed — covered email headers, delivery protocols, and phishing indicators.*

---

### Room 2 – Completed
![Room 2](screenshots/10_room2_completed.png)
*Phishing Emails in Action completed — analyzed real phishing samples including fake login pages and malicious attachments.*

---

### Email Header Analysis
![Email Header](screenshots/2_email_header.png)
*Email header revealed spoofed sender — display name showed ADI Security Services but actual sender was newsletters@ant.anki-tech.com.*

---

### Email Body & Attachment Analysis
![Email Body](screenshots/3_email_body.png)
*Email body contained malicious PDF attachment Payment-updateid.pdf with base64 encoded content.*

---

### Fake Login Page – Credential Harvesting
![Login Page](screenshots/9_phishing_login_page.png)
*Fake Outlook login page used to steal credentials — shows Invalid Credentials regardless of input confirming data is sent to attacker.*

---

## Key Findings

| # | Finding | MITRE ATT&CK |
|---|---------|--------------|
| 1 | Email Spoofing | T1566.001 |
| 2 | Malicious URL – hxxp[://]devret[.]xyz | T1566.002 |
| 3 | Brand Impersonation | T1566 |
| 4 | Credential Harvesting | T1056.003 |
| 5 | Tracking Pixel | T1598 |
| 6 | Malicious PDF Attachment | T1566.001 |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| TryHackMe | Lab with real phishing samples |
| Mozilla Thunderbird | Analyzing .eml files |
| CyberChef | URL defanging and base64 decoding |
| MITRE ATT&CK | Threat framework mapping |

---

## Author

**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)
[GitHub](https://github.com/anshadshanu)

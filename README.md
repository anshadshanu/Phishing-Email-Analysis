# Phishing Email Analysis
## Identifying Malicious Emails & Indicators of Compromise

![TryHackMe](https://img.shields.io/badge/Platform-TryHackMe-red)
![Status](https://img.shields.io/badge/Status-Completed-green)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)

---

## Project Overview

This project demonstrates the analysis of real phishing email samples to identify 
malicious indicators of compromise. Two TryHackMe rooms were completed to gain 
hands-on experience investigating actual phishing emails used by attackers.

---

## TryHackMe Rooms Completed

| Room | Status |
|------|--------|
| Phishing Emails 1 | ✅ 100% |
| Phishing Emails in Action | ✅ 100% |

---

## Screenshots

### Room 1 – Phishing Emails 1 Completed
![Room 1](screenshots/6_room1_completed.png)
*TryHackMe Phishing Emails 1 completed with 100% progress – all 7 tasks finished.*

---

### Room 2 – Phishing Emails in Action Completed
![Room 2](screenshots/10_room2_completed.png)
*TryHackMe Phishing Emails in Action completed with 100% progress – all 8 tasks finished.*

---

### Email Header Analysis
![Email Header](screenshots/2_email_header.png)
*Real phishing email header showing spoofed sender newsletters@ant.anki-tech.com masquerading as ADI Security Services.*

---

### Phishing Email Body Analysis
![Email Body](screenshots/3_email_body.png)
*Email body analysis revealing malicious PDF attachment Payment-updateid.pdf with base64 encoded content.*

---

### Fake Login Page – Credential Harvesting
![Login Page](screenshots/9_phishing_login_page.png)
*Fake Microsoft Outlook login page used to steal credentials – shows Invalid Credentials regardless of input.*

---

## Key Findings

| # | Finding | Indicator | MITRE ATT&CK |
|---|---------|-----------|--------------|
| 1 | Email Spoofing | Sender/Reply-To mismatch | T1566.001 |
| 2 | Malicious URL | hxxp[://]devret[.]xyz | T1566.002 |
| 3 | Brand Impersonation | Home Depot, Microsoft, Adobe | T1566 |
| 4 | Credential Harvesting | Fake Outlook login page | T1056.003 |
| 5 | Tracking Pixel | Tracking.png embedded | T1598 |
| 6 | Malicious Attachment | Payment-updateid.pdf | T1566.001 |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| TryHackMe | Lab environment with real phishing samples |
| Mozilla Thunderbird | Email client for analyzing .eml files |
| CyberChef | URL defanging and base64 decoding |
| MITRE ATT&CK | Threat framework mapping |

---

## Author

**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)
[GitHub](https://github.com/anshadshanu)

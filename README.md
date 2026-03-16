# Phishing Email Analysis
## Identifying Malicious Emails & Indicators of Compromise

![TryHackMe](https://img.shields.io/badge/Platform-TryHackMe-red)
![Status](https://img.shields.io/badge/Status-Completed-green)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)

---

## Project Overview

This project demonstrates the analysis of real phishing email samples to identify 
malicious indicators of compromise (IOCs). Two TryHackMe rooms were completed to 
gain hands-on experience investigating actual phishing emails used by attackers.

Phishing is one of the most common attack vectors SOC analysts encounter daily. 
This project covers email header analysis, malicious URL detection, fake login page 
identification, and malicious attachment investigation.

---

## TryHackMe Rooms Completed

| Room | Description | Status |
|------|-------------|--------|
| Phishing Emails 1 | Email structure, headers, delivery protocols | ✅ 100% |
| Phishing Emails in Action | Real phishing email sample analysis | ✅ 100% |

---

## Key Findings

| # | Finding | Indicator | MITRE ATT&CK |
|---|---------|-----------|--------------|
| 1 | Email Spoofing | Sender/Reply-To mismatch | T1566.001 |
| 2 | Malicious URL | hxxp[://]devret[.]xyz | T1566.002 |
| 3 | Brand Impersonation | Home Depot, Microsoft, Adobe | T1566 |
| 4 | Credential Harvesting | Fake Outlook login page | T1056.003 |
| 5 | Tracking Pixel | Tracking.png embedded in email | T1598 |
| 6 | Malicious Attachment | Payment-updateid.pdf | T1566.001 |

---

## Skills Demonstrated

- Email header analysis to identify spoofed senders
- Malicious URL detection and defanging using CyberChef
- Identifying fake login pages used for credential harvesting
- Recognizing phishing techniques such as urgency and brand impersonation
- Mapping phishing indicators to MITRE ATT&CK framework
- Documenting findings in a professional SOC investigation report

---

## Tools Used

| Tool | Purpose |
|------|---------|
| TryHackMe | Lab environment with real phishing samples |
| Mozilla Thunderbird | Email client for analyzing .eml files |
| CyberChef | URL defanging and base64 decoding |
| MITRE ATT&CK | Threat framework for mapping attack techniques |

---

## Lab Architecture
```
Phishing Email Received
        ↓
Email Header Analysis → Identify Spoofed Sender
        ↓
Email Body Analysis → Find Malicious URLs & Attachments
        ↓
URL Defanging → CyberChef
        ↓
Domain Investigation → Identify Malicious Domains
        ↓
Findings → MITRE ATT&CK Mapping
```

---

## Project Report

Full investigation report with screenshots is available in this repository.

---

## Author

**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)
[GitHub](https://github.com/anshadshanu)

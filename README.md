# SOC Home Lab – SIEM Monitoring & Attack Detection

![VMware](https://img.shields.io/badge/Platform-VMware-blue)
![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

---

## Project Overview

As a SOC Analyst, one of the core responsibilities is monitoring security events, 
detecting suspicious activity, and investigating potential threats using a SIEM platform. 
This project replicates that real-world workflow by building a fully functional SOC home 
lab from scratch.

The lab environment simulates a small enterprise network where an attacker machine 
launches real cyber attacks against a target machine. All generated security events 
are collected and analyzed using Splunk SIEM — exactly how a SOC analyst would 
investigate threats in a real company.

---

## SOC Analyst Workflow Demonstrated
```
Threat Actor Activity → Windows Security Logs Generated → 
Splunk SIEM Collects Logs → SOC Analyst Investigates → Threat Detected
```

This workflow mirrors the daily responsibilities of a Tier 1 SOC Analyst:
- Monitoring incoming security alerts
- Searching SIEM for suspicious EventCodes
- Identifying attack patterns in logs
- Documenting findings and mapping to threat frameworks

---

## Lab Architecture

| Component | System | IP Address | Role |
|-----------|--------|------------|------|
| Attacker | Kali Linux 2025.2 | 192.168.52.x | Simulate cyber attacks |
| Target | Windows Server 2022 | 192.168.52.136 | Generate security logs |
| SIEM | Splunk Enterprise 10.0.1 | 127.0.0.1:8000 | Log monitoring & analysis |
| Virtualization | VMware Workstation Pro 17 | Host Machine | Run virtual machines |

---

## Screenshots

### Network Connectivity Test
![Ping Test](screenshots/4.%20ping_test.png)
*Before any attack simulation, network connectivity between the attacker machine 
(Kali Linux) and target machine (Windows Server 2022) was verified using ping. 
A SOC analyst always confirms the network environment is working correctly 
before beginning any investigation or simulation.*

---

### Splunk SIEM Dashboard
![Splunk Dashboard](screenshots/5.%20splunk_dashboard.png)
*Splunk Enterprise was installed and configured as the SIEM platform to collect 
Windows Security, System, and Application logs. In a real SOC environment, the 
SIEM dashboard is the primary tool analysts use to monitor incoming security events, 
search for suspicious activity, and investigate potential threats in real time.*

---

### Attack Simulation – Network Scanning (Nmap)
![Nmap Attack](screenshots/8.%20attack_nmap_scan.png)
*A network reconnaissance scan was performed from the Kali Linux attacker machine 
using Nmap to identify open ports and running services on the Windows Server target. 
This simulates the initial reconnaissance phase a real threat actor performs before 
launching a targeted attack. As a SOC analyst, identifying unauthorized network scans 
in SIEM logs is a key early warning indicator of a potential breach — mapped to 
MITRE ATT&CK T1046 (Network Service Discovery).*

---

### Attack Simulation – Brute Force Login (Hydra)
![Brute Force](screenshots/9.%20attack_brute_force.png)
*A brute force credential attack was simulated using Hydra from the Kali Linux 
machine targeting the SMB service (port 445) on the Windows Server. This attack 
generates a high volume of failed authentication attempts which appear as 
EventCode 4625 (Failed Logon) in the Windows Security logs. SOC analysts 
commonly encounter brute force attacks as one of the most frequent attack 
types in enterprise environments — mapped to MITRE ATT&CK T1110 (Brute Force).*

---

### SOC Investigation – Attack Detected in Splunk
![Investigation](screenshots/10.%20investigation_results.png)
*After running the brute force attack, Splunk was used to investigate the 
generated security events. The search query EventCode=4625 returned 15 failed 
logon events, confirming the attack was successfully detected by the SIEM. 
This demonstrates the core SOC analyst skill of using SIEM queries to identify 
and investigate suspicious authentication activity — a task performed daily in 
real SOC environments.*

---

## Attacks Simulated & Detection

| Attack | Tool | Detection Query | MITRE ATT&CK |
|--------|------|----------------|--------------|
| Network Scanning | Nmap | index=main EventCode=4625 | T1046 |
| Brute Force Login | Hydra | index=main EventCode=4625 | T1110 |
| SMB Service Attack | Hydra | index=main EventCode=4625 | T1021.002 |

---

## Windows Event IDs Investigated

As a SOC analyst, understanding Windows Event IDs is essential for 
investigating security incidents. The following Event IDs were used 
during this investigation:

| Event ID | Name | SOC Relevance |
|----------|------|---------------|
| 4624 | Successful Logon | Baseline normal activity — monitor for unusual logons |
| 4625 | Failed Logon | Key indicator of brute force attacks |
| 4688 | Process Creation | Detect suspicious process execution |
| 4672 | Special Privileges | Indicates potential privilege escalation |
| 4740 | Account Lockout | Triggered by repeated failed login attempts |

---

## Splunk Queries Used
```splunk
# View all security logs
index=main

# Investigate successful logins
index=main EventCode=4624

# Detect failed login attempts (Brute Force Indicator)
index=main EventCode=4625

# Monitor process creation events
index=main EventCode=4688
```

---

## Tools Used

| Tool | Version | Purpose |
|------|---------|---------|
| VMware Workstation Pro | 17 | Virtual machine environment |
| Kali Linux | 2025.2 | Attacker machine |
| Windows Server 2022 | Build 20348 | Target machine – log generation |
| Splunk Enterprise | 10.0.1 | SIEM – log collection and analysis |
| Nmap | 7.95 | Network reconnaissance simulation |
| Hydra | 9.5 | Brute force credential attack simulation |

---

## Key Takeaways

From a SOC analyst perspective this project demonstrates:

- How attackers perform reconnaissance before launching attacks
- How brute force attacks appear in Windows Security logs
- How SIEM tools like Splunk are used to detect and investigate threats
- How to map real-world attacks to the MITRE ATT&CK framework
- The importance of log monitoring and alert investigation in SOC operations

---

## Author

**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)
[GitHub](https://github.com/anshadshanu)

# SOC Home Lab – SIEM Monitoring & Attack Detection

![VMware](https://img.shields.io/badge/Platform-VMware-blue)
![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

---

## Project Overview

Built a SOC home lab to simulate real-world cyber attacks and detect them using 
Splunk SIEM. The lab replicates the core workflow of a SOC analyst — monitoring 
security logs, detecting suspicious activity, and investigating threats.

---

## Lab Architecture

| Component | System | IP Address | Role |
|-----------|--------|------------|------|
| Attacker | Kali Linux 2025.2 | 192.168.52.x | Simulate attacks |
| Target | Windows Server 2022 | 192.168.52.136 | Generate security logs |
| SIEM | Splunk Enterprise 10.0.1 | 127.0.0.1:8000 | Log monitoring |
| Virtualization | VMware Workstation Pro 17 | Host Machine | Run VMs |

---

## Screenshots

### Network Connectivity Test
![Ping Test](screenshots/4.%20ping_test.png)
*Network connectivity verified between Kali Linux and Windows Server 2022 before attack simulation.*

---

### Splunk SIEM Dashboard
![Splunk Dashboard](screenshots/5.%20splunk_dashboard.png)
*Splunk configured to collect Windows Security, System, and Application logs for real-time monitoring.*

---

### Attack 1 – Network Scan (Nmap)
![Nmap Attack](screenshots/8.%20attack_nmap_scan.png)
*Nmap scan from Kali Linux identifying open ports on Windows Server — simulates attacker reconnaissance (MITRE T1046).*

---

### Attack 2 – Brute Force Login (Hydra)
![Brute Force](screenshots/9.%20attack_brute_force.png)
*Hydra brute force attack targeting SMB port 445 generating failed login events in Windows Security logs (MITRE T1110).*

---

### Investigation – Attack Detected in Splunk
![Investigation](screenshots/10.%20investigation_results.png)
*Splunk query EventCode=4625 returned 15 failed logon events — confirming brute force attack was successfully detected.*

---

## Windows Event IDs Used

| Event ID | Name | Description |
|----------|------|-------------|
| 4624 | Successful Logon | Normal login activity |
| 4625 | Failed Logon | Brute force indicator |
| 4688 | Process Creation | Suspicious process execution |
| 4672 | Special Privileges | Privilege escalation indicator |

---

## Splunk Queries
```
index=main EventCode=4624
index=main EventCode=4625
index=main EventCode=4688
```

---

## Tools Used

| Tool | Version | Purpose |
|------|---------|---------|
| VMware Workstation Pro | 17 | Virtual machine environment |
| Kali Linux | 2025.2 | Attacker machine |
| Windows Server 2022 | Build 20348 | Target machine |
| Splunk Enterprise | 10.0.1 | SIEM platform |
| Nmap | 7.95 | Network scanning |
| Hydra | 9.5 | Brute force simulation |

---

## Author

**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)
[GitHub](https://github.com/anshadshanu)

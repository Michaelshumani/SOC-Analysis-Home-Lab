# SOC Analysis Home Lab
### Sysmon · Wazuh SIEM · Nmap · Wireshark · Hyper-V · Windows Server 2022 · Ubuntu Server 24.04

> Built and documented by **Bologo Michael Shumani** — BSc Computer Science & Mathematics, University of Venda

---

## Project Overview

Designed and deployed a fully functional **Security Operations Centre (SOC) home lab** from scratch on a Windows 11 laptop using Hyper-V virtualisation — simulating a real enterprise SOC environment.

The lab detects simulated attacks in real time, generates security alerts, maps threats to the MITRE ATT&CK framework, captures network packets, and produces professional incident reports.

---

## Architecture

```
HOST LAPTOP — BOLOGOM-LT (Windows 11 · 16GB RAM)
│
├── Hyper-V
│   ├── SOC VM — Windows Server 2022 (172.31.228.160)
│   │   ├── Sysmon v15.20        → endpoint telemetry
│   │   └── Wazuh Agent v4.7.0  → log forwarding
│   │
│   └── Ubuntu VM — Ubuntu Server 24.04 (172.31.236.95)
│       ├── Wazuh Manager v4.8.2 → SIEM analysis
│       └── Wazuh Dashboard      → alert visualisation
│
└── Host Tools
    ├── Nmap v7.99      → attack simulation
    └── Wireshark v4.6.4 → packet capture
```

---

## Tools & Technologies

| Tool | Version | Purpose |
|------|---------|---------|
| Sysmon | v15.20 | Endpoint telemetry and event logging |
| Wazuh Agent | v4.7.0 | Log collection and forwarding |
| Wazuh Manager | v4.8.2 | SIEM analysis and alerting |
| Wazuh Dashboard | v4.8.2 | Real-time alert visualisation |
| Nmap | v7.99 | Attack simulation and port scanning |
| Wireshark | v4.6.4 | Network packet capture and analysis |
| Hyper-V | Windows 11 | Virtual machine infrastructure |
| Windows Server | 2022 | Target endpoint |
| Ubuntu Server | 24.04 LTS | Wazuh Manager host |

---

## Key Achievements

- 239 medium severity alerts generated and analysed from a single Windows endpoint
- Simulated Nmap port scan detected within seconds of execution
- 51,000+ network packets captured and filtered using Wireshark
- Custom Wazuh detection rule (ID 100002) written in XML and validated
- Full incident report produced (INC-2026-001)
- MITRE ATT&CK framework mapping enabled automatically
- 100% agent coverage confirmed on Wazuh Dashboard

---

## Project Structure

```
SOC-Analysis-Home-Lab/
├── 1-Hyper-V-Setup/         → VM setup and virtual switch screenshots
├── 2-Sysmon/                → Sysmon installation and event capture
├── 3-Wazuh-Agent/           → Wazuh Agent installation and logs
├── 4-Wazuh-Dashboard/       → Dashboard overview, agents, alerts
├── 5-Nmap-Attack/           → Nmap attack simulation and detection
├── 6-Wireshark/             → Packet capture and SYN filter analysis
├── 7-Custom-Rules/          → Custom Wazuh detection rule
├── 8-Reports/               → Incident report (INC-2026-001)
└── README.md
```

---

## Setup Steps

### Step 1 — Hyper-V Configuration
- Created internal virtual switch (SOC-Lab-Switch)
- Deployed Windows Server 2022 VM as target endpoint
- Deployed Ubuntu Server 24.04 VM as Wazuh Manager host

### Step 2 — Sysmon Installation
- Downloaded Sysmon v15.20 from Microsoft Sysinternals
- Applied SwiftOnSecurity enterprise configuration
- Verified event capture using PowerShell Get-WinEvent

### Step 3 — Wazuh Agent
- Installed Wazuh Agent v4.7.0 on Windows Server VM
- Configured agent to point to Ubuntu VM IP address
- Confirmed connection and log forwarding

### Step 4 — Wazuh Manager and Dashboard
- Installed Wazuh v4.8.2 on Ubuntu Server using official installer
- Accessed dashboard via browser at https://172.31.236.95
- Confirmed SOC VM agent active with 100% coverage

### Step 5 — Attack Simulation
- Ran Nmap port scan from host laptop against SOC VM
- Monitored Wazuh dashboard for real-time alert generation
- Captured attack traffic using Wireshark on Default Switch adapter

### Step 6 — Custom Detection Rule
- Wrote custom rule ID 100002 in local_rules.xml
- Restarted Wazuh Manager to apply rule
- Validated rule firing on simulated attack

---

## Incident Report Summary

| Field | Details |
|-------|---------|
| Incident ID | INC-2026-001 |
| Date | 03 May 2026 |
| Type | Network Port Scan — Reconnaissance |
| Severity | Medium |
| Affected System | WIN-BG1EIQRHP98 (172.31.228.160) |
| Source | Host laptop (172.31.224.1) |
| Detection | Wazuh SIEM + Sysmon |
| Status | Resolved — Simulated Lab Attack |

---

## Skills Demonstrated

- Cybersecurity and SOC operations
- SIEM deployment and alert analysis
- Endpoint telemetry and threat detection
- Network packet capture and analysis
- Linux server administration
- Windows Server administration
- Custom detection rule writing (XML)
- Incident response and documentation
- Virtualisation and lab infrastructure

---

## Author

**Bologo Michael Shumani**
BSc Computer Science & Mathematics — University of Venda
Microsoft Azure Fundamentals (AZ-900) Certified

LinkedIn: linkedin.com/in/shumani-michael-bologo
Email: bologoshumanimichael@gmail.com

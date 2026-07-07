# Northwind-Regional-Healthcare-Cloud-Breach-Investigation

Kali Linux (Attacker)
        │
        ▼
Windows 10 Endpoint
├─ Sysmon
├─ MySQL Database
├─ Synthetic Patient Records
└─ Azure Monitor Agent
        │
        ▼
Microsoft Sentinel
        │
        ▼
Threat Hunting Investigation

Scenario

A threat actor compromises a third-party contractor VPN account and gains unauthorized access to a hybrid healthcare environment spanning on-premises systems and cloud resources. After successfully authenticating, the attacker conducts PowerShell-based reconnaissance, enumerates users and system information, and accesses a MySQL database containing synthetic patient records.

The adversary then stages sensitive healthcare data for exfiltration and transfers the collected records to attacker-controlled cloud storage. To evade detection and maximize operational disruption, the attacker attempts to establish persistence, clear evidence of activity, and deploy ransomware across affected systems.

Throughout the attack lifecycle, telemetry is collected from Windows event logs, Sysmon, database activity, authentication logs, and cloud services. Microsoft Sentinel is leveraged to correlate endpoint, identity, database, and cloud-based indicators to reconstruct the attack timeline, identify impacted assets, investigate patient data exposure, and support incident response activities.

Security Domains Demonstrated
Cloud Security
Threat Hunting
Detection Engineering
Identity & Access Management (IAM)
Healthcare Security
Database Security
Security Monitoring & SIEM
Incident Response
Adversary Emulation
MITRE ATT&CK Mapping

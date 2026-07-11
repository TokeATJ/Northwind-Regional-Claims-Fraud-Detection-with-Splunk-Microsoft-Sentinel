# Northwind Regional Claims Fraud Detection with Splunk Microsoft-Sentinel

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/88e63e7e-25ce-4595-8ac5-d082cd094ce3" />


## Lab Architecture

```text
Kali Linux (Attacker)
          |
          v
Compromised VPN Account
          |
          v
Windows 10 Healthcare Workstation
(Sysmon + MySQL + Synthetic PHI/Claims Data)
          |
          +----------------+
          |                |
          v                v
 Splunk Universal     Azure Monitor Agent
     Forwarder
          |                |
          v                v
 Splunk Enterprise   Microsoft Sentinel
          |                |
          +-------+--------+
                  |
                  v
     Threat Hunting & Investigation
                  |
                  v
      Data Exfiltration Detection
``` 


## Scenario: Compromised Healthcare Billing Analyst Workstation Resulting in Claims and Patient Data Access

A threat actor compromises a third-party contractor VPN account and gains unauthorized access to a hybrid healthcare environment consisting of on-premises systems and cloud-connected security infrastructure. After successfully authenticating to a Windows healthcare workstation, the attacker performs PowerShell-based reconnaissance, enumerates users and system information, and accesses a MySQL database containing synthetic patient, provider, payer, claims, and claims transaction data.

Using the compromised workstation, the attacker queries sensitive healthcare records, stages patient and claims data for collection, and prepares the information for exfiltration to attacker-controlled cloud storage. To expand access and reduce the likelihood of detection, the adversary attempts to establish persistence, clear traces of activity, and perform actions consistent with ransomware pre-deployment behavior.

Throughout the attack lifecycle, telemetry is collected from Windows Event Logs, Sysmon, MySQL database activity, authentication events, and cloud-connected monitoring services. Security data is forwarded to both Splunk Enterprise and Microsoft Sentinel, enabling cross-platform threat hunting, detection engineering, and incident investigation.

Splunk is used to analyze endpoint telemetry, process creation events, PowerShell activity, and system-level indicators, while Microsoft Sentinel provides centralized visibility into authentication activity, cloud-connected resources, endpoint events, and correlated security alerts. Together, these platforms are leveraged to reconstruct the attack timeline, identify impacted assets, investigate potential patient data exposure, and support incident response activities.

Security Domains Demonstrated
Threat Hunting
Detection Engineering
Security Monitoring & SIEM
Incident Response
Microsoft Sentinel
Splunk Enterprise
Cloud Security
Identity & Access Management (IAM)
Healthcare Security
Database Security
Endpoint Security Monitoring
Adversary Emulation
MITRE ATT&CK Mapping
Data Exfiltration Detection
Insider Threat Detection

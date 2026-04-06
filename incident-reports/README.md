# Incident Reports - Security Operations Center (SOC)

This directory contains professionally structured incident reports generated during security monitoring and investigation activities within a simulated Security Operations Center (SOC) environment.

The reports are based on real detection scenarios using Wazuh SIEM and the Elastic Stack, combined with endpoint telemetry from Sysmon and controlled attack simulations.

---

## Project Context

These incident reports are part of the:

**Home SOC Project - Wazuh + Elastic Stack**

The environment simulates a real-world SOC setup consisting of:

- Windows 10 Endpoint (Victim Machine)
- Kali Linux (Attacker Machine)
- Wazuh SIEM (Detection & Alerting)
- Elastic Stack (Log Analysis & Visualization)
- Sysmon (Endpoint Telemetry)

---

## Purpose

The goal of this repository is to demonstrate the ability to:

- Perform SOC Tier-1 alert triage
- Conduct structured incident investigations
- Analyze logs and correlate security events
- Identify Indicators of Compromise (IOCs)
- Map detections to MITRE ATT&CK techniques
- Classify incident severity levels
- Document incidents in a professional format
- Support escalation decisions and response actions

---

## SOC Incident Handling Workflow

Each report follows a standardized SOC workflow:

1. Alert Detection (Wazuh SIEM)
2. Alert Triage
3. Investigation & Log Analysis
4. Evidence Correlation
5. IOC Identification
6. Threat Assessment
7. Containment & Mitigation
8. Escalation Decision
9. Documentation & Reporting
10. Lessons Learned

---

## Incident Types Covered

The SOC environment simulates and documents incidents such as:

- Suspicious PowerShell execution
- Command-line obfuscation attacks
- Unauthorized process execution
- Persistence mechanisms (registry, startup)
- Privilege escalation attempts
- Network anomaly detection
- Simulated malware execution

---

## Tools & Technologies Used

| Tool | Purpose |
|------|--------|
| Wazuh | SIEM detection and alerting |
| Elastic Stack | Log analysis and visualization |
| Sysmon | Endpoint event logging |
| Windows 10 | Target system |
| Kali Linux | Attack simulation |
| VirtualBox | Lab environment |

---

## Severity Classification Model

Incidents are classified based on risk and impact:

| Severity | Description |
|----------|------------|
| Low | low-risk activity |
| Medium | Suspicious activity requiring investigation |
| High | Confirmed malicious behavior |
| Critical | Active compromise or high-impact threat |

---

## Skills Demonstrated

This project demonstrates practical SOC analyst capabilities:

- Security Monitoring & Alert Triage  
- Log Analysis (Wazuh, Sysmon, Elastic)  
- Threat Detection & Investigation  
- Incident Documentation & Reporting  
- MITRE ATT&CK Framework Mapping  
- DFIR (Digital Forensics & Incident Response) Concepts  
- Analytical Thinking & Decision-Making  

---

## Report Structure

Each incident report includes:

- Executive Summary  
- Detection Details  
- Indicators of Compromise (IOCs)  
- Timeline of Events  
- Investigation Findings  
- Threat Assessment  
- Actions Taken  
- Escalation Decision  
- Lessons Learned  
- Final Analyst Conclusion  

---

## SOC Relevance

Accurate and structured incident reporting is critical in real-world SOC environments for:

- Communication between Tier-1 and Tier-2 analysts  
- Incident Response coordination  
- Threat intelligence sharing  
- Compliance and audit requirements  

This project reflects industry-standard documentation practices used in professional SOC operations.

---

## Author

**Caleb Kamau Kimani**  
SOC Analyst | Cyber Security Enthusiast
Home SOC Lab (Wazuh + Elastic Stack)

---

## Repository Notes

- All incidents are generated within a controlled lab environment  
- Attack scenarios are simulated for learning and demonstration purposes  
- No real systems were compromised  

---

## Future Improvements

- Integration with threat intelligence feeds  
- Automated alert enrichment  
- Advanced correlation rules in Wazuh  
- Additional incident scenarios (lateral movement, persistence, exfiltration)  

# Security Incident Report  
Mini Security Operations Center (SOC)

---

# 1. Executive Summary

**Incident Title:** Suspicious PowerShell Execution Detected  
**Incident ID:** SOC-2025-001  
**Date/Time (UTC):** 2025-01-12 10:37 UTC  
**Analyst:** Caleb Kamau Kimani  
**Severity Level:** Medium  
**Status:** Closed  

### Summary

A suspicious PowerShell execution was detected on a Windows 10 endpoint during SOC monitoring using Wazuh SIEM. The alert was triggered based on Sysmon logs indicating command-line execution consistent with encoded PowerShell activity.

The activity was flagged as suspicious due to the use of obfuscated commands commonly associated with attacker techniques such as command execution and potential payload delivery.

Investigation confirmed this activity originated from a controlled attack simulation using a Kali Linux system within the Home SOC lab environment. No persistence or lateral movement was observed.

The incident was contained and classified as a simulated attack with no real compromise.

---

# 2. Detection Details

**Detection Source:** Wazuh SIEM (Sysmon Logs)  

**Wazuh Rule ID:** 18107  

**Log Source:** Sysmon Event ID 1 (Process Creation)  

**MITRE ATT&CK Mapping:**  
- T1059.001 - Command and Scripting Interpreter: PowerShell  

---

# 3. Affected Systems

| Host        | IP Address     | Role             |
|------------|---------------|------------------|
| WIN10-ENDPT | 192.168.56.110 | Victim Endpoint  |
| KALI-LINUX  | 192.168.56.101 | Attacker System  |

---

# 4. Indicators of Compromise (IOCs)

| Type     | Indicator            | Description                         |
|----------|---------------------|-------------------------------------|
| Process  | powershell.exe      | Suspicious encoded execution        |
| Process  | cmd.exe             | Parent process                      |
| Command  | -encodedCommand     | Obfuscated command execution        |
| IP       | 192.168.56.101      | Source of simulated attack          |

---

# 5. Timeline of Events

| Time       | Event                                      | Source        |
|-----------|-------------------------------------------|--------------|
| 10:37 UTC | Suspicious PowerShell execution detected   | Wazuh         |
| 10:37 UTC | Sysmon logs process creation               | Sysmon        |
| 10:38 UTC | Alert generated and triaged                | Wazuh         |
| 10:40 UTC | Investigation initiated                    | Analyst       |
| 10:45 UTC | Activity confirmed as simulated attack     | Analyst       |
| 10:47 UTC | Incident closed                            | Analyst       |

---

# 6. Investigation

## Observations

- PowerShell executed with encoded command parameters  
- Parent process identified as cmd.exe  
- Activity originated from attacker machine (Kali Linux)  
- No persistence mechanisms detected  
- No lateral movement observed  

---

## Evidence Reviewed

- Wazuh Alerts Dashboard  
- Sysmon Process Creation Logs  
- Windows Event Logs  
- Elastic Stack Log Correlation  

---

## Log Analysis

Process Tree:

cmd.exe → powershell.exe  

Suspicious command:

powershell -encodedcommand  

The encoded command structure indicates possible obfuscation commonly used by attackers to evade detection.

---

# 7. Threat Assessment

**Risk Level:** Medium  

**Impact Assessment:**

- Suspicious activity detected  
- No confirmed system compromise  
- No persistence or privilege escalation observed  

---

# 8. Actions Taken

## Containment

- Process execution monitored and analyzed  
- No active containment required (controlled lab environment)  
- Alert escalated for investigation  

---

## Mitigation

- Reviewed system logs for additional anomalies  
- Verified absence of persistence mechanisms  
- Confirmed system integrity  

---

# 9. Escalation Decision

**Escalated to Tier 2:** No  

**Reason:**  
Activity was confirmed as part of a controlled attack simulation within the Home SOC lab. No indicators of real compromise were identified.

---

# 10. Lessons Learned

## What Worked

- Wazuh detection rules successfully triggered  
- Sysmon provided detailed process visibility  
- Alert triage workflow was effective  

## What Needs Improvement

- Improve alert context enrichment  
- Enhance detection tuning to reduce noise  
- Expand monitoring to include network-level telemetry  

---

# 11. Recommendations

- Implement additional Sysmon rules for deeper visibility  
- Improve Wazuh rule tuning for PowerShell detection  
- Integrate threat intelligence feeds for enrichment  
- Enable network traffic monitoring for correlation  

---

# 12. Final Analyst Conclusion

Suspicious PowerShell activity was successfully detected and investigated within the SOC environment. The activity was determined to be part of a simulated attack originating from a controlled Kali Linux system.

No system compromise, persistence, or lateral movement was identified. The incident demonstrates effective detection, investigation, and documentation capabilities aligned with SOC operational standards.

---

# 13. Report Metadata

| Field | Value |
|------|------|
| Analyst | Caleb Kamau Kimani |
| SOC Environment | Home SOC (Wazuh + Elastic Stack) |
| Tools Used | Wazuh, Elastic Stack, Sysmon, Kali Linux |
| Report Version | 1.0 |
| Report Date | 2025-01-12 |

---

# Commit Notes

- Added fully documented SOC incident report based on Wazuh detection
- Implemented structured Tier-1 SOC investigation workflow
- Included MITRE ATT&CK mapping and IOC analysis
- Enhanced professional DFIR documentation for portfolio
- Demonstrated real-world alert triage and incident handling process

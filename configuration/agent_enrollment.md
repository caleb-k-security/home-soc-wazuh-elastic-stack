# Endpoint Agent Enrollment

## Objective
Register endpoints to the Wazuh server for centralized monitoring and alert generation.

---

## Deployment Method
Agent installed silently via command line.

Example:

msiexec /i wazuh-agent-4.7.0.msi /q WAZUH_MANAGER="192.168.x.x" WAZUH_AGENT_NAME="WIN10-ENDPOINT"

---

## Service Start
net start wazuh

---

## Verification
Agent should appear in dashboard:

Agents → Status = Active

---

## Expected Outcome
Successful enrollment confirms:

- Secure communication between endpoint and SIEM
- Log forwarding operational
- Endpoint visible to SOC analysts

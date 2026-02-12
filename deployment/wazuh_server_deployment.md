# Wazuh Server Deployment (Ubuntu)

## VM Build (VirtualBox)
Recommended baseline:
- RAM: 4096 MB (4 GB)
- CPU: 2 cores
- Disk: 40 GB (VDI, dynamically allocated)

---

## Networking
Adapter 1: NAT (internet access)  
Adapter 2: Host-only Adapter (VM-to-VM lab traffic)

---

## OS Install (Ubuntu Server)
- Language: English
- Network: DHCP
- Storage: Use entire disk
- Install OpenSSH Server: Yes
- User: ubuntu
- Password: (set during install)

---

## System Update
```bash
sudo apt update && sudo apt upgrade -y
```

---

## Install Wazuh (Manager + Indexer + Dashboard)
```bash
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a
```

---

## Service Validation
```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
```

---

## Find Server IP (Host-only interface)
```bash
ip a
```

Record the host-only IP address for agent enrollment and dashboard access.

---

---

# Windows Endpoint Onboarding (Wazuh Agent)

## Objective
Enroll a Windows endpoint into Wazuh so the SOC server can receive logs and generate alerts.

---

## Install Wazuh Agent
From Wazuh Dashboard:
- Agents → Deploy new agent
- OS: Windows
- Server address: (host-only IP of Wazuh server)
- Agent name: WIN10-ENDPOINT

---

## Silent Install (PowerShell as Administrator)
```powershell
msiexec /i wazuh-agent-4.7.0.msi /q WAZUH_MANAGER="192.168.x.x" WAZUH_AGENT_NAME="WIN10-ENDPOINT"
```

---

## Start Agent Service
```powershell
net start wazuh
```

---

## Verification
In Wazuh Dashboard:
- Agents → confirm endpoint shows **Active**

---

---

# Operational Validation Checklist

## Wazuh Services (Ubuntu)
Confirm all are running:
- wazuh-manager
- wazuh-indexer
- wazuh-dashboard

---

## Dashboard Access (Analyst Workstation)
- Access via: https://192.168.x.x
- Confirm successful login

---

## Agent Enrollment
- Agent status: Active
- Events visible under Security Events for the Windows endpoint

---

## Minimum Evidence to Capture
- Dashboard login screen
- Agents list showing endpoint Active
- Ubuntu service status output
- Sample security events from endpoint logs

---

## Validation Success Criteria
The deployment is considered successful when:

- All Wazuh services are active
- Dashboard loads remotely
- Agent registers successfully
- Logs appear in SIEM
- Alerts can be generated

---

## SOC Analyst Note
Successful validation confirms operational SIEM functionality, endpoint telemetry ingestion, and analyst monitoring capability.

# Home SOC Deployment with Wazuh SIEM and Elastic Stack

## Overview
This project documents the design and implementation of a small-scale Security Operations Center (SOC) lab using Wazuh SIEM and the Elastic Stack. The lab simulates an enterprise SOC workflow: central log collection, endpoint onboarding, dashboard monitoring, and operational validation.

## Lab Roles
- **Ubuntu Server** - Wazuh Manager + Indexer + Dashboard (SIEM core)
- **Windows 10** - monitored endpoint (victim)
- **Kali Linux** - attacker simulator
- **Host machine** - analyst workstation (dashboard access + documentation)

## What This Proves (SOC Value)
- SIEM deployment and service validation
- Secure dashboard access from analyst workstation
- Endpoint onboarding with Wazuh agent
- Network design for controlled lab communication (NAT + Host-only)
- Evidence-based verification (screenshots + checks)

## Repository Structure
- `architecture/` - network model and data flow
- `deployment/` - VM build + Wazuh installation steps
- `configuration/` - agent enrollment + key settings
- `validation/` - health checks and verification steps
- `evidence/` - screenshots and proof artifacts
- `incident-reports/` - professional incident report template/output

## Tools
- VirtualBox or VMware
- Ubuntu Server (Wazuh server)
- Windows 10 endpoint
- Kali Linux
- Wazuh SIEM (Manager, Indexer, Dashboard)

## Author
**Caleb Kamau Kimani** - SOC Analyst (Tier-1) / Network Security


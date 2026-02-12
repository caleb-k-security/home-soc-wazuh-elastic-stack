# Architecture Overview

## Goal
Build a mini SOC lab to collect endpoint telemetry, detect suspicious activity, and validate SOC monitoring operations using Wazuh SIEM.

## High-Level Data Flow
Kali Linux (attack simulation) → Windows endpoint (telemetry) → Wazuh Server (analysis + correlation) → Dashboard (analyst investigation)

## Network Model
Two network adapters on the Wazuh server enable:
- **NAT**: internet access for package installation/updates
- **Host-only**: isolated VM-to-VM communication inside the lab

This design supports a controlled environment while maintaining required connectivity for deployments and updates.

## SOC Components
- **Wazuh Manager**: ingests and analyzes agent events
- **Wazuh Indexer**: stores and indexes alerts/events
- **Wazuh Dashboard**: analyst interface for monitoring and investigations

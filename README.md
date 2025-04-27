# Doraz Homelab - Infrastructure and Security Lab

## Overview

This is a small-scale homelab environment designed for infrastructure management and cybersecurity learning. Focus areas include:
- Secure deployment of LAN services
- Docker containerization
- Endpoint security monitoring using Wazuh SIEM

The lab is built for realism with production-like configurations and minimal external exposure.

---

## Topology

![image](https://github.com/user-attachments/assets/21b75559-2004-45b6-b413-3732276d312a)



---

## Devices

| Device          | Role                  | OS/Platform            | IP Address    |
|:----------------|:----------------------|:-----------------------|:--------------|
| Workstation     | Media Downloads/Testing| Windows 11            | 192.168.2.72  |
| Server          | Docker host            | Ubuntu 24.04 LTS      | 192.168.2.134 |
| NAS Storage     | Centralized Storage    | WD My Cloud EX2       | 192.168.2.54  |

---

## Services Deployed (Docker)

| Service           | Purpose                          | Network Exposure |
|:------------------|:---------------------------------|:-----------------|
| Plex Media Server | Media streaming (LAN-only)       | LAN only         |
| Portainer CE      | Docker container management      | LAN only         |
| Wazuh Stack       | SIEM Learning                    | LAN only         |

---

## Wazuh Agent Deployment

Wazuh agents are installed to monitor and forward security events from lab endpoints:

| Agent Location     | Purpose                          |
|:-------------------|:---------------------------------|
| Ubuntu Server (host) | Monitor Docker host activity     |
| Windows 11 Workstation | Monitor user activities and system events |

Event data is collected, processed by the Wazuh Manager, and visualized through the Wazuh Dashboard.

![image](https://github.com/user-attachments/assets/f37a26e9-7939-41db-97fd-40acc6d4f0d2)


---

## Security Controls

- UFW Firewall configured (default deny inbound, allow specific LAN ports)
- No real administrative services exposed to the WAN
- LAN-only access enforced for Plex, Portainer, and Wazuh Dashboard
- Docker containers configured with restart policies

---

## Skills Practiced

- SIEM Deployment and Agent Management
- Basic Alert Analysis and Event Triage (Authentication, System Events)
- Docker Compose Infrastructure Deployment
- Linux Firewall Hardening (UFW)
- Secure LAN Service Configuration

---




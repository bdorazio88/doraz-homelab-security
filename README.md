# doraz-homelab-security

## 📜 Project Overview
Small scale homelab environment focused on learning and implementing core cybersecurity concepts:
- Network segmentation
- Secure service deployment
- SIEM monitoring (Wazuh)
- Honeypot deployment (Cowrie)

---

## 🏠 Homelab v1 Diagram

                     [Internet]
                         |
                     (Router)
                     192.168.2.1
                         |
          ---------------------------------
         |                                 |
  [Gigabit 8-port Switch]           [Wi-Fi Devices]
         |                                 |
  -----------------------------    ------------------------------
 |             |               |   
 |             |               |
[Workstation] [Server]      [NAS Storage]
 WIN11         Ubuntu        WD My Cloud
 192.168.2.72  192.168.2.134    192.168.2.54

---

## 📡 Networking
- **Internet Service:** Fiber Gigabit — 1.5GB down / 940MB up
- **Router:** Bell Home Hub 3000 (192.168.2.1)
- **Switch:** Gigabit 8-Port Unmanaged Switch
- **LAN Subnet:** 192.168.2.0/24

---

## 🖥️ Compute & Storage
| Device        | OS / Details        | IP Address     |
|:--------------|:--------------------|:---------------|
| Workstation   | Windows 11 (ROG)     | 192.168.2.72   |
| Server        | Ubuntu 24.04 LTS (Docker Host) | 192.168.2.134  |
| NAS Storage   | WD My Cloud (8TB)    | 192.168.2.54   |

---

## 🔥 Services Deployed
| Service | Description | Exposure |
|:---|:---|:---|
| Plex Media Server | LAN media streaming | LAN only |
| Portainer CE | Docker management UI | LAN only |
| Wazuh SIEM Stack | Security event monitoring | LAN only |
| Cowrie Honeypot | Fake SSH server for attack capture | WAN exposed on port 22 |

---

##  Skills Practiced
- Threat detection and incident analysis
- Firewall hardening and network isolation
- Security event monitoring (Wazuh SIEM)
- Honeypot deployment and attacker data capture
- Infrastructure as Code (Docker Compose)

---

- Wazuh alert logs
- Firewall UFW rules
- Docker container status

---

# 🧹 Notes
- Internal IP addresses (192.168.x.x) are private and non-routable.
- No credentials, public IPs, or sensitive data exposed.

---


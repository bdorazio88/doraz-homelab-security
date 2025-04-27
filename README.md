# doraz-homelab-security
Small scale homelab environment focused on learning and implementing core cybersecurity concepts

==================================================================================
Doraz Homelab v1
==================================================================================
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

==================================================================================
Networking
==================================================================================
Internet Service: Fiber Gigabit — 1.5GB down / 940MB up

Router: Home Hub 3000 — 192.168.2.1

Switch: D-Link DGS-108 — 8-Port Gigabit Unmanaged
==================================================================================
Compute/Storage
==================================================================================
Workstation (WIN11): Asus ROG (Ryzen 5 5600X / RTX 3060 / 32GB RAM / 1.5TB SSD)

Server (Ubuntu 24 LTS): Mac mini (intel i5 / 8GB RAM / 512GB SSD)

NAS: WD 8TB My Cloud EX2 (2x Seagate Iron Wolf Pro 4TB drives) — 192.168.2.54
==================================================================================
Plex Setup
==================================================================================
[ NAS ]
    |
    v
[ Server (Ubuntu 24 LTS + Docker + Plex Server) ]
    |
    v
[ Plex Clients (TVs, Phones, etc.) ]
==================================================================================
Media Flow:
==================================================================================

Download media using the Windows workstation.

Media is saved directly onto the NAS instead of locally on Windows.

Plex server (running via Docker on Ubuntu server) scans NAS share for updates.

Plex clients (smart TVs, phones, tablets, etc.) access the Plex server while on 192.168.2.0/24 network.
==================================================================================
Services Running on Server
==================================================================================
- Plex Media Server 
  - Docker container: linuxserver/plex
  - Port: 32400 (TCP)
  - Purpose: Streams media from NAS to clients (TVs, phones, tablets)

- Portainer 
  - Docker container: portainer/portainer-ce + portainer/agent
  - Ports: 9000 (Portainer UI), 9001 (Agent)
  - Purpose: GUI management for Docker containers

- Wazuh Security Stack (Single Node)  
  - Manager: wazuh/wazuh-manager (1514-1515 TCP, 514 UDP, 55000 TCP)
  - Dashboard: wazuh/wazuh-dashboard (443 TCP)
  - Indexer: wazuh/wazuh-indexer (9200 TCP)
  - Purpose: Host security monitoring and analysis
==================================================================================
Admin Access URLs
==================================================================================
| Service  | URL                                  |
|:---------|:-------------------------------------|
| Plex     | http://192.168.2.134:32400/web        |
| Portainer| http://192.168.2.134:9000             |
| Wazuh    | https://192.168.2.134 (self-signed cert) |

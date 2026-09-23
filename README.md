# Homelab Infrastructure

<p align="center">
  <img src="https://img.shields.io/badge/Debian-CE0058?style=for-the-badge&logo=debian&logoColor=white" />
  <img src="https://img.shields.io/badge/Platform-OpenMediaVault-blue?style=for-the-badge&logo=openmediavault&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Portainer-13BEF9?style=for-the-badge&logo=portainer&logoColor=white"/>
  <img src="https://img.shields.io/badge/Nextcloud-0082C9?style=for-the-badge&logo=nextcloud&logoColor=white"/>
  <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white"/>
  <img src="https://img.shields.io/badge/Wiki.js-0066FF?style=for-the-badge&logo=wikidot&logoColor=white"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge"/>
</p>


This repository documents the configuration of my **personal homelab**, using **Docker** to orchestrate and maintain multiple self-hosted services.

> **Warning:** all sensitive values (IPs, exposed ports, passwords, tokens, keys) are replaced with `xxxx` / `example.local`. Never commit a real `.env`. 

## 🖥️ Main machine — NAS (Debian 12, OpenMediaVault)

| Service | Observed state | In this repo |
|----------|---------------|-------------|
| **OpenMediaVault** | Base OS | — (infra) |
| **Portainer CE** | Running (launched via `docker run`, `portainer_data` volume) | Mention only, no compose |
| **Nginx Proxy Manager** | Running | `docker/nginx/` |
| **Nextcloud** | Running (2 containers) | `docker/nextcloud/` |
| **Homer** | Running | `docker/homer/` |
| **Glance** | Running | `docker/glance/` (compose + `.env.example`, config not versioned) |
| **Diun** | Running | `docker/diun/` |
| **Portracker** | Running | `docker/portracker/` |
| **Posterizarr** | Running | `docker/posterizarr/` |
| **Speedtest Tracker** | Running | `docker/speedtest-tracker/` |
| **Wiki.js** | Running (2 containers) | `docker/wikijs/` |
| **Vert / Vertd** | Running | `docker/vert/` |
| **Monitoring** (Prometheus, Grafana, Alertmanager, cAdvisor, Node Exporter, Blackbox, Uptime Kuma) | Running (Alertmanager with default config, no versioned rules) | `docker/monitoring/` |
| **NetAlertX** | Running | `docker/netalertx/` |
| **Plex** | Running | Mention only, no compose |
| **WireGuard** | Running | Mention only (sensitive confs/keys, not versioned) |

## 📡 Small machine — Pi-hole + home automation (Debian 13)

| Service | Observed state | In this repo |
|----------|---------------|-------------|
| **Pi-hole** | Running | `docker/pihole/` |
| **Home Assistant** | Running (`network_mode: host`) | `docker/homeassistant/` |
| **Whisper** (wyoming-whisper, FR voice for HA) | Running | `docker/whisper/` |
| **Portainer Agent** | Running (managed by the main Portainer) | Mention only |

## 📁 Repository Structure
```
homelab/
├── docker/
│ ├── diun/
│ ├── glance/
│ ├── homeassistant/
│ ├── homer/
│ │ └── homer_data/
│ ├── monitoring/
│ │ └── prometheus/
│ ├── netalertx/
│ ├── nextcloud/
│ ├── nginx/
│ ├── pihole/
│ ├── portracker/
│ ├── posterizarr/
│ ├── speedtest-tracker/
│ ├── vert/
│ ├── whisper/
│ └── wikijs/
├── .gitignore
└── README.md
```

## 🧾 Deployment
Each service can be deployed individually:
```bash
cd docker/<service_name>
docker compose up -d
```
First copy `.env.example` files to `.env` and fill in the real values locally (never committed).

## 🚀 Future Improvements
- Set up Jellyfin
- Set up Pterodactyl
- Set up Overleaf

## 🪪 License
This project is released under the MIT License.
It is intended for educational and self-hosting reference purposes.

---

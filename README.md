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


This repository documents the configuration of my **personal homelab** running on **OpenMediaVault**, using **Docker** and **Portainer** to orchestrate and maintain multiple self-hosted services.

## 🧩 Overview
The goal of this project is to maintain a modular, reliable, and reproducible self-hosted environment for both experimentation and daily use.  
All services are deployed as isolated Docker containers with persistent volumes and defined networks.

## ⚙️ Core Components
| Service | Purpose | Stack |
|----------|----------|-------|
| **OpenMediaVault** | Base NAS operating system | Debian-based |
| **Portainer** | Container management and monitoring | Docker |
| **Nginx** | Reverse proxy and web routing | Docker |
| **Nextcloud** | Private cloud storage and file synchronization | Docker |
| **Homer** | Dashboard for accessing internal services | Docker |
| **Diun** | Docker image update notifier | Docker |
| **Posterizarr** | Poster generation for media libraries | Docker |
| **Speedtest Tracker** | Internet performance monitoring | Docker |
| **Wiki.js** | Internal documentation platform | Docker |

## 📁 Repository Structure
```
homelab/
├── docker/
│ ├── diun/
│ ├── homer/
│ ├── nextcloud/
│ ├── nginx/
│ ├── posterizarr/
│ ├── speedtest-tracker/
│ └── wikijs/
└── README.md
```

## 🧾 Deployment
Each service can be deployed individually:
```bash
cd docker/<service_name>
docker compose up -d
```

## 🚀 Future Improvements
- Set up Jellyfin
- Set up NetAlertX
- Set up Vert
- Set up Pterodactyl

## 🪪 License
This project is released under the MIT License.
It is intended for educational and self-hosting reference purposes.

---

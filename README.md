# 🏠 Security-First Self-Hosted Homelab

A zero-trust, VPN-only personal cloud built using open-source software.
This repository documents the **architecture, security model, and operational design**
of the homelab.

## 🎯 Design Goals
- VPN-only access (no public admin panels)
- Central authentication (SSO + 2FA)
- Clear separation of security, apps, and data
- Fully reproducible from documentation + backups

---

## 📐 High-Level Architecture

Internet  
❌  
↓  
WireGuard VPN  
↓  
Firewall + CrowdSec + Fail2Ban  
↓  
Reverse Proxy (HTTPS)  
↓  
SSO (Authentik)  
↓  
Application Services  

Full details:  
👉 [Architecture](docs/architecture.md)

---

## 🧱 Service Index

### 🔐 Security & Access
| Service | Purpose | Documentation |
|------|-------|---------------|
| WireGuard | Secure VPN access | docs/security.md |
| Firewall (UFW) | Network-level protection | docs/security.md |
| Fail2Ban | Brute-force prevention | docs/security.md |
| CrowdSec | Behavior-based intrusion detection | docs/security.md |
| Authentik | SSO + 2FA | docs/security.md |
| Vaultwarden | Secrets & password manager | docs/vaultwarden.md |
| Pi-hole | DNS-based blocking | docs/security.md |

---

### 🌍 Edge, DNS & Networking
| Service | Purpose | Documentation |
|------|-------|---------------|
| Cloudflare | DNS & domain management | docs/cloudflare.md |
| Nginx Proxy Manager | HTTPS reverse proxy | docs/docker.md |

---

### ☁️ Cloud, Sync & Knowledge
| Service | Purpose | Documentation |
|------|-------|---------------|
| Nextcloud | File cloud & collaboration | docs/architecture.md |
| Syncthing | Real-time device sync | docs/syncthing.md |
| Paperless-ngx | Document management | docs/architecture.md |
| BookStack | Knowledge base | docs/architecture.md |
| FreshRSS | RSS reader | docs/architecture.md |
| Standard Notes | Encrypted notes | docs/architecture.md |

---

### 🎬 Media & Photos
| Service | Purpose | Documentation |
|------|-------|---------------|
| Jellyfin | Media server | docs/architecture.md |
| Navidrome | Music streaming | docs/architecture.md |
| Immich | Photo & video backup | docs/architecture.md |
| Kodi | Media client | docs/architecture.md |

---

### 🤖 Media Automation
| Service | Purpose | Documentation |
|------|-------|---------------|
| Prowlarr | Indexer management | docs/architecture.md |
| Sonarr | TV automation | docs/architecture.md |
| Radarr | Movie automation | docs/architecture.md |
| Lidarr | Music automation | docs/architecture.md |
| Whisparr | Adult content automation | docs/architecture.md |
| Deluge | Torrent client | docs/architecture.md |
| Jellyseerr | Media requests | docs/architecture.md |
| Tdarr | Media transcoding | docs/architecture.md |

---

### 🐳 Platform & Operations
| Service | Purpose | Documentation |
|------|-------|---------------|
| Docker | Application runtime | docs/docker.md |
| Portainer | Docker management UI | docs/docker.md |
| Uptime Kuma | Service monitoring | docs/docker.md |
| OpenSpeedTest | Network testing | docs/docker.md |

---

## 💾 Backups & Recovery
- Encrypted, automated backups
- Off-system storage
- Regular restore testing

👉 [Backups & Disaster Recovery](docs/backups.md)

---

## 📜 Security Model
- Zero-trust design
- VPN-only access
- Secrets never committed to GitHub

👉 [Security Documentation](docs/security.md)

---

## 🧠 Philosophy

- GitHub stores **knowledge**
- Vaultwarden stores **secrets**
- Backups store **data**
- Docker provides **reproducibility**

If it cannot be rebuilt, it is considered broken.

---

## 📌 Status
This homelab is under continuous improvement.
Documentation is treated as part of the system.

# 🔁 Homelab Rebuild & Deployment Checklist

This document describes how to rebuild the entire homelab
from scratch after a failure.

The goal is full recovery using:
- GitHub documentation
- Vaultwarden secrets
- Encrypted backups

---

## 1️⃣ Base System Setup

- Install operating system (Debian / Ubuntu Server)
- Update system packages
- Set correct timezone and hostname
- Create non-root admin user
- Enable SSH access (key-based)

---

## 2️⃣ Host-Level Security

- Install and configure firewall (UFW / nftables)
- Allow only:
  - SSH (LAN/VPN)
  - WireGuard port
- Deny all other inbound traffic

- Install WireGuard
- Restore WireGuard configuration
- Verify VPN connectivity

- Install Fail2Ban
- Install CrowdSec
- Verify bans and logs

---

## 3️⃣ Docker Installation

- Install Docker Engine
- Install Docker Compose plugin
- Enable Docker at boot
- Verify Docker is running

---

## 4️⃣ Restore Repository & Documentation

- Clone homelab GitHub repository
- Review architecture and security docs
- Verify folder structure

GitHub is the source of truth for structure and decisions.

---

## 5️⃣ Secrets & Credentials

- Deploy Vaultwarden
- Restore Vaultwarden data from backup
- Verify access using Bitwarden clients

All passwords, tokens, and keys are retrieved from Vaultwarden.

---

## 6️⃣ Reverse Proxy & Identity

- Deploy Nginx Proxy Manager
- Deploy Authentik
- Restore configurations from backup
- Enable HTTPS
- Enforce SSO + 2FA

Verify login flow before exposing services.

---

## 7️⃣ Core Services Deployment

Deploy containers in this order:

1. Core / Management
   - Portainer
   - Uptime Kuma

2. Cloud & Knowledge
   - Nextcloud
   - Paperless-ngx
   - BookStack
   - FreshRSS
   - Standard Notes

3. Sync & Media
   - Syncthing
   - Jellyfin
   - Navidrome
   - Immich

4. Media Automation
   - Prowlarr
   - Sonarr
   - Radarr
   - Lidarr
   - Whisparr
   - Deluge
   - Jellyseerr
   - Tdarr

---

## 8️⃣ Data Restore

- Restore Docker volumes from backups
- Restore application data directories
- Verify file permissions
- Verify database integrity

---

## 9️⃣ DNS & Networking

- Restore Pi-hole configuration
- Verify DNS resolution
- Restore Cloudflare DNS records (if used)

---

## 🔟 Verification Checklist

- VPN access works
- No public services exposed
- Authentik SSO enforced
- Media libraries visible
- Sync services operational
- Monitoring dashboards healthy
- Backups running successfully

---

## ✅ Rebuild Complete

If all checks pass, the homelab is considered fully restored.

This checklist should be followed calmly and sequentially.

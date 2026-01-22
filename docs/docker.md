# 🐳 Docker & Container Layout

This homelab uses Docker to run all application services
while keeping security-critical components on the host.

## Why Docker is used
- Application isolation
- Predictable deployments
- Easy updates and rollbacks
- Clean separation between services

## What runs on the Host (NOT Docker)
The following services run directly on the host OS:

- WireGuard VPN
- Firewall (UFW / nftables)
- Fail2Ban
- CrowdSec

These components must remain available even if Docker stops.

## What runs in Docker
All user-facing and internal applications run as containers:

- Nginx Proxy Manager
- Authentik
- Vaultwarden
- Nextcloud
- Syncthing
- Jellyfin
- Immich
- Paperless-ngx
- BookStack
- FreshRSS
- ARR stack (Sonarr, Radarr, etc.)
- Monitoring tools (Uptime Kuma, Portainer)

## Docker Service Grouping

### 1. Core / Management
- Portainer
- Uptime Kuma

### 2. Security & Identity
- Nginx Proxy Manager
- Authentik
- Vaultwarden

### 3. Cloud & Knowledge
- Nextcloud
- Paperless-ngx
- BookStack
- FreshRSS
- Standard Notes

### 4. Media & Photos
- Jellyfin
- Navidrome
- Immich

### 5. Media Automation
- Prowlarr
- Sonarr
- Radarr
- Lidarr
- Whisparr
- Deluge
- Jellyseerr
- Tdarr

## Docker Networks

Multiple Docker networks are used to reduce attack surface:

- frontend  
  Exposed only to the reverse proxy

- backend  
  Internal communication between services

- media  
  Media services and automation stack

Services are attached only to the networks they require.

## Access Flow Inside Docker

Internet
  |
[ Nginx Proxy Manager ]
  |
[ Authentik ]
  |
[ Application Container ]
  |
[ Persistent Volumes ]

## Volumes & Persistence
All important data is stored in Docker volumes or bind mounts:
- Application data
- Databases
- Media files
- Configuration

Containers can be destroyed and recreated without data loss.

## Why this layout matters
- Limits lateral movement between services
- Makes troubleshooting easier
- Improves security and maintainability

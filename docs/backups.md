# 💾 Backups & Disaster Recovery

This homelab follows a **backup-first mindset**.
If something cannot be restored, it is considered already lost.

## Backup Principles
- Backups are encrypted
- Backups are stored off the main system
- Backups are automated
- Backups are periodically tested

## Backup Tooling
The primary backup tool used is Restic.

Why Restic:
- Strong encryption by default
- Snapshot-based backups
- Supports local disks and remote targets
- Easy restore process

## What Is Backed Up (CRITICAL)

### Application Data
- Nextcloud data directory
- Immich photo and video library
- Paperless-ngx documents
- BookStack uploads
- FreshRSS data

### Docker Volumes
- Application configuration volumes
- Databases (PostgreSQL, MariaDB)
- Authentik configuration
- Vaultwarden data directory

### Configuration & Metadata
- Docker compose files
- Scripts
- Important server configuration files
- This GitHub documentation repository

## What Is NOT Backed Up
- Container images
- Cache directories
- Temporary files
- Download-only media (can be re-acquired)

These can always be rebuilt or re-downloaded.

## Backup Targets
- External HDD or SSD
- Secondary internal disk
- Optional remote storage

At least one backup target must be physically separate from the server.

## Backup Frequency
- Daily automated backups
- Weekly integrity checks
- Monthly restore test

## Disaster Recovery Scenarios

### Case 1: Docker failure
- Reinstall Docker
- Restore volumes from backup
- Redeploy containers using compose files

### Case 2: OS failure
- Reinstall operating system
- Reinstall Docker and security tools
- Restore data and volumes
- Redeploy services

### Case 3: Disk failure
- Replace disk
- Restore all data from backup
- Rebuild using GitHub documentation

## Why this works
- GitHub stores the knowledge
- Backups store the data
- Docker provides reproducibility

Together, they allow full system recovery.

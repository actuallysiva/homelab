# 🔄 Syncthing

## What is Syncthing?
Syncthing is a peer-to-peer, real-time file synchronization tool.
It synchronizes folders directly between trusted devices without
relying on a central cloud service.

## Why Syncthing is used in this Homelab
Syncthing is used alongside Nextcloud to provide:

- Real-time file sync between devices
- Offline-first access
- No dependency on a web interface
- End-to-end encrypted transfers

## Syncthing vs Nextcloud

| Feature | Syncthing | Nextcloud |
|------|---------|-----------|
| Sync model | Peer-to-peer | Server-client |
| Offline usage | Excellent | Limited |
| Web access | No | Yes |
| Real-time sync | Yes | Partial |
| Central server | Not required | Required |

## Security Model
- All Syncthing traffic flows through WireGuard VPN
- Devices are manually approved
- Folder sharing is explicit and controlled
- No public discovery or relays enabled

## Use Cases
- Sync important documents
- Sync notes and configs
- Replicate critical folders to the server
- Lightweight backup between trusted devices

## Why it matters
If Nextcloud or the server goes down, Syncthing devices
continue syncing normally. This increases resilience
and reduces single points of failure.

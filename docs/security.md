# 🔐 Security Model

 This homelab follows a **Zero-trust, VPN-first security design**.

## Access Control
- No direct public access to services
- All access via WireGuard VPN
- Firewall restricts ports strictly

## Host-Level Protection
- WireGuard VPN
- UFW Firewall
- Fail2Ban for brute-force protection
- CrowdSec for behaviour-based blocking

## Identity & Authentication
- Authentik (SSO + 2FA) 

## Secrets Management
- Vaultwarden stores passwords, API tokens, recovery codes
- No secrets are committed to GitHub

## DNS & edge
- Pi-Hole blocks ads, trackers, and malware
- Cloudflare manages DNS and domain records
# 🔐 Vaultwarden & Secrets Management

Vaultwarden is the central secrets manager for this homelab.
It ensures that sensitive data is never stored in plaintext
configuration files or committed to GitHub.

## What is Vaultwarden?
Vaultwarden is a lightweight, self-hosted implementation
compatible with Bitwarden clients.

It provides encrypted storage for:
- Passwords
- API tokens
- Recovery codes
- Secure notes

## Why Vaultwarden is used
Vaultwarden solves a critical security problem:
how to manage secrets safely in a self-hosted environment.

Benefits:
- End-to-end encryption
- Centralized secret storage
- Multi-device sync
- Strong authentication and 2FA support

## What is stored in Vaultwarden
The following sensitive items are stored only in Vaultwarden:

- Admin passwords for services
- Database credentials
- Cloudflare API tokens
- Docker service credentials
- Recovery keys and backup passphrases
- WireGuard peer information (metadata only)

## What is NOT stored in GitHub
The following must NEVER be committed to GitHub:

- Passwords
- API keys
- Tokens
- Private keys
- `.env` files
- WireGuard private keys

GitHub stores documentation and structure, not secrets.

## Integration with the Homelab
- Vaultwarden runs behind Nginx Proxy Manager
- Access is protected by Authentik SSO
- Vaultwarden itself enforces 2FA
- Access is VPN-only

## Operational Rules
- All secrets must be rotated periodically
- Access to Vaultwarden is restricted to trusted devices
- Emergency recovery codes are backed up securely offline

## Why this matters
If the server is compromised or rebuilt:
- Secrets are not exposed in configuration files
- GitHub remains safe to share publicly
- Recovery is possible without credential leakage

Vaultwarden is a core pillar of the homelab’s security model.

# 🌍 Cloudflare

## What is Cloudflare?
Cloudflare is used in this homelab primarily as a DNS and domain
management provider. It acts as the public-facing edge for domain
resolution but does not directly expose services.

## Why Cloudflare is used
Cloudflare provides:
- Reliable DNS hosting
- Easy domain and subdomain management
- Optional DDoS protection
- Optional Cloudflare Tunnel support

## What Cloudflare is NOT used for
Cloudflare does NOT replace:
- WireGuard VPN
- Firewall rules
- Reverse proxy authentication
- Authentik SSO

Cloudflare is an edge convenience layer, not the primary security boundary.

## Access Model

Internet
  |
[ Cloudflare DNS ]
  |
❌ (No direct service exposure)
  |
[ WireGuard VPN ]
  |
[ Nginx Proxy Manager ]
  |
[ Authentik SSO ]
  |
[ Internal Services ]

## Cloudflare Tunnel (Optional)
Cloudflare Tunnel may be used selectively for:
- Read-only dashboards
- Temporary external access
- Non-sensitive services

Even when using Cloudflare Tunnel:
- Authentication remains mandatory
- Services are still protected by Authentik

## Security Considerations
- Cloudflare API tokens are stored in Vaultwarden
- Proxying can be disabled for sensitive services
- VPN-only access remains the default

## Why it matters
Cloudflare improves reliability and flexibility without
violating the zero-trust design of the homelab.

# 🚀 How to Deploy This Homelab

This guide explains how to deploy a security-first, self-hosted homelab
based on the design documented in this repository.

It is written for learners and homelab enthusiasts and avoids
hardcoding secrets or unsafe defaults.

---

## 🎯 Deployment Philosophy

- Security before convenience
- VPN-first, zero-trust access
- Documentation-driven setup
- Secrets are never committed

If you are new, follow this guide slowly and in order.

---

## 1️⃣ Prepare the Server

### Hardware
- x86_64 system recommended
- Minimum 8 GB RAM (16 GB preferred)
- Separate disk for data storage recommended

### Operating System
- Debian or Ubuntu Server
- Minimal installation
- SSH enabled

---

## 2️⃣ Secure the Host First (Before Docker)

Do NOT install applications yet.

### Required host-level components:
- Firewall (UFW or nftables)
- WireGuard VPN
- Fail2Ban
- CrowdSec

Rules:
- SSH allowed only from LAN or VPN
- No public access to applications
- Verify VPN access before proceeding

---

## 3️⃣ Install Docker

Once the host is secured:

- Install Docker Engine
- Install Docker Compose plugin
- Enable Docker at boot
- Verify Docker works correctly

Docker is used only for applications, not security tools.

---

## 4️⃣ Clone This Repository

```bash
git clone https://github.com/actuallysiva/homelab
cd homelab

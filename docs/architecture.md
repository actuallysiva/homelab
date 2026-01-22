# 🏦 Homelab Architecture

## Traffic Flow

  Internet
    
    |

  [ Cloudflare DNS ]
    
    |

  ❌ (No direct access)
    
    |

  [ WireGuard VPN ]

    |

  [ Firewall (UFW) ]

    |

  [ CrowdSec + Fail2Ban ]

    |

  [ Nginx Proxy Manager ]

    |

  [ Authentik SSO + 2FA ]

    |

  ------------------------------------------

  | Vaultwarden | Nextcloud | Syncthing    |
  | Immich      | Paperless | Jellyfin     |
  | Bookstack   | FreshRSS  | ARR services |
  ------------------------------------------

    |

  [ Pi-Hole DNS ]
    
    |
    
  [ Encrypted Backups ]
# Homelab Architecture

## Access Flow

Internet
  ❌
  |
  [ WireGuard VPN ]

  |

  [ Firewall (UFW) ]

  |

  [ CrowdSec + Fail2Ban ]

  |

  [ Nginx Proxy Manager ]

  |

  [ Authentik SSO ]

  |

  ----------------------------------

  | Nextcloud | Jellyfin | Immich |
  | Syncthing | Vaultwarder | ARR |
  
  ----------------------------------
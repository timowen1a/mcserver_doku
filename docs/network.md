# Netzwerk

## VPN

Software: WireGuard

Zweck:
- sichere Verbindung zwischen VPS und Heimserver

## Port Management

| Dienst | Host | Port | Zugriff |
|-|-|-:|-|
| SSH | VPS | 22 | öffentlich |
| Bedrock | VPS | 19132 | öffentlich |
| Velocity | VPS | 25565 | öffentlich |
| MariaDB | VPS | 3306 | nur WireGuard |
| WireGuard | VPS | 51820/udp | öffentlich |
| Lobby | Home Server | 25500 | nur Proxy über WireGuard |
| CB1 | Home Server | 25501 | nur Proxy über WireGuard |
| CB2 | Home Server | 25502 | nur Proxy über WireGuard |
| Farm | Home Server | 25503 | nur Proxy über WireGuard |
| Nether | Home Server | 25504 | nur Proxy über WireGuard |
| End | Home Server | 25505 | nur Proxy über WireGuard |
| PvP | Home Server | 25506 | nur Proxy über WireGuard |
| Minigames | Home Server | 25507 | nur Proxy über WireGuard |
| RCON Bereich | Home Server | (RCON-Port = Server-Port + 100) 25600–25699 | nur Admin / intern |
| SSH | Home Server | 6021 | öffentlich |

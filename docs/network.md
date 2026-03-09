# Netzwerk

## VPN

Software: WireGuard

Zweck:
- sichere Verbindung zwischen VPS und Heimserver

## Ports VPS

- 22 TCP → SSH
- 19132 UDP → Bedrock (Geyser) 
- 25565 TCP → Minecraft Proxy  
- 51820 UDP → WireGuard

## Ports Backend

- 6020 TCP → SSH (NAS)
- 6021 TCP → SSH (erster Server)
- 25560-25599 TCP → Minecraft Server (nur von VPS)
- 25660-25699 TCP → rcon (nur intern erreichbar)

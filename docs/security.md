# Security

Dieses Dokument beschreibt die Sicherheitsmaßnahmen des Minecraft-Server-Netzwerks.

Ziel ist es, Angriffsflächen zu minimieren und sicherzustellen, dass nur autorisierte Systeme miteinander kommunizieren.

---

# Sicherheitsarchitektur

Das Netzwerk verwendet eine **Proxy-Architektur**.

Internet  
↓  
Velocity Proxy (VPS)  
↓  
WireGuard VPN  
↓  
Backend Minecraft Server  


Wichtige Prinzipien:

- Der **Velocity Proxy ist der einzige öffentlich erreichbare Minecraft-Endpunkt**
- Backend-Server sind **nicht direkt aus dem Internet erreichbar**
- Kommunikation zwischen Proxy und Backend erfolgt **ausschließlich über WireGuard**
- Datenbankzugriffe erfolgen nur von autorisierten Servern

---

# Firewall (UFW)

Auf allen Servern wird **UFW (Uncomplicated Firewall)** verwendet.

## VPS

Erlaubte Ports VPS:

| Port | Protokoll | Zweck |
|-|-|-|
| 22 | TCP | SSH |
| 19132 | UDP | Bedrock |
| 25565 | TCP | Minecraft Proxy |
| 51820 | UDP | WireGuard |
| 3306 | TCP | MariaDB (nur intern) |


Erlaubte Ports Backend:

| Port | Protokoll | Zweck |
|-|-|-|
| 6020-6030 (Je nach Gerät) | TCP | SSH |
| 25600-25699 (nur von Heimnetz erreichbar) | TCP | RCON |
| 25500-25599 (nur von VPS erreichbar) | TCP | Minecraft Server |

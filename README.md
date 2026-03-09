# Minecraft Netzwerk

## Übersicht

Dieses Projekt beschreibt die Infrastruktur eines Minecraft-Netzwerks mit Proxy-Architektur.

### Technologien und wichtige Plugins

- Velocity
- Purpur
- MariaDB
- LuckPerms
- CarbonChat
- Geyser + Floodgate
- WireGuard VPN zwischen Backend und Frontend
- UFW Firewall
- Fortigate Firewall
- Fail2Ban

### Architektur

Spieler   ->   [Velocity Proxy]   ->   WireGuard   ->   [Heimserver]
- Lobby
- Farmwelten
- Citybuild
- zukünftige Spielmodi

### Ziele

- stabiles Netzwerk
- gute Performance
- hohe Sicherheit
- bleibende Spieler
- möglichst up to date

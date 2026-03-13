# Maintenance

Dieses Dokument beschreibt die Wartungsprozesse für das Minecraft-Netzwerk.
Ziel ist es, Updates, Backups und Neustarts konsistent und sicher durchzuführen.

# Grundprinzipien

- Wartungen mit Downtime möglichst außerhalb der Hauptspielzeiten durchführen
- Vor Änderungen immer ein Backup erstellen
- Änderungen zuerst auf Testservern prüfen
- Änderungen dokumentieren
- Giltet noch nicht bei der Einrichtung des Servers (Sicherung nach eigenem Ermessen)

# Regelmäßige Wartung (evtl. Automatisiert)

## Täglich

- Serverstatus prüfen (VPS und Backend)

```bash
systemctl status <servicename>
```

- Logs prüfen (VPS und Backend)

```bash
journalctl -u <servicename> -n <Zeilenanzahl>
```

- MariaDB Status prüfen (VPS)

```bash
systemctl status mariadb
```

## Wöchentlich

### Updates prüfen

- Minecraft Server Software (Purpur/Paper)
- Plugins
- Java Updates
- System Updates

Beispiel:

```bash
apt update
apt upgrade
```

### Server Logs prüfen

Speziell auf folgende Dinge achten:

- WARN
- ERROR
- Plugin Exceptions
- Performance Probleme

### Speicherplatz prüfen

```bash
df -h
```

Wichtig für:

- Welt Daten
- Logs
- Backups

# Server Neustart

Server können über systemd neu gestartet werden.

Beispiel:

```bash
systemctl restart <servicename>
```

Oder alle Server:

```bash
systemctl restart lobby cb1 farm nether end
```

# Updates durchführen

## Minecraft Server (Nur wenn unbedingt nötig oder erwünscht wegen Pluginkompatibilität)

1. Server stoppen

```bash
systemctl stop <servicename>
```

2. Neue Server-JAR herunterladen

3. Alte JAR ersetzen

4. Server starten

```bash
systemctl start <servicename>
```

## Plugins

1. Server stoppen
2. Plugin ersetzen
3. Server starten
4. Logs prüfen

# Datenbank Wartung

MariaDB läuft auf dem VPS.

## Status prüfen

```bash
systemctl status mariadb
```

## Verbindungen prüfen

```sql
SHOW PROCESSLIST;
```

## Host Blockierungen aufheben

```sql
FLUSH HOSTS;
```

# Backups

Folgende Daten müssen regelmäßig gesichert werden:

- Minecraft Welten
- Plugin Konfigurationen
- Datenbanken
- Velocity

# Notfallmaßnahmen

## Server startet nicht

1. Logs prüfen

```bash
journalctl -u <server> -f
```

2. Plugin Fehler prüfen
3. Startscript prüfen

## Datenbankverbindung funktioniert nicht

Prüfen:

- MariaDB läuft
- Firewall Regeln
- WireGuard Verbindung
- Datenbank Benutzerrechte

# Wartungsmodus

Bei größeren Änderungen kann der Wartungsmodus aktiviert werden.

Spieler sollten vorher informiert werden.

Typische Schritte:

1. Spieler informieren
2. Server stoppen
3. Änderungen durchführen
4. Server starten
5. Funktion prüfen

# Verantwortlichkeiten

- Server Infrastruktur: VPS + Home Server
- Datenbank: MariaDB
- Proxy: Velocity
- Netzwerk: WireGuard

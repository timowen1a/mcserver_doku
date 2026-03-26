# Server auf neuen Host migrieren

- Ubuntu installieren
- SSH-Port anpassen
- Portweiterleitung einrichten/anpassen
- apt update && apt upgrade -y
- Ufw installieren und konfigurieren
- Wireguard installieren und konfigurieren
- Serverfolder migrieren
- Servicefile migrieren
- Service aktivieren (systemctl enable)
- Richtiger port in der Ufw freigeben auf das Interface 10.10.0.0/24
- Server starten und testen

# Server auf bestehenden Host migrieren

- Serverfolder migrieren
- Servicefile migrieren
- Service aktivieren (systemctl enable)
- Serverport in der Ufw freigeben auf das Interface 10.10.0.0/24
- Server starten und testen

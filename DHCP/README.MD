# DHCP-Server Installation auf einem Raspberry Pi mit `dnsmasq`

Dieses Tutorial erklärt, wie Sie einen DHCP-Server auf einem Raspberry Pi unter Verwendung von `dnsmasq` installieren und konfigurieren.

## Voraussetzungen

- Raspberry Pi mit Raspberry Pi OS installiert.
- Feste IP-Adresse für den Raspberry Pi im Netzwerk.
- SSH-Zugriff oder direkter Zugang zum Terminal des Raspberry Pi.

## Schritte

### Schritt 1: System aktualisieren

Aktualisieren Sie Ihr System, um sicherzustellen, dass alle Pakete auf dem neuesten Stand sind:

```bash
sudo apt-get update
sudo apt-get upgrade

### Schritt 2: Installation von dnsmasq

Installieren Sie den DHCP-Server dnsmasq:

```bash
sudo apt-get install dnsmasq

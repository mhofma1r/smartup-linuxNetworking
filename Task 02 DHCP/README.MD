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
```

### Schritt 2: Installation von dnsmasq

Installieren Sie den DHCP-Server dnsmasq:

```bash
sudo apt-get install dnsmasq
```
### Schritt 3: Konfiguration von dnsmasq

Nach der Installation müssen Sie die Konfigurationsdatei von dnsmasq, `dnsmasq.conf`, bearbeiten. Sichern Sie zuerst die Originalkonfigurationsdatei:

```bash
sudo mv /etc/dnsmasq.conf /etc/dnsmasq.conf.orig
```
### Schritt 3.a: Konfiguration von dnsmasq

Erstellen Sie dann eine neue Konfigurationsdatei mit einem Texteditor Ihrer Wahl, zum Beispiel nano:
``` bash
sudo nano /etc/dnsmasq.conf
```
In die neue Konfigurationsdatei fügen Sie die folgenden Zeilen ein, die dnsmasq als DHCP-Server in Ihrem Netzwerk konfigurieren. Diese Beispielkonfiguration legt einen Bereich von IP-Adressen fest, die vergeben werden können, sowie die Dauer, für die die IP-Adressen gültig sind. Passen Sie die Werte entsprechend Ihrem Netzwerk an:
```bash
interface=eth0                              # Das Netzwerkinterface, das dnsmasq verwenden soll
dhcp-range=192.168.1.50,192.168.1.150,12h   # IP-Bereich und Lease-Zeit

```
Speichern Sie die Datei und schließen Sie den Editor mit se Testenkombination Strg + x und bestätigen sie flogende frage zur korrektheit des Dateinamens mit y (für yes)
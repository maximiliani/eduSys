# eduSys

## Funktionen
- Zentrale Homeverzeichnisse
- Zentrale Benutzer-/Speicher-/Mailverwaltung
- Identitätsprovider für Föderation (z.B. mit DFN-AAI) --> Shibboleth
- Druckserver (CUPS/samba4) (über Subnetting? oder Gruppen)
- Nextcloud
- Moodle (LMS)
- Zammad (Servicedesk)
- evtl. Gitlab
- DNS
- DHCP
- Firewall
- RADIUS (Anmeldung an WLAN/LAN) oder eduroam
- evtl. gerätespezifische WLAN-Passwörter --> siehe [KIT-IOT](https://www.scc.kit.edu/dienste/internet-of-things.php)
- evtl. anpassbare DNS/DHCP Einstellungen für Schulleitung --> siehe NETVS am KIT
- Setupassistent
  - Erscheinungsbild
  - Passwort
  - sonstige Daten
- zuerst: "Vollwertige" Desktops
  - Benutzerauthentifizierung
  - Netboot?
  - HTTP-/APT-Cache
  - vorerst einfacher umzusetzen
  - Software nachinstallierbar (Whitelist) ohne sudo --> Softwarestore (pamac, apt, ...)
- Thinclients aka Raspberry Pi
  - PXEboot
  - Varianten: lokaler Desktop, zentraler Desktop (auf Server gehostet)
  - Keine SD-Karte oder Festplatte nötig

## Umsetzung

Benutzerverwaltung:
- openLDAP 
- Script für Input von schILD NRW
- Kerberos

Nextcloud:
- Automatische Syncronisation über Nextcloud client
- Verzeichnisse von Gruppen/Circles erscheinen automatisch auch auf Endgeräten und können selbst verwaltet werden
- Talk/BBB
- Collabora Online
- Groupware
- Signieren und Zustimmen von Dokumenten --> evtl. Elternzugriff
- 2FA für Lehrer und Eltern (mehrere Möglichkeiten anbieten)
- Moodle-Integration
- Zammad-Integration
- sonstige Tools (z.B. Pico-CMS, ...)

Desktop-OS: 
- Arch --> Manjaro
- möglichst einfach gestaltet
- Wahl zwischen Gnome und KDE

Softwarestore
- CLI-Tool das erlaubte Software vom Hauptserver abfragt
- Auf Hauptserver werden Liste und Paketcache vorgehalten
- basiert auf Pamac

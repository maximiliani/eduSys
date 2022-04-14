# Generelles

```
# Als root ausführen
$ Als aktueller Nutzer
```
# Vor Chroot

Orientiert am ARCH-Wiki [Install-guide](https://wiki.archlinux.org/title/Installation_guide)

## Tastaturlayout festlegen
Um alle verfügbaren Layouts anzuzeigen kann 
```
$ ls /usr/share/kbd/keymaps/**/*.map.gz
``` 
genutzt werden.

Um das Layout festzulegen kann man dann den Namensteil an [loadkeys(1)](https://man.archlinux.org/man/loadkeys.1) übergeben. Als Beispiel für das Deutsche Layout:
```
# loadkeys de-latin1
```

## Bootmodus kontrollieren 

Hierfür zeigt man den Inhalt des [efivars](https://wiki.archlinux.org/title/Efivars) Ordners an:
```
$ /sys/firmware/efi/efivars
``` 
Wenn dieser Befehl den Ordner ohne Fehler anzeigt ist das System im UEFI Modus hochgefahren worden. Wenn dieser Ordner nicht existiert wurde das System wahrscheinlich im BIOS Modus hochgefahren.

## Internetverbindung sicherstellen

Am besten testet man die Internetverbindung in dem einen Server ```ping```ed von dem man weiß dass er läuft. 
```
$ ping archlinux.org
```

## Systemuhrzeit einstellen

Die Systemuhrzeit kann man über [timedatectl(1)](https://man.archlinux.org/man/timedatectl.1) einstellen. Hierfür nutzt man am besten NTP.
```
# timedatectl set-ntp true
```

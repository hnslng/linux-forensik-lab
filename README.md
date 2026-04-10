# ABB IT-Fahndung Training - Linux Forensik Lab

**Interaktive Trainingsplattform fur operative forensische Datensicherung**  
Entwickelt fur das Amt fur Betrugsbekampfung (ABB) - Steuerfahndung.

## Uber das Projekt

Browserbasierte Single-Page-Application fur die Ausbildung in Linux-basierter Datentragerforensik. Vollstandig offline-fahig, kein Server erforderlich. Integriertes simuliertes Terminal fur praxisnahe Ubungen.

Alle Verfahren orientieren sich an NIST SP 800-86 und ISO/IEC 27037.

## Features

- **22 Lernkapitel** - Vom forensischen Grundlagenwissen bis zur Zeitlinienanalyse
- **Simuliertes Terminal** - Vollstandiges Bash-Terminal mit virtuellem Dateisystem, 25+ Befehlen, auto-offnend bei Ubungen
- **Referenz-Panel** - Seitliche Quick-Reference mit allen Befehlen und Kopier-Buttons
- **Slide-basierte Navigation** - Pro Abschnitt eigene Slide mit Vor/Zuruck-Navigation
- **Schritt-fur-Schritt-Ubungen** - Ankuendigungs-Slide, Befehl, erwartete Ausgabe, Erklarungen
- **Dark Forensik Theme** - Professionelles dunkles Interface im Terminal-Stil
- **Fortschritts-Tracking** - Kapitel als erledigt markieren (localStorage)
- **CTF-Challenges** - 5 praktische Challenges mit Losungen

## Kapitel

| # | Kapitel | Inhalt |
|---|---------|--------|
| 1 | Grundlagen | Devices, Partitionen, Dateisysteme, forensischer Workflow |
| 2 | Datentrager-Identifikation | lsblk, fdisk, parted, hdparm |
| 3 | Imaging | dd, dc3dd, dcfldd, E01-Formate |
| 4 | Hashing & Integritat | SHA-256, MD5, Verifikation |
| 5 | Mounten & Analyse | Read-only Mounts, Loop-Devices, Offset-Berechnung |
| 6 | Hex-Analyse | xxd, hexdump, binare Analyse |
| 7 | Strings | strings, grep, Mustererkennung |
| 8 | Dateisysteme | ext*, NTFS, FAT32 Internals |
| 9 | Wiping | Sicheres Loschen, dd destroy |
| 10 | Artefaktanalyse | Logs, Metadaten, Timeline |
| 11 | Case Study | Interaktiver 12-Schritt-Workflow |
| 12 | Image-Formate | RAW, E01, AFF Vergleich |
| 13 | Dateivergleich | diff, cmp, Hash-Vergleich |
| 14 | Protokollierung | script, Dokumentation, Chain of Custody |
| 15 | Write-Blocker | Hardware & Software Write-Blocking |
| 16 | Sicheres Loschen | wipe, shred, DoD-Standard |
| 17 | Best Practices | Forensische Grundsatze, Fallstricke |
| 18 | Tools | Autopsy, Sleuth Kit, dd, xxd |
| 19 | Datenrettung | testdisk, photorec |
| 20 | Memory-Forensik | RAM-Dump Analyse |
| 21 | Netzwerkforensik | PCAP, Netflow, Log-Analyse |
| 22 | Zeitlinienanalyse | Timeline-Erstellung und Analyse |

## Simuliertes Terminal

Das integrierte Terminal simuliert eine echte Bash-Umgebung:

- **25+ Befehle**: ls, cd, pwd, mkdir, touch, cat, tree, dd, sha256sum, md5sum, mount, xxd, strings, grep, find, script, uname, file, stat, history, clear, help
- **Virtuelles Dateisystem**: Verzeichnisse, Dateien, realistische Baumstruktur
- **Brace-Expansion**: `mkdir -p case-001/{images,mounts,hashes}`
- **Protokollierung**: `script` startet Session-Recording, `exit` beendet es
- **Auto-Offnen**: Terminal offnet sich automatisch bei Ubungs-Slides
- **Block-Cursor**: Realistischer Terminal-Look mit blinkendem Cursor

## Projektstruktur

```
forensik-lab/
  index.html                    # SPA (77 Zeilen)
  assets/
    css/
      style.css                 # Dark Forensik Theme (~2470 Zeilen)
      gamification.css          # Gamification Styles
    js/
      app.js                    # Router, Slide-Parser, Navigation (~690 Zeilen)
      chapters.js               # 22 Kapitel (~2210 Zeilen)
      terminal.js               # Simuliertes Terminal + virtuelles FS (~1130 Zeilen)
      reference.js              # Referenz-Panel (~640 Zeilen)
      labs.js                   # Labs
      labs-interactive.js       # Interaktive Labs
      challenges.js             # CTF-Challenges
      missions.js               # Missionen
      gamification.js           # Gamification
      ui-improvements.js        # UI-Erweiterungen
      progress.js               # Fortschritts-Tracking
      certification.js          # Zertifizierung
      cheatsheet.js             # Cheatsheet
  datasets/                     # Forensische Datensatze
    auth.log                    # SSH Brute Force Logs
    apache_access.log           # Webserver-Logs
    syslog                      # Systemlogs
    usb_case01.img              # 1MB USB-Image (FAT32)
    mbr_sample.bin              # 512B Master Boot Record
    memory_dump_sample.raw      # 64KB RAM-Dump
    original.txt                # Original-Datei
    manipulated.txt             # Manipulierte Datei
    hashes/                     # SHA-256 Prufsummen
```

** Gesamt: ~10.770 Zeilen Code**

## Schnellstart

```bash
git clone https://github.com/hnslng/linux-forensik-lab.git
cd linux-forensik-lab
firefox forensik-lab/index.html
```

Kein Server notig - einfach `index.html` im Browser offnen.

## Technologie

- Vanilla HTML5, CSS3, JavaScript (ES6+)
- Single Page Application mit Hash-Routing
- Slide-Parser: Splittet HTML nach `<h2 class="section-title">` in eigene Slides
- Custom CSS Grid/Flexbox Layout
- localStorage fur Fortschritt und Einstellungen
- Keine externen Abhangigkeiten, komplett offline

## Lizenz

MIT License

## Kontakt

**Hannes Lang** - ABB IT-Fahndung Training

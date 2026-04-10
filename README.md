# Linux Forensik Lab

**Interaktive Trainingsplattform für operative forensische Datensicherung**
Entwickelt für das Amt für Betrugsbekämpfung (ABB) – Steuerfahndung.

## Über das Projekt

Browserbasierte Single-Page-Application für die Ausbildung in Linux-basierter Datenträgerforensik. Vollständig offline-fähig, kein Server erforderlich. Integriertes simuliertes Terminal mit Pipe-, Chain- und Redirect-Support für praxisnahe Übungen.

Alle Verfahren orientieren sich an NIST SP 800-86 und ISO/IEC 27037.

## Features

- **22 Lernkapitel** in 3 Modulen – von Grundlagen bis Zeitlinienanalyse
- **Simuliertes Terminal** – Pipes (`|`), Chain (`&&`), Redirect (`>`), 30+ Befehle
- **Inline-Terminals** – Direkt in den Übungen eingebettet
- **Erwartete Ausgaben** – Jede Übung zeigt was das Terminal ausgeben soll
- **Entscheidungsfragen** – Interaktive Quizze am Ende jedes Kapitels
- **Gamification** – Achievements, Fortschritts-Tracking, Kapitel als erledigt markieren
- **Referenz-Panel** – Seitliche Quick-Reference mit allen Befehlen und Kopier-Buttons
- **Slide-basierte Navigation** – Pro Abschnitt eigene Slide mit Vor/Zurück
- **Dark Forensik Theme** – Professionelles dunkles Interface mit Inter + JetBrains Mono

## Module

| Modul | Kapitel | Inhalt |
|-------|---------|--------|
| **01 – Grundlagen** | 1–11 | Devices, Partitionen, Imaging, Hashing, Mounten, Hex-Analyse, Strings, Dateisysteme, Wiping, Artefaktanalyse, Case Study |
| **02 – Vertiefung** | 12–18 | Image-Formate, Vergleiche, Protokollierung, Write-Blocker, Sicheres Löschen, Best Practices, Tools |
| **03 – Analyse** | 19–22 | Datenrettung, Memory-Forensik, Netzwerkforensik, Zeitlinienanalyse |

## Terminal-Simulation

Das integrierte Terminal simuliert eine echte Bash-Umgebung:

- **30+ Befehle**: ls, cd, pwd, mkdir, cat, tree, dd, dc3dd, lsblk, fdisk, parted, xxd, strings, grep, sha256sum, md5sum, mount, umount, blkid, hdparm, fls, mmls, istat, icat, nvme, blockdev, script, find, stat, file, sort, diff, cmp, uname, whoami, history, date, echo, help, sync
- **Pipe-Support**: `strings image.img | grep -i "password"`
- **Chain-Support**: `mkdir -p /mnt/x && mount -o ro image.img /mnt/x`
- **Redirect-Support**: `sha256sum /dev/sdb > hashes/original.sha256`
- **Virtuelles Dateisystem**: Verzeichnisse, Dateien, realistische Baumstruktur
- **Brace-Expansion**: `mkdir -p case-001/{images,mounts,hashes}`
- **Session-Recording**: `script` startet Protokollierung, `exit` beendet sie

## Projektstruktur

```
forensik-lab/
  index.html                    # SPA Hauptanwendung
  assets/
    css/
      style.css                 # Haupt-CSS (Dark Theme, Layout, alle Komponenten)
      gamification.css          # Gamification Styles
    js/
      app.js                    # Router, Slide-Parser, Navigation
      chapters.js               # 22 Kapitel + Willkommensseite
      terminal.js               # Terminal-Simulation + virtuelles FS
      reference.js              # Referenz-Panel
      app.js                    # Hauptanwendung (Routing, Slides)
      gamification.js           # Achievement-System
      achievements.js           # Achievements
      progress.js               # Fortschritts-Tracking
      labs.js / labs-interactive.js  # Labor-Übungen
      challenges.js             # CTF-Challenges
      missions.js               # Missionen
      cheatsheet.js             # Cheatsheet
      certification.js          # Zertifizierung
      ui-improvements.js        # UI-Erweiterungen
  datasets/                     # Forensische Datensätze
    auth.log / apache_access.log / syslog
    usb_case01.img / mbr_sample.bin / memory_dump_sample.raw
    original.txt / manipulated.txt / hashes/
```

## Schnellstart

```bash
git clone https://github.com/hnslng/linux-forensik-lab.git
cd linux-forensik-lab/forensik-lab
# index.html im Browser öffnen – kein Server nötig
```

## Technologie

- Vanilla HTML5, CSS3, JavaScript (ES6+)
- Single Page Application mit Hash-Routing
- Google Fonts: Inter (UI) + JetBrains Mono (Code/Terminal)
- Custom CSS Grid/Flexbox Layout
- localStorage für Fortschritt und Einstellungen
- Keine externen Abhängigkeiten, komplett offline

## Lizenz

MIT License

## Kontakt

**Hannes Lang** – ABB IT-Fahndung Training

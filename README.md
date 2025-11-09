# 🌐 Website-Beweissicherung ("Web Evidence Capture")

Dieses Projekt dokumentiert Webseiten **rechtssicher und automatisiert**.  
Es zeigt nachweisbar, dass eine Webseite **zu einem bestimmten Zeitpunkt aktiv** war und welchen **Inhalt sie genau hatte**.

Dies ist besonders nützlich für:
- juristische Nachweise (z. B. Beleidigungen, Urheberrechtsverletzungen, Preisangebote),
- Archivierung von Online-Inhalten,
- Compliance- oder Audit-Zwecke.

---

## ⚙️ Funktionsweise

Das Skript `web_evidence_capture_git.py` führt automatisch folgende Schritte aus:

1. **Aufrufen einer Webseite**  
   – lädt den Quellcode und erstellt einen Screenshot.

2. **Erstellen eines Zeitstempels**  
   – der aktuelle Zeitpunkt wird automatisch in UTC protokolliert.

3. **Speichern der Daten**  
   – HTML-Datei, Screenshot und Metadaten werden in einem eigenen Zeitordner abgelegt.

4. **Erzeugen von Prüfsummen (SHA256)**  
   – jede Datei erhält eine kryptografische Signatur gegen Manipulation.

5. **Digitale Signatur (GPG)**  
   – beweist, dass die Dateien vom ursprünglichen Ersteller stammen.

6. **Blockchain-Zeitstempel (OpenTimestamps)**  
   – belegt, dass die Daten zu diesem Zeitpunkt existierten.

7. **Automatischer Upload ins GitHub-Repository**  
   – jede Sicherung wird einzeln versioniert und hochgeladen.

---

## 📁 Verzeichnisstruktur

```text
gaertner/
├── web_evidence/
│   └── 2025-11-09_12-30-45/
│       ├── page.html                  → Quellcode der Webseite
│       ├── screenshot.png             → Screenshot der Seite
│       ├── metadata.txt               → Zeitstempel & Prüfsummen
│       ├── 2025-11-09_12-30-45.zip    → Archiv aller Dateien
│       ├── 2025-11-09_12-30-45.zip.asc → Digitale Signatur (GPG)
│       └── 2025-11-09_12-30-45.zip.ots → Blockchain-Zeitstempel
├── README.md
└── .gitignore / .gitattributes

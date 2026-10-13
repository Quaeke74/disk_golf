# Discgolf Scorer

Kleine Web-App zum Erfassen und Auswerten von Discgolf-Runden auf dem Handy. Entstanden für Runden mit Kolleginnen und Kollegen auf der Anlage Roderbruch Nord in Hannover (15 Bahnen). Weitere Plätze lassen sich in der App anlegen.

Die App läuft komplett im Browser, auch offline. Es gibt keinen Server und keine Anmeldung. Alle Daten bleiben auf dem Gerät, auf dem gespielt wird.

## Funktionen

- **Runde spielen:** Platz und Datum wählen, 1 bis 8 Spieler, eine Bahn pro Bildschirm mit großen Plus/Minus-Tasten. Jeder Tipp wird sofort gespeichert, eine unterbrochene Runde läuft beim nächsten Öffnen weiter. Der Bildschirm bleibt während der Runde an.
- **Ranking:** pro Platz und Zeitraum (Saison, letzte 12 Monate, gesamt). Gewertet wird der Durchschnitt der besten X Runden relativ zum Par. X ist einstellbar, Standard ist 5.
- **Bahnstatistik:** Durchschnitt pro Bahn, schwerste und leichteste Bahn, Hinweis bei unpassend wirkendem Par.
- **Spielerdetails:** Verlauf, Bestleistung, Schnitt der letzten fünf Runden, Stärken und Schwächen nach Bahn.
- **Stammdaten:** Plätze mit Par, Länge und Notiz pro Bahn, Spielerverwaltung.
- **Datensicherung:** Export und Import als JSON-Datei, zusätzlich CSV-Export für Excel.

## Installation auf dem Handy

Die App muss über die GitHub-Pages-Adresse geöffnet und dann als App installiert werden. Nur so bleiben die Daten dauerhaft gespeichert.

**iPhone (Safari):** Adresse öffnen, auf „Teilen“ tippen, dann „Zum Home-Bildschirm“.

**Android (Chrome):** Adresse öffnen, im Drei-Punkte-Menü „App installieren“ oder „Zum Startbildschirm hinzufügen“ wählen.

Danach die App immer über das Symbol auf dem Home-Bildschirm starten.

## Datensicherung

Jedes Gerät hat seinen eigenen Datenstand, es gibt keine automatische Synchronisierung.

- In der App unter **Stammdaten → Sicherung exportieren** regelmäßig eine Sicherung erstellen und z. B. in iCloud Drive oder Google Drive ablegen.
- **Sicherung laden** ersetzt alle Daten auf dem Gerät durch den Stand der Datei. Damit lässt sich der Stand auch auf ein neues Handy übertragen, zwischen iPhone und Android in beide Richtungen.
- Vor dem Löschen der App vom Home-Bildschirm unbedingt sichern, sonst sind die Daten weg.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette App (Oberfläche, Logik, Gestaltung) |
| `manifest.webmanifest` | Name, Farben und Symbol für die Installation als App |
| `sw.js` | Service Worker für den Offline-Betrieb |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | App-Symbole |

## Bereitstellung über GitHub Pages

1. Alle Dateien in dieses Repository hochladen.
2. Unter **Settings → Pages** als Quelle den Branch `main` und den Ordner `/ (root)` wählen.
3. Nach etwa einer Minute ist die App erreichbar unter `https://<benutzername>.github.io/<repository>/`.

## Updates einspielen

1. Die geänderten Dateien hochladen und die alten überschreiben.
2. In `sw.js` die Versionsnummer in der Zeile `const CACHE = 'dg-scorer-v2';` um eins erhöhen. Sonst zeigt das Handy weiter die alte Version an.
3. Auf dem Handy die App einmal öffnen, schließen und wieder öffnen.

Die gespeicherten Runden bleiben bei einem Update erhalten.

## Anpassungen

- **Hauptfarbe:** In `index.html` ganz oben im Stil-Bereich steht die Zeile `--brand:#c4122f;`. Dort lässt sich das MHH-Rot durch einen anderen Farbwert ersetzen.
- **Par-Werte und Plätze** werden direkt in der App unter Stammdaten gepflegt, nicht im Code.

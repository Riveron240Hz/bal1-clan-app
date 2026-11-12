# #Bal1 Clan Control — installierbare Web-App (PWA)

Dies ist eine responsive, statische Web-App mit **Mitgliedern, Zahlungsübersicht, Projekten, News und JSON-Backups**. Sie enthält **Beispieldaten**, keine echten Serverdaten.

## Schnellstart

1. ZIP entpacken.
2. Alle Dateien und Ordner in ein GitHub-Repository hochladen (oder den Inhalt in den bestehenden Website-Ordner kopieren).
3. GitHub: **Settings → Pages → Build and deployment → Deploy from a branch → main / (root) → Save**.
4. Nach der Veröffentlichung die HTTPS-Adresse deiner GitHub-Pages-Seite aufrufen. Für Installierbarkeit muss die Seite über HTTPS laufen.
5. **Android:** Chrome → Menü → „App installieren“ (je nach Browser „Zum Startbildschirm hinzufügen“). **iPhone:** Safari → Teilen → „Zum Home-Bildschirm“ → „Hinzufügen“.

## Lokal ausprobieren

Im Projektordner mit installiertem Python:

```bash
python -m http.server 8000
```

Danach `http://localhost:8000` öffnen. Nicht die Datei `index.html` direkt mit `file://` starten; das würde Service Worker/Installieren verhindern.

## Funktionsumfang

- Übersicht und Mitgliederverwaltung (Minecraft-Namen, Rollen)
- Clan-Kasse: Gebührenhöhe, bezahlte Mitglieder, Summen (nur manuelle Markierung)
- Projekte und Fortschrittsregler
- News/Ankündigungen
- JSON-Export und -Import
- Offline-Unterstützung durch Service Worker, App-Icon und Manifest

## Wichtige Einschränkungen

- **Kein gemeinsamer Live-Zugriff.** Die Daten liegen ausschließlich im Local Storage des jeweiligen Browsers. Es gibt keine zentrale Datenbank. Export/Import zum manuellen Übertragen.
- **Keine Discord- oder HugoSMP-Anbindung**, keine echte Online-Erkennung, keine Authentifizierung und keine tatsächlichen Geldtransfers.
- **Keine sicheren Adminrechte.** Die App ist eine lokale Demo; für gemeinsame Nutzung mit sicheren Benutzerkonten braucht es ein Backend (z. B. Supabase), ein Berechtigungssystem und ggf. Discord-OAuth.
- GitHub Pages veröffentlicht die Dateien öffentlich. **Keine Tokens, Passwörter, privaten Discord-Webhooks oder API-Keys** in JavaScript/Repository eintragen.
- Der initiale Datensatz ist zu Demonstrationszwecken angelegt, nicht als tatsächlicher Clanstand zu verstehen.

## Struktur

- `index.html` – Benutzeroberfläche
- `styles.css` – futuristisches, responsives Layout
- `app.js` – lokale Funktionen und Datenverwaltung
- `manifest.webmanifest` – PWA-Metadaten
- `sw.js` – Offline-Cache
- `icons/` – App-Icons

## Nächster Ausbauschritt

Gemeinsames Backend und rollenbasierte Anmeldung; dann können Clanmitglieder plattformübergreifend dieselben Daten verwenden. Ohne Backend ist dies bewusst nur eine lokale App.

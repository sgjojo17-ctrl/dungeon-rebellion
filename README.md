# Dungeon Rebellion — Handy- und Online-Version

Eigenständiger Fantasy-Kartenspiel-Prototyp mit eigener Gestaltung. Kein offizielles Produkt und keine Kopie der Originalkarten.

## Lokal testen
Voraussetzung: Node.js 18 oder neuer.
```bash
npm install
npm start
```
Dann `http://localhost:3000` öffnen.

## Öffentlich mit Freunden spielen
Das Spiel braucht einen laufenden Node.js-Webserver, weil die Spielerzüge live über Socket.IO synchronisiert werden. Eine statische Website allein reicht nicht.

### Einfacher Weg: GitHub + Render
1. Erstelle ein Repository bei GitHub.
2. Lade den gesamten Inhalt dieses Projektordners in das Repository hoch (inklusive `package.json`, `server.js`, `render.yaml` und `public/`).
3. Öffne Render und verbinde dein GitHub-Konto.
4. Wähle **New → Blueprint** und das Repository mit `render.yaml` aus (alternativ: **New → Web Service**, Build Command `npm install`, Start Command `npm start`).
5. Warte, bis der Dienst erfolgreich veröffentlicht wurde. Render zeigt dir dann eine öffentliche `https://...onrender.com`-Adresse.
6. Öffne diese HTTPS-Adresse auf deinem Handy und sende sie deinen Freunden. Eine Person erstellt einen Raum und teilt den Raumcode; die anderen öffnen dieselbe Adresse und treten bei.

Hinweise:
- Render unterstützt WebSocket-Verbindungen. Im kostenlosen Tarif kann der Dienst bei Inaktivität einschlafen und beim nächsten Aufruf wieder starten.
- Spielräume werden nur im Arbeitsspeicher gehalten. Nach einem Serverneustart gehen aktive Räume verloren.
- Es gibt noch keine Accounts, Chatfunktion oder Wiederbeitritt in ein laufendes Spiel.
- Für eine installierbare Web-App: Öffne die HTTPS-Seite auf dem Handy. Auf iPhone: Teilen → Zum Home-Bildschirm. Auf Android/Chrome: Menü → App installieren bzw. Zum Startbildschirm hinzufügen. Die Anzeige hängt vom Browser ab.
- PWA-Dateien erlauben das Installieren der Oberfläche; zum gemeinsamen Online-Spielen muss die Internetverbindung aktiv bleiben.

## Enthalten
- Express + Socket.IO Server
- Responsive mobile UI
- Web-App-Manifest, Icon und Service Worker
- Render Blueprint und Health-Check-Endpunkt
- Räume für 2–5 Spieler, Karten, Lichtressource, Dungeonpfad und Spielchronik

## Noch Prototyp
Regeln und Karteneffekte sind vereinfacht und sollten vor einer größeren Veröffentlichung weiter getestet und ausbalanciert werden. Die Kartenbilder sind derzeit CSS-Stil und Symbole, noch keine vollständigen individuellen Illustrationen.

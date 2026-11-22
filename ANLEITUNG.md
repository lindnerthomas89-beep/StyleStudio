# Style Studio – so kommt die App aufs Handy

Es gibt drei Wege. Fang mit Weg 1 an, der ist am einfachsten.

## Weg 1: Als App über eine Webseite (am einfachsten, kein Programmieren)

Der Ordner `web` ist eine fertige App-Webseite. Sie läuft danach auch ohne Internet.

1. Lege dir ein kostenloses Konto bei GitHub an (github.com) und erstelle dort ein neues Repository, z. B. `style-studio`. Es muss "Public" sein.
2. Lade den Inhalt des Ordners `web` hoch (Button "Add file" > "Upload files"): index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png.
3. Gehe auf "Settings" > "Pages". Wähle bei "Branch" den Eintrag `main` und speichere.
4. Nach etwa einer Minute steht dort dein Link, zum Beispiel `https://DEINNAME.github.io/style-studio/`.
5. Öffne den Link auf dem Handy in Chrome. Tippe auf die drei Punkte > "App installieren" (oder "Zum Startbildschirm hinzufügen").

Fertig: Die App hat ein eigenes Icon, startet im Vollbild und funktioniert offline.
Der Foto-Knopf lädt das Bild herunter bzw. öffnet das Teilen-Menü.

Statt GitHub geht auch jeder andere kostenlose Webspace (z. B. Netlify Drop, Cloudflare Pages).

## Weg 2: Echte APK-Datei bauen lassen (ohne Android Studio)

1. Lege wie oben ein GitHub-Repository an, diesmal mit dem GANZEN Inhalt dieses Ordners (außer `node_modules`, falls vorhanden).
2. Gehe im Repository auf "Actions". Der Ablauf "APK bauen" startet von selbst (oder über "Run workflow").
3. Nach ca. 5 bis 10 Minuten klickst du auf den fertigen Lauf und lädst unten bei "Artifacts" die Datei `StyleStudio-APK` herunter. Darin liegt `app-debug.apk`.
4. Kopiere die APK aufs Handy und tippe sie an. Android fragt, ob Installationen aus dieser Quelle erlaubt sind. Erlaube es einmalig.

Der Foto-Knopf speichert hier das Bild direkt in der Galerie im Album "Style-Studio".
Die App braucht Android 10 oder neuer.

## Weg 3: APK selbst bauen mit Android Studio

1. Installiere Node.js (nodejs.org) und Android Studio (developer.android.com/studio).
2. Öffne ein Terminal in diesem Ordner und führe aus: `npm install` und danach `npx cap sync android`.
3. Starte Android Studio, wähle "Open" und öffne den Unterordner `android`. Warte, bis die Synchronisierung fertig ist.
4. Menü "Build" > "Build Bundle(s) / APK(s)" > "Build APK(s)".
5. Die Datei liegt danach in `android/app/build/outputs/apk/debug/app-debug.apk`.

## Wenn du die App später änderst

Die Webseite der App liegt in `www/index.html` (für die APK) und `web/index.html` (für Weg 1).
Nach Änderungen bei der APK: `npx cap sync android` und neu bauen.

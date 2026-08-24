# DateiCleaner

Ein kleines Browser-Tool, das unerwünschte Textmuster (z. B. `Spotisaver`, `[Downloaded]`, `(HD)`) aus Dateinamen entfernt und die bereinigten Dateien als ZIP zum Download anbietet. Läuft komplett lokal im Browser – es werden keine Dateien hochgeladen oder irgendwohin gesendet.

## Nutzung

1. **01 — Zu entfernende Muster**: Text eingeben und mit „+ Hinzufügen" oder Enter als Muster speichern. Mehrere Muster möglich, per „×" wieder entfernbar. Über den Toggle lässt sich Groß-/Kleinschreibung berücksichtigen.
2. **02 — Dateien hochladen**: Dateien per Drag & Drop, Dateiauswahl oder Ordnerauswahl hinzufügen.
3. **03 — Vorschau & Ergebnis**: Zeigt alte und neue Dateinamen nebeneinander, plus Statistik (gesamt / umbenannt / unverändert). Einzelne Dateien lassen sich über „×" wieder entfernen.
4. Mit „⬇ Als ZIP herunterladen" werden alle Dateien mit bereinigten Namen in eine ZIP-Datei gepackt und heruntergeladen.

## Funktionsweise (Kurzfassung)

- Für jedes Pattern wird ein Regex gebaut (Sonderzeichen werden escaped) und im Dateinamen ersetzt.
- Danach werden doppelte Leerzeichen, führende/trailing Trenner (`-`, `_`, `.`, Leerzeichen) sowie leere Klammern `()`/`[]` aufgeräumt.
- Bleibt nach der Bereinigung nichts Sinnvolles übrig, wird der Originalname beibehalten.

## Technische Hinweise

- Reines HTML/CSS/JavaScript, keine Build-Tools nötig.
- Nutzt [JSZip](https://stuk.github.io/jszip/) (via CDN) zum Erstellen der ZIP-Datei im Browser.
- Alle Daten bleiben lokal im Browser (`ArrayBuffer`-Verarbeitung, kein Netzwerk-Upload).

## Bekannte Einschränkung

Dieses README sowie das CSS des Tools wurden vollständig mit KI generiert.

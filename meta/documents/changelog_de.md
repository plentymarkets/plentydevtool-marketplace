## 1.1.0
### Neu
* **Das Framework wurde auf die neuste Version aktualisiert.**
* **Endbenutzer-Lizenzbestimmungen hinzugefügt.**
* **Tastenkombinationen hinzugefügt.** Die Tastenkombinationen lauten wie folgt:
    - Pull: CMD+P (macOS) oder CTRL+P (Windows & Linux)
    - Push: CMD+U (macOS) oder CTRL+U (Windows & Linux)
    - Neue lokale Plugins erkennen: CMD+D (macOS) oder CTRL+D (Windows & Linux)

### Geändert
* Die Tab-Taste wurde deaktiviert.

### Behoben
* Die App muss nach dem Hochladen eines Plugins nicht mehr geschlossen und neu gestartet werden.
## 0.4.1

### Behoben

* **Unterstützung für Dateisysteme, die Groß- und Kleinschreibung nicht beachten:** Auf Dateisystemen, die Groß- und Kleinschreibung nicht beachten, wurden Dateien direkt nach dem Pullen gelöscht, wenn nur die Groß- und Kleinschreibung geändert wurde. Dieses Verhalten wurde behoben.

## 0.4.0

### Neu
* **Verbesserte Benutzeroberfläche:** Die Bedienbarkeit der Benutzeroberfläche wird nicht mehr durch das Synchronisieren von Dateien eingeschränkt.
* **Deutsche Benutzeroberfläche:** Die Benutzeroberfläche wurde ins Deutsche übersetzt.

### Behoben

* **Schließen von Erfolgsnachrichten:** Erfolgsnachrichten können jetzt wie vorgesehen geschlossen werden.
* **Neue Plugins ohne ServiceProvider:** Neue Plugins werden auch erkannt, wenn in der Plugin-JSON kein ServiceProvider angegeben ist. ServiceProvider sind optional.
* **Zertifikat für Windows aktualisiert:** Benutzer erhalten bei der Erstnutzung auf Windows keine Warnmeldung mehr.

## 0.3.1

### Behoben

* **Ausnahmefehler bei falsch formatierten Plugin-ZIP-Dateien:** Es kann vorkommen, dass ein Plugin nicht als ZIP-Datei heruntergeladen werden kann. Diese Fälle werden nun besser abgefangen, indem die Dateien des Plugins als Fallback einzeln heruntergeladen werden.
* **Unveränderte Dateien „verändert“ (MacOS):** Auf MacOS wird bei schreibgeschützten Dateien der Zeitstempel der letzten Änderung geändert. Aus diesem Grund wird auf MacOS nun eine zusätzliche Prüfung durchgeführt, damit Dateien nicht mehr fälschlicherweise als „verändert“ angezeigt werden.
* **Mehrfachsynchronisierung (MacOS):** Wenn das App-Fenster auf MacOS geschlossen und wieder geöffnet wird, ohne die App komplett zu schließen, wird die Synchronisierungslogik nicht mehr mehrfach ausgeführt.
* **Kein Pushen während des Bereitstellens:** Während das bearbeitete Plugin-Set im plentymarkets System bereitgestellt wird, werden Dateien nicht mehr gepusht.

## 0.3.0

### Neu

* **Detailansicht von Prozessen:** Unter der Fortschrittsanzeige wird die Datei angezeigt, die verarbeitet wird. Dadurch wird der Prozess transparenter.
* **Fortsetzung von Downloads:**Wenn ein Download unterbrochen wird, werden die bereits heruntergeladenen Daten nicht mehr gelöscht und beim nächsten Pull erneut heruntergeladen.

### Behoben

* **Änderung einer Datei sowohl remote als auch lokal:** Wenn eine Datei lokal gelöscht wurde, wird nicht mehr versucht, die Datei umzubenennen, wenn sie auch remote bearbeitet wurde.
* **Fehler beim Entpacken von ZIP-Dateien:** Wenn ein Plugin, das als ZIP-Datei heruntergeladen wurde nicht entpackt werden kann, werden die Dateien des Plugins nun einzeln heruntergeladen.
* **Fortschrittsanzeige beim Anmelden:** Wenn versucht wird, sich mit abgelaufenen Zugangsdaten anzumelden, wird auf dem Anmeldebildschirm keine Fortschrittsanzeige mehr angezeigt.

## 0.2.0

### Neu

* **Protokoll:** Es wird nun eine Protokolldatei geschrieben.
* **Verbotene Zeichen in Dateipfaden:** Wenn eine Dateipfad verbotene Zeichen enthält, wird die Datei nicht mehr gepusht. Stattdessen wird eine Liste mit den verbotenen Zeichen angezeigt.

### Behoben

* **Installation neuer Plugins:** Pluginverzeichnisse müssen denselben Namen wie das Plugin haben. Ein Bug in der Prüfung des Namens wurde behoben.

## 0.1.0

### Neu

* **Automatisches Aktualisieren:** Ab sofort erhältst du eine Meldung, sobald eine neue Version von plentyDevTool zu Verfügung steht. Du kannst direkt auf die neue Version aktualisieren.
* **Tastenkombinationen:** Du kannst jetzt folgende Tastenkombinationen nutzen: Schneiden (X), Kopieren (C), Einfügen (V), Alles markieren (A), Aktion rückgängig machen (Z) und Programm beenden (Q). Dank der Tastenkombination CMD+Q müssen Benutzer die App auf MacOS nicht mehr über die Taskleiste schließen.
* **Tooltips:** Zu den Schaltflächen oberhalb der Plugin-Set-Liste wurden Tooltips hinzugefügt.

### Behoben

* **Hohe CPU-Auslastung auf Windows und Linux:** Der Watcher wurde verlangsamt, damit die Last reduziert wird. Es kann jetzt bis zu 3 Sekunden dauern bis eine bearbeitete Datei in der Liste der bearbeiteten Dateien angezeigt wird.
* **Bug beim Umbenennen von Dateien auf Windows:** Es gab einen Bug, wenn dieselbe umbenannte Datei sowohl lokal als auch remote bearbeitet wurde. Dieses Problem wurde gelöst.
* **Datei-Watcher-Bug auf Linux:** Es gab Probleme mit dem Datei-Watcher auf Linux-Systemen. Diese Probleme wurden behoben.

## 0.0.1

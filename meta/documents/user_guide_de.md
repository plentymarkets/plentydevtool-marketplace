# plentyDevTool Benutzeranleitung

Mit plentyDevTool kannst du deine Prozesse beim Entwickeln von Plugins optimieren. Es erlaubt dir, Dateien von deinem lokalen System mit deinem plentymarkets System zu synchronisieren.

## Einrichten

1. Melde dich in plentyDevTool mit der PID und den Zugangsdaten deines plentymarkets Systems an.
2. Nach dem ersten Anmelden, öffnet sich automatisch das Menü **Einstellungen**.
3. Wähle einen lokalen Ordner. Dieser Ordner wird zum Synchronisieren von Dateien mit plentyDevTool verwendet.

Das Menü **Einstellungen** öffnet sich auch dann, wenn der gewählte Ordner nicht mehr erkannt wird.

### Ordnerstruktur

Wenn du neue Plugins von deinem System herunterlädst, werden in dem Ordner, den du zum Synchronisieren gewählt hast, automatisch neue Ordner angelegt. Die Ordnerstruktur wird dabei nach folgendem Muster erstellt:

```shell
LokalerSyncOrdner/
    ├── System_PID/
    │   ├── Set_ID/
    │   │   │
    │   │   ├── Plugin_Name/
    │   │   │
    │   │   ├── Plugin_Name/
    │   │   │
    │   │   └── . . .
    │   └── . . .
    └── . . .
```

**Ändere weder diese Struktur noch die Namen der Ordner.** Wenn du diese Angaben änderst, werden Systeme, Plugin-Sets und Plugins lokal nicht mehr von plentyDevTool erkannt.

**Vermeide das Hinzufügen, Löschen und Ändern von Dateien außerhalb der Plugin-Unterordner.**

### Multi-Login

Du kannst dich gleichzeitig auf mehreren plentymarkets Systemen einloggen. Das ist vor allem dann nützlich, wenn du auf mehreren Systemen entwickelst und häufig zwischen den Systemen hin- und herwechseln musst.

Um dich in einem weiteren Systemen einzuloggen, gehe wie folgt vor:

1. Klicke auf das Symbol zum Ausloggen.
2. Klicke auf **System wechseln**. Du wirst zur Login-Ansicht weitergeleitet.
3. Melde dich in einem anderen System mit den entsprechenden Zugangsdaten an.

Du kannst zwischen Systemen wechseln, indem du auf das Konto-Symbol klickst.

## Synchronisierung

Bevor du mit dem Entwickeln loslegst, musst du auswählen, an welchen Plugins du arbeiten möchstest. Öffne im Menü auf der linken Seite das Plugin-Set, das das Plugin enthält, das du synchronisieren möchtest. Nutze dann die Umschaltfläche, um das Plugin auszuwählen. Du kannst so viele Plugins auswählen wie du möchtest.

Öffne das **Dashboard** und **Pull**e die Plugins. Je nachdem wie viele Plugins du so herunterlädst oder aktualisierst, kann der Vorgang einige Sekunden dauern. Wenn du eine Datei herunterlädst, die du auch lokal verändert hast, wird die lokale Datei vor dem Herunterladen umbenannt und als Backup markiert. Dadurch kannst du die remote Version der Datei mit der lokalen abgleichen und notwendige Anpassungen vornehmen. Die umbenannte Datei wird als neue Datei auf dem **Dashboard** angezeigt.

Nachdem du ein Plugin lokal bearbeitet hast, kannst du die Änderungen zurück in dein plentymarkets System **Push**en. Prüfe deine Änderungen auf dem **Dashboard**. Beachte, dass nur Plugins in das System gepusht werden, wenn du sie vorher zum Synchronisieren ausgewählt hast. Wenn du in einem Plugin-Set arbeitest, das mit keinem Mandanten verknüpft ist, kannst du außerdem eine schnellere, abgekürzte Version des Bereitstellungsprozesses auslösen, wenn du Dateien **Push**st. Um den abgekürzten Bereitstellungsprozess einzuschalten, verwende die Umschaltfläche **plentyDrive: Änderungen automatisch bereitstellen** im entsprechenden Plugin-Set im Backend. Diese Einstellung wird für jedes Plugin-Set einzeln getroffen. Du kannst also bei jedem Plugin-Set entscheiden, ob der Bereitstellungsprozess automatisch angestoßen werden soll oder nicht.

### Achtung

Der automatische Bereitstellungsprozess ist ein abgekürzter Prozess. Dabei werden nur die Dateien geprüft, an denen du Änderungen vorgenommen hast, aber nicht welche Auswirkungen die Änderungen auf andere Dateien haben. Das heißt, dass einige Fehler nur im normalen Bereitstellungsprozess angezeigt werden.

## Lokale Plugins hinzufügen

Du kannst nicht nur Plugins bearbeiten, die bereits in deinem plentymarkets System vorhanden sind, sondern auch neue Plugins lokal erstellen und sie dem System hinzufügen. Nachdem du einen neuen Plugin-Ordner in einem deiner Plugin-Set-Ordner erstellt und die benötigten Dateien angelegt hast, klicke auf **Neue lokale Plugins erkennen**, um alle neuen Plugins zu erkennen. Plugins werden nicht erkannt, wenn sich der Name des Stammordners von den Eigenschaften name und namespace in der Plugin-JSON unterscheidet.

Klicke auf **Installieren**, um ein Plugin zur Synchronisierung hinzuzufügen.

## Best Practices

1. Bei plentyDevTool handelt es sich nicht um ein System zur Versionsverwaltung. Nutze es in Verbindung mit [Git](https://git-scm.com/), damit du ältere Versionen deiner Dateien wiederherstellen kannst, falls es zu Problemen kommt.

2. Obwohl beim **Pull**en Backups von lokalen Dateien angelegt werden, werden beim **Push**en keine Backups von Dateien erstellt, die remote vorliegen. Sobald du lokale Dateien auf dein plentymarkets System pushst, werden die entsprechenden Dateien remote also überschrieben. Daher solltest du immer einen **Pull** durchführen bevor du **Push**st.
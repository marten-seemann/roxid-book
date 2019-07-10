# Installation

## ROXID-Helfermodul

ROXID benötigt zur Ausführung das ROXID-Modul. Sie können dieses durch Ausführen des folgenden Befehls installieren:

```bash
composer require seemannit/roxid
```

## zu kopierende Dateien

Im Installationsverzeichnis finden Sie zwei Ordner, die den Quellcode von ROXID für verschiedene PHP-Versionen enthalten. Gehen Sie in den für Ihre Serverkonfiguration zutreffenden Ordner.

Kopieren Sie erst den Inhalt des Ordners `copy_this` auf Ihren Server, dann den Inhalt des Ordners `changed_full`.


## Datenbankeinträge

ROXID benötigt für die Konfigurationsoptionen einige zusätzliche Datenbankeinträge. Gehen Sie in den Admin-Bereich Ihres Shops und führen Sie dort unter `Service → Tools` die Datei `sql/install.sql` aus (über `Durchsuchen` auswählen).

Klicken Sie dann auf `Update starten` und warten Sie, bis alle SQL-Abfragen abgeschlossen wurden.
Klicken Sie danach einmal auf `VIEWS jetzt updaten` auf derselben Seite.

Falls Sie eine OXID EE betreiben, beachten Sie bitte folgenden [Hinweis](ee.md).


## .htaccess-Anpassungen

ROXID generiert für Bilder, die für das jeweilige Endgerät optimiert sind.
Dazu ist es nötig, die `.htaccess` im Hauptverzeichnis Ihres Shops anzupassen.
Ersetzen Sie in dieser Datei (ungefähr Zeile 33) die Zeile:

```apacheconf
RewriteRule (\.jpe?g|\.gif|\.png|\.svg)$ getimg.php
```

durch

```apacheconf
RewriteRule (\.jpe?g|\.gif|\.png|\.svg)$ modules/seemanntit/roxid/getimg.php
```

Es kann sein, dass Sie die Dateiberechtigungen der Datei erst ändern müssen. Setzen Sie diese dafür vor dem Bearbeiten auf *777* und nach dem Bearbeiten zurück auf *444*.


## ROXID aktivieren

ROXID ist nun fertig installiert. Zur Inbetriebnahme aktivieren brauchen Sie es nur noch zu aktivieren:

* Aktivieren Sie das Template unter `Erweiterungen > Themes`.
* Aktivieren Sie das ROXID-Helfermodul unter `Erweiterungen > Module`.

## Hinweis bzgl. mmenu

ROXID benutzt [mmenu](https://mmenujs.com/) für die mobile Navigation auf Smartphones. Sie müssen eine [Lizenz erwerben](https://mmenujs.com/download.html), wenn Sie ROXID gewerblich benutzen. Die genauen Lizenzbedingungen finden Sie auf der Webseite von mmenu.


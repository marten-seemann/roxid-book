# Installation

Es ist zu empfehlen, ROXID zuerst auf einem Testsystem zu installieren, bevor Sie es produktiv in Ihrem Shop benutzen.


## Ihre Lizenz
ROXID benötigt den IonCube Loader. Viele Hoster haben diesen schon standardmäßig vorinstalliert, sollte dies nicht der Fall sein, können Sie ihn [hier herunterladen](http://www.ioncube.com/loaders.php).

Ihre Lizenzdatei `license.txt` sollten Sie bereits per Email erhalten haben. Legen Sie diese Datei ins Hauptverzeichnis des Shops.

## zu kopierende Dateien
Kopieren Sie den Ordner `copy_this_PHP5.X` mit allen Unterordnern direkt in das Hauptverzeichnis Ihres Shops. Wählen Sie dabei bitte den Ordner entsprechend der PHP-Version, die auf Ihrem Server installiert ist, aus. Für alte IonCube-Versionen unter PHP 5.3 kann es evtl. nötig sein, die Installationsdateien aus dem Ordner `copy_this_PHP5.3_old_ioncube` zu verwenden.

## Datenbankeinträge
ROXID benötigt für die Konfigurationsoptionen einige zusätzliche Datenbankeinträge. Gehen Sie in den Admin-Bereich Ihres Shops und führen Sie dort unter `Service → Tools` die Datei `sql/install.sql` aus (über `Durchsuchen` auswählen).

Klicken Sie dann auf `Update starten` und warten Sie, bis alle SQL-Abfragen abgeschlossen wurden.
Klicken Sie danach einmal auf `VIEWS jetzt updaten` auf derselben Seite.

## .htaccess-Anpassungen
ROXID generiert für Bilder, die für das jeweilige Endgerät optimiert sind.
Dazu ist es nötig, die `.htaccess` im Hauptverzeichnis Ihres Shops anzupassen.
Ersetzen Sie in dieser Datei (ungefähr Zeile 46) die Zeile:

```apacheconf
RewriteRule (\.jpe?g|\.gif|\.png)$ getimg.php
```

durch

```apacheconf
RewriteRule (\.jpe?g|\.gif|\.png)$ modules/roxid/utils/roxid_getimg.php
```

Es kann sein, dass Sie die Dateiberechtigungen der Datei erst ändern müssen. Setzen Sie diese dafür vor dem Bearbeiten auf *777* und nach dem Bearbeiten zurück auf *444*.

## ROXID aktivieren
ROXID ist nun fertig installiert. Zur Inbetriebnahme aktivieren brauchen Sie es nur noch zu aktivieren:

* Aktivieren Sie das Template unter `Erweiterungen > Themes`.
* Aktivieren Sie das ROXID-Helfermodul unter `Erweiterungen > Module`.
* Aktivieren Sie, falls gewünscht, den LayerSlider für die Startseite Ihres Shops unter `Erweiterungen > Module`.

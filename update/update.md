# Updates

**ROXID wird einen Hinweis auf der Home-Seite im OXID-Backend anzeigen, sobald ein Update verfügbar ist.**

Es ist zu empfehlen, ein ROXID-Update zuerst auf Ihrem Testsystem durchzuführen, bevor Sie es in Ihren produktiven Shop einspielen. Dies gilt umso mehr, wenn Sie Änderungen an Ihrem ROXID vorgenommen haben.

**Achtung**: Für das [Update auf ROXID v3.0](update_auf_v3.0.md) müssen einige zusätzliche Kleinigkeiten beachtet werden.

**Achtung**: Bitte beachten Sie die Hinweise in [Update auf ROXID v4.0](update_auf_v4.0.md). ROXID 4.0 updatet ROXID für OXID 6 updatet.


## Dateien

Im Installationsverzeichnis finden Sie zwei Ordner, die den Quellcode von ROXID für verschiedene PHP-Versionen enthalten. Gehen Sie in den für Ihre Serverkonfiguration zutreffenden Ordner.

Kopieren Sie den Ordner `copy_this` direkt in das Hauptverzeichnis Ihres Shops.  **Ersetzen** Sie bitte die alten Ordner durch diese neue Version (**nicht** Ordner mergen / zusammenführen).


## Datenbankeinträge

Die neue Version von ROXID benötigt evtl. zusätzliche Datenbankeinträge. Gehen Sie in den Admin-Bereich Ihres Shops und führen Sie dort unter `Service → Tools` die Datei `sql/update-vx-to-vy.sql` aus (über `Durchsuchen` auswählen). Diese Datei enthält alle SQL-Befehle aus, die zum Upgrade von Version v`x` auf v`y` nötig sind.

Wenn Sie in der Vergangenheit ein Upgrade ausgelassen haben, führen Sie bitte alle nötigen SQL-Updates nacheinander durch.

Falls Sie eine OXID EE betreiben, beachten Sie bitte folgenden [Hinweis](../installation/ee.md).


### Beispiel

Sie haben ROXID *v3.0* installiert, und möchten auf ROXID *v3.2* upgraden. Dann müssen Sie, in dieser Reihenfolge, folgende Dateien ausführen: `update-3.0-to-v3.1.sql`, und dann `update-v3.1-to-v3.2`.
Klicken Sie zum Ausführen einer Datei auf `Update starten` und warten Sie, bis alle SQL-Abfragen abgeschlossen wurden.

Zum Schluss bitte einmal `VIEWS jetzt updaten` auf derselben Seite ausführen.


## ROXID aktivieren

ROXID ist nun fertig upgedatet.

Schließen Sie das Update ab, indem Sie

* den `/tmp`-Ordner leeren und
* das ROXID-Helfermodul unter `Erweiterungen → Module` deaktivieren und direkt wieder aktivieren.

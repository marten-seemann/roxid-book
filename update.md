# Updates

**ROXID wird einen Hinweis auf der Home-Seite im OXID-Backend anzeigen, sobald ein Update verfügbar ist.**

Es ist zu empfehlen, ein ROXID-Update zuerst auf Ihrem Testsystem durchzuführen, bevor Sie es in Ihren produktiven Shop einspielen. Dies gilt umso mehr, wenn Sie Änderungen an Ihrem ROXID vorgenommen haben.

**Achtung**: Für das [Update auf ROXID v3.0](./update/Update_auf_v3.0.html) müssen einige zusätzliche Kleinigkeiten beachtet werden.

## Dateien
Kopieren Sie den Ordner `copy_this_PHP5.X` (wählen Sie dabei bitte den Ordner entsprechend der PHP-Version, die auf Ihrem Server installiert ist, aus) `'ohne`' folgende Unterordner

* `application/views/roxid_mod/tpl` und
* `out/roxid_mod/src`

direkt in das Hauptverzeichnis Ihres Shops (Das Hauptverzeichnis ist der Ordner, in dem sich u.a. die Ordner `application/`, `modules/` und `out/` befinden). Stellen Sie sicher, dass diese beiden Ordner wirklich ausgeschlossen sind, andernfalls kann es sein, dass einige Ihrer Änderungen am Kind-Theme überschrieben werden.

**Ersetzen** Sie bitte die alten Ordner durch diese neue Version (**nicht** Ordner mergen / zusammenführen).

## Datenbankeinträge
Die neue Version von ROXID benötigt evtl. zusätzliche Datenbankeinträge. Gehen Sie in den Admin-Bereich Ihres Shops und führen Sie dort unter `Service → Tools` die Datei `sql/update-vx-to-vy.sql` aus (über `Durchsuchen` auswählen). Diese Datei enthält alle SQL-Befehle aus, die zum Upgrade von Version v`x` auf v`y` nötig sind.

Wenn Sie in der Vergangenheit ein Upgrade ausgelassen haben, führen Sie bitte alle nötigen SQL-Updates nacheinander durch .

### Beispiel
Sie haben ROXID v1.8 installiert, und möchten auf ROXID 2.0 upgraden. Dann müssen Sie, in dieser Reihenfolge, folgende Dateien ausführen: `update-v1.8-to-v1.9.sql`, und dann `update-v1.9-to-v2.0`.
Klicken Sie zum Ausführen einer Datei auf `Update starten` und warten Sie, bis alle SQL-Abfragen abgeschlossen wurden.

Zum Schluss bitte einmal `VIEWS jetzt updaten` auf derselben Seite ausführen.

## ROXID aktivieren
ROXID ist nun fertig upgedatet.

Schließen Sie das Update ab, indem Sie:

* `/tmp`-Ordner leeren
* das ROXID-Helfermodul unter `Erweiterungen → Module` deaktivieren und direkt wieder aktivieren.

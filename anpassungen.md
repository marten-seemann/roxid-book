# Anpassungen

Diese Anleitung beschreibt, wie Sie ROXID an Ihre Bedürfnisse anpassen können. **Grundlegende Programmierkenntnisse werden vorausgesetzt.**

Um Ihr Template so update-sicher wie möglich zu halten, sollten Sie dafür das bereits mitgelieferte Child-Theme verwenden. Änderungen, die Sie hier vornehmen, werden beim nächsten ROXID-Update nicht überschrieben.

Aktivieren Sie das Child-Theme unter `Erweiterungen → Themes → ROXID Child-Theme`.


## Anpassung der Template-Dateien

Die Template-Dateien des Child-Themes finden sie unter `application/views/roxid_mod`. Wenn Sie Änderungen an einer Template-Datei durchführen möchten, kopieren Sie die entsprechende Datei aus dem Original-Template (`application/views/roxidx/`) in den oben genannten Ordner und führen Sie alle Änderungen in dieser Datei durch.

**Beispiel**: Sie wollen an der Startseite Ihres Shops etwas ändern. Dann kopieren Sie die Datei `application/views/roxidx/tpl/page/shop/start.tpl` nach `application/views/roxid_mod/tpl/page/shop/start.tpl` und editieren diese Datei.


## Anpassung des CSS-Codes

ROXID verwendet [LESS](http://lesscss.org) zur Erstellung der CSS-Dateien. Dies hat - unter anderem - gegenüber CSS den Vorteil, dass man Variablen definieren kann. So können sich durch die Änderung eines Variablen-Werts in LESS Änderungen an mehreren Stellen der CSS-Datei ergeben.

ROXID kommt mit bereits 10 vordefinierten Farbschemata. Sie können sich einstellen, auf welchem Farbschema Ihre Anpassungen basieren sollen.

Setzen Sie die `@theme`-Variable in den folgenden zwei Dateien auf das von Ihnen gewünschte Farbschema:

* `out/roxid_mod/src/css/bootstrap_own.less`
* `out/roxid_mod/src/css/theme_own.less`

Außerdem müssen Sie ROXID mitteilen, nicht die vordefinierten, sondern Ihre angepassten CSS-Dateien zu verwenden. Wählen Sie dazu die Farbschema-Option `own: selbst angepasstes` in den Theme-Einstellungen (unter `Erweiterung → Themes → ROXID → Einstellungen → diverse ROXID Einstellungen`) aus.


## Kompilieren der LESS-Dateien

Damit Ihre Änderungen im Template angezeigt werden, müssen zwei LESS-Dateien in CSS-Dateien kompiliert werden.


| Quelldatei | kompiliert nach | komprimiert nach |
|---|---|---|
| `src/css/theme_own.less` | `build/css/theme_own.css` | `build/css/theme_own.min.css` |
| `src/css/bootstrap_own.less` | `build/css/bootstrap_own.css` | `build/css/bootstrap_own.min.css` |

Alle Pfadangaben hier sind relativ zum `out/roxid_mod/`-Verzeichnis.

Die komprimierte Datei wird im Produktivmodus des Shops (einstellbar im Backend unter `Stammdaten → Grundeinstellungen → Stamm`) verwendet, andernfalls kommt die unkomprimierte Datei zum Einsatz.

Zur automatisierten Kompilierung haben Sie zwei Möglichkeiten:

* [Verwendung von Grunt](anpassungen/grunt.md) (empfohlen)
* [Verwendung des integrierten LESS-Compilers](anpassungen/asset_compiler.md) (*deprecated*)


## Anpassung des Farbschemas

Das Farbschema können Sie am einfachsten über die [LESS-Variablen von Twitter Bootstrap](http://getbootstrap.com/customize/#less-variables) anpassen. Fügen Sie die Variablen, die Sie überschreiben möchten, einfach der `out/roxid_mod/src/css/bootstrap_own_variables.less` hinzu. Die komplette Liste der Bootstrap-Variablen finden Sie in der Variablen-Datei von Bootstrap (`out/roxidx/src/css/bootstrap/less/variables.less`).

**Beispiel**: Wenn Sie die Farbe der *In den Warenkorb*-Buttons auf rot ändern möchten, müssen Sie folgende Zeile hinzufügen:

```less
@btn-success-bg: #FF0000;
```


## Sonstige CSS-Änderungen

Wollen Sie eigene CSS-Regeln erstellen, sollten Sie diese in der Datei `theme_own_mods.less` hinzufügen. Dort können Sie beliebigen LESS- (bzw. CSS) Code hinzufügen.

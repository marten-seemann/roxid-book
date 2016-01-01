# Update auf v3.0

**Diese Seite ist nur für Sie relevant, wenn Sie von ROXID Version v1.x oder v2.x auf v3.0 oder neuer updaten.**

Für ROXID v3.0 wurden viele frühere Entscheidungen überdacht und einige grundlegende Änderungen durchgeführt. Beim Upgrade von einer früheren ROXID-Version müssen daher ein paar Dateien gelöscht und geändert werden.

## zu löschende Dateien
Die Datei `core/utils/roxid_getimg.php` wird jetzt nicht mehr benötigt. Bitte löschen Sie diese.

## .htaccess-Anpassungen
Ersetzen Sie in der `.htaccess` diese Zeile

    RewriteRule (\.jpe?g|\.gif|\.png)$ core/utils/roxid_getimg.php

durch

    RewriteRule (\.jpe?g|\.gif|\.png)$ modules/roxid/utils/roxid_getimg.php

## umbenannte Farbschemata
In ROXID v3.0 wurden eine Reihe neue Farbschemata hinzugefügt. Die drei bisherigen Farbschemata (`blue`, `orange` und `white`) wurden umbenannt:
* `blue` &rarr; `cerulean`
* `orange` &rarr; `united`
* `white` &rarr; `journal`

Wenn Sie Änderungen mit LESS vorgenommen haben, muss die Variable `@colortheme` wie unter [[Anpassungen#Anpassung_der_CSS-Dateien|Anpassungen]] beschrieben entsprechend geändert werden.

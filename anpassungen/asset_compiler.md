# LESS-Compiler

**Achtung**: Der LESS-Compiler ist *deprecated* seit ROXID Version *v3.2*. Er wird in einem künftigen Update entfernt werden. Der LESS-Compiler funktioniert mit einigen speziellen Server-Konfigurationen nicht richtig. Bitte beachten Sie, dass wir keinerlei Support für Probleme mit dem LESS-Compiler anbieten können.

Der integrierte LESS-Compiler übersetzt Ihre Design-Anpassungen von LESS nach CSS. Zur Benutzung ist keine Installation von zusätzlicher Software nötig, weder auf Ihrem Rechner noch auf dem Server.

**Generell empfehlen wir die [Verwendung von Grunt](grunt.md)**.

Den Link zum LESS-Compiler finden Sie unter `Erweiterungen -> Themes -> ROXID modified` in der Theme-Beschreibung.


## Funktionsweise

Der LESS-Compiler übersetzt die LESS-Dateien in CSS-Code, wie unter [Anpassungen](anpassungen.md) beschrieben. Auf den kompilierten CSS-Code wird dann der Autoprefixer angewendet. Die CSS-Dateien werden dann für den Produktiv-Modus noch komprimiert.

Beim Aufruf des LESS-Compilers werden die LESS-Dateien vom Server in Ihren Browser geladen, vom Browser kompiliert und der Autoprefixer wird angewendet, der resultierende CSS-Code wird dann per AJAX zurück an den Server gesendet. Dort wird dieser komprimiert und abgespeichert.


## Sicherheitshinweise

Aus Sicherheitsgründen müssen Sie das Verzeichnis `out/roxid_mod/asset_compiler/` mit einer `.htaccess` und `.htpasswd` mit einem Passwort schützen. Dies ist nötig, weil ansonsten jeder die CSS-Dateien Ihres Shops überschreiben könnte. Ein Angreifer könnte so Ihren Shop praktisch unbenutzbar machen.

Die Erstellung des Passwort-Schutzes sollte über die Oberfläche Ihres Hosters möglich sein. Bei Problemen damit wenden Sie sich bitte an Ihren Hoster.


Wenn Sie die Sicherheitsprüfung dennoch deaktivieren möchten, fügen Sie in der Datei `modules/roxid/asset_compiler/config.php` folgende Zeile hinzu:

```php
$config['disable_auth_check'] = true;
```

Wir raten dringend davon ab, dies bei einem produktiven Shop zu tun.

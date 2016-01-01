# Grunt

Die Benutzung von **Grunt** ist die empfohlene Methode, um die LESS-Dateien des ROXID Child-Themes nach CSS zu kompilieren.

## Installation

Installieren Sie [Grunt](http://gruntjs.com) auf Ihrem System. Wie das geht, entnehmen Sie bitte einer Installationsanleitung für Ihr Betriebssystem aus dem Internet. Der Rest der Anleitung geht davon aus, dass Sie eine aktuelle Version von `grunt` und `npm` auf Ihrem System installiert haben.


Zur Installation aller benötigten Grunt-Plugins führen Sie einfach den Befehl

    npm install

im Hauptverzeichnis Ihres Shops aus. Grunt ist jetzt einsatzbereit.


## Verwendung

Führen Sie den Befehl

    grunt

im Hauptverzeichnis Ihres Shops aus.

Grunt führt dann folgende Schritte aus:

* Kompilierung Ihrer LESS-Dateien in CSS-Dateien, wie unter [Anpassungen](./anpassungen.md) beschrieben
* [Autoprefixer](https://github.com/postcss/autoprefixer/blob/master/README.md) kümmert sich dabei um die CSS-Browser-Präfixe
* Komprimierung der erstellten CSS-Dateien für den Produktivmodus von OXID
* Generierung diverser Favicon-Formate aus dem Favicon in `out/roxid_mod/src/favicons/favicon.png`


## Entwicklung mit LiveReload

Für die besonders komfortable Entwicklung können Sie die LiveReload-Konfiguration verwenden. Grunt überwacht dann
* Änderungen an den TPL-Dateien des Child-Themes
* Änderungen der LESS-Dateien des Child-Themes

und kompiliert dann automatisch die entsprechenden CSS-Dateien und aktualisiert den geänderten Code im Browser. Führen Sie dazu den Befehl

    grunt watch

im Hauptverzeichnis Ihres Shops aus.

**Achtung**: Aus Performance-Gründen baut diese LiveReload-Konfiguration nicht die komprimierten Dateien, welche im Produktivmodus des Shops zum Einsatz kommen. Zur Erstellung der produktiven CSS-Dateien müssen Sie daher zum Abschluss Ihrer Anpassungen einmal den Befehl `grunt` wie oben beschrieben ausführen.

# Troubleshooting - Die häufigsten Fehler

## Der Shop / das OXID-Backend bleibt komplett weiß

Es handelt sich wahrscheinlich um ein Problem mit der Lizenzdatei `license.txt`. Stellen Sie bitte sicher, dass
* die `license.txt` im Hauptverzeichnis Ihres Shops liegt und
* die Lizenz für genau die Domain (inkl. Subdomain) ausgestellt ist, auf der Sie den Shop betreiben.

Details zu Fehlern mit der Lizenzdatei finden sich meist im PHP Error-Log.


## Der Shop lädt, hat aber überhaupt kein Design

Weiteres Symptom: unter `Erweiterungen → Themes → ROXID` tauchen überhaupt keine Konfigurationsoptionen auf.

Dies ist ein sicheres Zeichen, dass die Datenbankeinträge, in denen ROXID die Konfiguration abspeichert, nicht vorhanden sind. Fügen Sie diese hinzu, wie in der Installationsanleitung beschrieben.


## Es wird nur ein bisschen Text auf weißem Hintergrund angezeigt

Überprüfen Sie, ob das ROXID Helfer-Modul aktiviert ist.


## Es werden keine Artikel- und Kategorie-Bilder angezeigt

Dies deutet auf ein Problem mit der Bildgenerierung hin. Überprüfen Sie, dass Sie die Änderung an der `.htaccess` korrekt durchgeführt haben.

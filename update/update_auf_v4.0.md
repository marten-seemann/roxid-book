# Update auf *v4.0*

ROXID v4.0 ist die erste ROXID-Version, die mit OXID 6.x kompatibel ist.

Für das Update löschen Sie bitte die alten ROXID-Dateien komplett. Dazu müssen Sie folgende Ordner löschen:

* `application/views/roxidx`
* `out/roxid` und `out/roxidx` (falls Sie ROXID Two, ROXID Three oder ROXID Four verwenden)
* `modules/roxid`

Updaten Sie dann die Datenbankeinträge, indem Sie die Datei `update-v3.3-to-v4.0` unter `Service → Tools` im OXID Backend ausführen.

Installieren Sie dann ROXID v4.0 nach der [Installationsanleitung](installation.md). Überspringen Sie dabei den Abschnitt "Datenbankeinträge".
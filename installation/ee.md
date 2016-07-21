# Hinweis für OXID Enterprise Installationen

Wenn Sie eine OXID Enterprise-Edition verwenden, muss nach dem Ausführen der *install.sql* sowie nach dem Ausführen eines Datenbankupdates im Rahmen eines ROXID-Updates folgender Befehl ausgeführt werden:

    UPDATE oxconfig SET OXSHOPID=##SHOPID## WHERE OXMODULE LIKE 'theme:roxid%' AND OXSHOPID=0

wobei `##SHOPID##` durch die ID des Subshops, auf dem Sie ROXID einsetzen, ersetzt werden muss.

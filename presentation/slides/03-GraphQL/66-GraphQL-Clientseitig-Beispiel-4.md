---
title: GraphQL Clientseitig - Beispiel 4
---

GitHubs API unterstütz Paging. Das dient dazu, dass bei Listen nicht alle Daten auf einmal geladen werden müssen, sondern erst wenn sie gebraucht werden (Der User scrollt beispielsweise ans Ende der aktuell geladenen Liste).<br>
Das wird über die `pageInfo` und den `cursor` realisiert. Nach jeder Abfrage wird eine `pageInfo` zurückgegeben, die den `endCursor`, also den Cursor für das Ende der Liste und einen Boolean-Wert `hasNextPage` enthält.<br>
Gibt es laut `hasNextPage` noch eine nächste Seite, kann mithilfe des Cursors eine weitere Abfrage gestartet werden, um die nächste Seite zu Laden. Die API erkennt dann mithilfe des Cursors automatisch die nächsten zu ladenden Elemente.<br><br>
Im Beispiel werden dann noch zusätzlich über `edges` und `node` die Nutzdaten abgefragt. Hier muss mit einem Inline Fragment gearbeitet werden, da die Schnittstelle auch andere Daten als Organizationen ausgeben kann.

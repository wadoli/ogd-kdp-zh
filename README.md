# Offene Behördendaten der Denkmalpflege Kanton Zürich

## Inventar der Denkmalschutzobjekte von überkommunaler Bedeutung

Das Inventar bildet die Grundlage für die Arbeit der [Denkmalpflege](https://zh.ch/denkmalpflege). Es setzt sich zusammen aus der [Objektliste](#objektliste-denkmalschutzobjekte) und den [Inventarblättern](#inventarblätter). Weitere Informationen: https://zh.ch/denkmalinventar

### Objektliste Denkmalschutzobjekte

In der Objektliste sind alle überkommunal, das heisst kantonal oder regional eingestuften Objekte verzeichnet. Zusätzlich vermerkt die Tabelle bereits bestehende Schutzmassnahmen wie eine öffentlich-rechtliche Eigentumsbeschränkung oder eine privatrechtliche Personaldienstbarkeit zugunsten des Kantons Zürich. Soweit vorhanden verweisen die Einträge zu den einzelnen Objekten in der Tabellenspalte "publiziertes PDF" auf ihre relevanten Inventarblätter.

Formate:
* **CSV**: https://odb.zh.ch/odbwiki/mediawiki/files/pdfs/objektliste_mit_PDF-Links.csv (Opendata.swiss-Eintrag: https://opendata.swiss/de/dataset/denkmalschutzobjekte2)
* Verschiedene Dateiformate via [GIS-Browser des Kantons Zürich](https://maps.zh.ch): http://maps.zh.ch/?topic=ArchDenkmalZH&amp;showtab=ogddownload
* **WMS**-Webservice: https://wms.zh.ch/OGDArchDenkmalZH (vgl. https://geolion.zh.ch/geodatenservice/2094, Opendata.swiss-Eintrag: https://opendata.swiss/de/dataset/wms-denkmalschutzobjekte1)
 * **WFS**-Webservice: https://maps.zh.ch/wfs/OGDZHWFS (vgl. https://geolion.zh.ch/geodatenservice/2030, Opendata.swiss-Eintrag: https://opendata.swiss/de/dataset/wfs-denkmalschutzobjekte1)

Die **CSV**-Datei entspricht dem CSV-Format der deutschsprachigen Microsoft Excel-Versionen und lässt sich damit sowie mit Libre- und OpenOffice einfach per Doppelklick öffnen.

Zusätzlich gibt es zur Nutzung und Validierung der **CSV**-Datei in diesem Repository ein [Data Package](datapackage.json), welches den Aufbau und Inhalt der Datei genauer beschreibt und die [Nutzung der Daten in verschiedenen Programmiersprachen](https://frictionlessdata.io/tooling/libraries/#data-package) stark erleichtern kann, vgl. https://frictionlessdata.io/.

Objekte, welche in mehreren politischen Gemeinden gleichzeitig liegen, werden mit einer Zeile pro Gemeinde aufgelistet. Die verschiedenen Zeilen eines Objekts lassen sich über die Objektkennung in der Spalte "ODB-ID" zusammenführen.

#### Eindeutiger Primärschlüssel ODB-ID

Die Objektliste im **CSV**-Form enthält duplizierte Objektzeilen, um genau eine Gemeinde pro Zeile zuzusichern. Für die Weiterverarbeitung ist allerdings eine Datei mit eindeutigen Primärschlüssel-Werten in der Regel besser geeignet. Eine solche Form kann beispielsweise wie folgt unter Zuhilfenahme von [curl](https://github.com/curl/curl), [iconv](https://www.gnu.org/software/libiconv/) und [Miller](https://github.com/johnkerl/miller) erstellt werden:

>```curl -s https://odb.zh.ch/odbwiki/mediawiki/files/pdfs/objektliste_mit_PDF-Links.csv | iconv --from-code windows-1252 | mlr --csv --irs LF --fs semicolon --c2t nest --implode --values --across-records --nested-fs semicolon -f Gemeinde then sort -f Gemeinde,ODB-ID | mlr --t2c --ofs semicolon cat```

### Inventarblätter

Derzeit läuft bei der Denkmalpflege ein Projekt zur Revision des Inventars der Denkmalschutzobjekte von überkommunaler Bedeutung, vgl. https://zh.ch/denkmalinventar. Festgesetzte Inventarblätter der überarbeiteten Regionen werden laufend als PDF-Dateien unter der Lizenz [«Creative Commons Namensnennung 4.0 International» (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.de) im folgenden Verzeichnis veröffentlicht:

https://odb.zh.ch/odbwiki/mediawiki/files/pdfs/

Bisher festgesetzt und im obigen Verzeichnis und im GIS-Browser veröffentlicht sind die Inventarblätter der Planungsregionen:

* Furttal
* Knonaueramt
* Limmattal

Auf welche Objekte in der Objektliste sich ein Inventarblatt bezieht, kann über die Verlinkung des PDFs in der Tabellenspalte "publiziertes PDF"  der [Objektliste](#objektliste-denkmalschutzobjekte) ermittelt werden.

### Kontakt

Vgl. https://geolion.zh.ch/geodatensatz/1343

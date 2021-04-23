# Offene Behördendaten der Denkmalpflege Kanton Zürich

Vgl. die offizielle Beschreibung unter https://ad.zh.ch/ogd/.

## Data Package in diesem Repository

Zur Nutzung und Validierung der Objektliste der Denkmalpflege Kanton Zürich im **CSV**-Format gibt es in diesem Repository ein [Data Package](datapackage.json), welches den Aufbau und Inhalt der Datei genauer beschreibt und die [Nutzung der Daten in verschiedenen Programmiersprachen](https://frictionlessdata.io/tooling/libraries/#data-package) stark erleichtern kann, vgl. https://frictionlessdata.io/. Unter Zuhilfenahme des [Frictionless Framework](https://github.com/frictionlessdata/frictionless-py) können das Data Package und Objektliste im ***CSV***-Format wie folgt validiert werden:

>```frictionless validate https://raw.githubusercontent.com/wadoli/objektliste-kdp/master/datapackage.json```

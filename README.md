

<img align="right" width="250" src="img\1200px-DHBW_Ravensburg.svg.png">
<br>
<br>


# Biblometrische Analyse

## Beschreibung
Mit der Umwandlung zur Hochschule in 2009 hat die DHBW einen kooperativen Forschungsauftrag erhalten. Aufgrund der dezentralen Struktur der DHBW und keiner
systematischen Erfassung von Forschungsaktivitäten gibt es keinen Überblick über die Forschungsleistungen der vergangenen
Jahre.<br>
Ziel dieses Projekts ist die quantitative Messung von Forschungs‐Output der DHBW über die Auswertung von Publikationen und
weiteren Forschungsleistungen. Diese werden aus Internetquellen gewonnen und visuell dargestellt.

## Einstieg

### Abhängigkeiten

* Tableau: Lizenz benötigt
* Jupyter Notebook
* Git

### Installation

* Der Source Code kann von github geklont werden.
```
git init
git clone https://github.com/kmatysova2/dhbw_bibliometrische_analyse.git
```
* Die benötigten Bibliotheken sind in der Datei requirements.txt aufgeführt. Diese können mit pip über den folgenden Befehl installiert werden:
```
pip install -r requirements.txt
```

### Programmausführung

Die Programmausführung ist wegen der langen Laufzeiten in mehrere Schritte unterteilt. Diese sind in der richtigen Reihenfolge auszuführen, wobei der Startpunkt bei einem beliebigen Schritt erfolgen kann.<br>
Die Jupyter Notebooks zum Ausführen der einzelnen Schritte sind dabei im [src](https://github.com/kmatysova2/dhbw_bibliometrische_analyse/tree/main/src) Ordner zu finden.

#### 1. Beschaffung der Mitarbeiter
Die für die bibliometrische Analyse relevanten Mitarbeiter werden über die Liste der Ansprechpersonen von den Websiten der einzelnen Standorte ermittelt. Die relevanten Mitarbeiter werden dabei jeweils für einen Standort und ein Jahr in einer csv-Datei zusammengefasst. Basierend auf diesen csv-Dateien wird eine neue csv-Datei erstellt, die alle Standorte und alle Jahre beinhaltet, damit diese zur grafischen Darstellung verwendet werden kann.
* [Notebook für Mitarbeiter](https://github.com/kmatysova2/dhbw_bibliometrische_analyse/tree/main/src/retrieving_employees.ipynb) komplett ausführen.
#### 2. Beschaffung der Publikationen
Die Beschaffung der Publikationen muss für jeden Standort einzeln ausgeführt werden, jeweils mit einem Tag Abstand. Dies resultiert aus den bereits erwähnten Abwehrmechanismen der Webseiten für die Vermeidung einer DDOS Attacke.
* Notebook für [Google Scholar](https://github.com/kmatysova2/dhbw_bibliometrische_analyse/tree/main/src/retrieving_author_publications_google_scholar.ipynb)
* Notebook für [Researchgate](https://github.com/kmatysova2/dhbw_bibliometrische_analyse/tree/main/src/retrieving_author_publications_research_gate.ipynb)
* Standort im Beginn des Notebooks ändern.
* Notebook komplett auführen.
#### 3. Kombination der Publikationen für einzelne Standorte
Die Publikationen der zwei verschiedenen Quellen werden für jeden Standort wiederum in jeweils einer csv-Datei zusammengefasst. Die Identifikation zweier gleicher Publikationen erfolgt hierbei über den Titel.
* [Notebook für Kombination der Quellen](https://github.com/kmatysova2/dhbw_bibliometrische_analyse/tree/main/src/combine_publication_info.ipynb) komplett ausführen.

#### 4. Kombination aller Publikationen und Jahre
Die Publikationen aller Standorte über alle vorhandenen Jahre werden in einer csv-Datei zusammengefasst, um für die grafische Darstellung verwendet werden zu können. Dies geschieht durch die Hinzunahme der beiden Spalten “YEAR” und “SITE”. Zudem werden in diesem Schritt die Zeitschriftenrankings hinzugefügt.
* [Notebook für Kombination der Standorte](https://github.com/kmatysova2/dhbw_bibliometrische_analyse/tree/main/src/combine_pub_into_one_file.ipynb) komplett ausführen.
#### 5. Nutzung der grafischen Oberfläche
Zur Nutzung der grafischen Oberfläche muss nach der Installation von Tableau und dem Klonen des Source Codes die Tableau-Datei [Bibliometrische Analyse](https://github.com/kmatysova2/dhbw_bibliometrische_analyse/tree/main/Bibliometrische%20Analyse.twb) ausgeführt werden.


## Hilfe

Bei Risiken und Nebenwirkungen fragen Sie ihren Chef oder Informatiker.<br>
Oder sprechen Sie die Autoren [Julian Kaiser](mailto:matysova@stud.dhbw-ravensburg.de) und [Katerina Matysova](mailto:lunde@adobe.com) direkt an.

## Autoren

Mitwirkende an diesem Projekt:
 
[Julian Kaiser](https://github.com/kaiserj)<br>
[Katerina Matysova](https://github.com/kmatysova2)

## Lizenz

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons Lizenzvertrag" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />Dieses Werk ist lizenziert unter einer <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Namensnennung - Weitergabe unter gleichen Bedingungen 4.0 International Lizenz</a>.

## Disclaimer

Diese Software wurde als Teil des Abschlussprojekt für den Bachelor of Science im Studiengang Wirtschaftsinformatik - Data Science an der Dualen Hochschule Baden-Württemberg entwickelt. Die Autoren bieten keine Garantie an Vollständigkeit und Richtigkeit des entstandenen Datensatzes. Die erlangten Daten stammen aus öffentlich zugänglichen Quellen. Sensible persönliche Informationen wurden nicht verwendet.

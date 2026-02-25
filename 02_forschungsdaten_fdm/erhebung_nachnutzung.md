# Exkurs: Erhebung & Nachnutzung

*Da diese Fallstudie sich auf die **Organisation, Aufbereitung und Publikation** von Daten entlang des filmwissenschaftlichen SFB-Teilprojekts der FU konzentriert, werden hier lediglich einige gängige Methoden, Beispiele und Hinweise für die Datenerhebung vorgestellt - es besteht kein Anspruch auf Vollständigkeit.*

## Erhebung von Forschungsdaten

Je nach technischem Erfahrungsniveau stehen unterschiedliche Methoden und Verfahren zur Verfügung, um Forschungsdaten in der Film- und Medienwissenschaft zu erheben oder zu generieren. Im Folgenden werden gängige Methoden vorgestellt.

### Erhebung mit digitalen Annotationstools
⟶ <span style="background-color:#FF7F7F;">**Niveau: Basis**</span> 

Für filmanalytische Untersuchungen eignen sich insbesondere digitale Annotationswerkzeuge wie <a href="https://www.advene.org/" class="external-link" target="_blank">Advene</a>, (zum Beispiel in Verbindung mit dem <a href="https://www.ada.cinepoetics.fu-berlin.de/ada-toolkit/index.html" class="external-link" target="_blank">AdA-Toolkit</a>), <a href="https://archive.mpi.nl/tla/elan" class="external-link" target="_blank">ELAN</a>, <a href="https://www.vian.app/" class="external-link" target="_blank">VIAN</a> oder <a href="https://frametrail.org/" class="external-link" target="_blank"> FrameTrail</a>. 

Das Erstellen von Annotationsdaten erfordert i.d.R. nur begrenztes technisches Vorwissen. Die Handhabung kann auf Grundlage verfügbarer Manuals, Open Educational Resources oder Projektdokumentationen schnell erlernt werden. Die jeweiligen Plattformen bieten oftmals ausführliche Dokumentationen und Tutorials an. 

```{figure} ../assets/02_forschungsdaten_fdm/abb_k02_ada_timeline.png
---
align: center
width: 100%
name: ada-timeline
---
Visualisierung von Annotationsdaten mit der AdA-Timeline
```

```{admonition} Annotationen erstellen mit dem AdA-Toolkit
:class: seealso
 In unserer <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-1/intro.html" class="external-link" target="_blank">QUADRIGA Fallstudie: "Affektrhetorik in Online-Videos zur Klimakrise. Datengestützte Analysen audiovisueller Muster"</a> wird gezeigt, wie mit der für die Filmanalyse entwickelten Analyseontologie AdA (Toolkit) in Advene Annotationsdaten erstellt und visualisiert werden können.
 ```
### Data Dumps, APIs und SPARQL-Abfragen
⟶ <span style="background-color:#FF7F7F;">**Niveau: Fortgeschritten**</span>

Neben eigenen Erhebungen können Forschungsdaten auch über bestehende Datenquellen und Datensammelbanken bzw. Plattformen gewonnen werden.

Hierzu zählen insbesondere:
* Sogenannte **Data Dumps** offener Filmdatenbanken wie <a href="https://www.omdb.org/en/us/content/Help:DataDownload" class="external-link" target="_blank">OMDB</a> oder <a href="https://grouplens.org/datasets/movielens/" class="external-link" target="_blank">Movielens</a>.
```{admonition} Was sind Data Dumps?
:class: hinweis, dropdown
Data Dumps sind große bereitgestellte Datenmengen, die von einem Computersystem, einer Datei oder einem Gerät auf ein anderes übertragen werden.
```
* Technisch versierte Nutzer:innen können **API-Schnittstellen** kommerzieller und nicht-kommerzieller Dienste nutzen –  z.B. <a href="https://developer.imdb.com/non-commercial-datasets/" class="external-link" target="_blank">IMDb Non-Commercial Datasets</a>, <a href="https://developer.themoviedb.org/docs/getting-started" class="external-link" target="_blank">The Movie Database</a>(TMDb –  für nicht-kommerzielle Nutzung) oder die <a href="https://opensubtitles.stoplight.io/docs/opensubtitles-api/e3750fd63a100-getting-started)" class="external-link" target="_blank">OpenSubtitles</a> REST API.
```{admonition} Was sind API-Schnittstellen?
:class: hinweis, dropdown
Eine API (Application Programming Interface) ist eine Programmierschnittstelle zwischen verschiedenen Softwareanwendungen. Sie ermöglicht die automatisierte Kommunikation zwischen Programmen, um Daten oder Funktionen auszutauschen, also eine Form der "Maschine-zu-Maschine"– Kommunikation. Über APIs können Entwickler:innen auf Inhalte, Daten oder Dienste anderer Systeme zugreifen und diese in eigene Anwendungen integrieren.
```
* Ebenso bietet beispielsweise das Portal <a href="https://www.wikidata.org/wiki/Wikidata:Main_Page" class="external-link" target="_blank">Wikidata</a> mittes eines <a href="https://query.wikidata.org/" class="external-link" target="_blank">SPARQL-Endpoints</a> semantische Abfragen an. Anleitungen und Abfragebeispiele sind in den Dokumentationen der Seite zu finden. 

```{figure} ../assets/02_forschungsdaten_fdm/abb_k02_sparql_abfrage.png
---
align: center
width: 100%
name: sparql-abfrage
---
Beispiel einer SPARQL-Abfrage mit dem Schlagwort "climate change"
```
```{admonition} Was ist ein SPARQL-Endpoint?
:class: hinweis, dropdown
SPARQL ist eine "graphenbasierte Abfragesprache", durch die Abfragen von Inhalten aus der webbasierten Beschreibungssprache RDF (Resource Description Framework) aus Datenbanken vorgenommen werden können. Ein SPARQL-Endpoint ist eine URL, über die Benutzer:innen diese Abfragen stellen können. Aus großen Datenmengen, die im RDF-Format vorliegen, können mit SPARQL-Abfragen also gezielt Informationen abgerufen werden.
```
### Erhebung mit Webscrapingverfahren
⟶ <span style="background-color:#FF7F7F;">**Niveau: Expert:in**</span> <br>
**Webscraping für fortgeschrittene Nutzer:innen mit Programmierkenntnissen (Python, R, JavaScript)**

Webscraping ist ein Verfahren der automatisierten Extraktion von Daten aus Webseiten. Scraper - das sind Codeskripte - analysieren die HTML-Struktur einer Website und filtern bestimmte vorgegebene Informationen raus, die dann in einer Tabelle oder Datenbank (`dataframe`) strukturiert gespeichert werden können.
Unter Berücksichtigung rechtlicher Vorgaben und der jeweiligen `robots.txt` kann Webscraping als digitales Verfahren eingesetzt werden, um beispielsweise Filmdaten zu extrahieren, die nicht über Schnittstellen oder offene Data Dumps zugänglich sind.
In jedem Fall sind **Lizenzbedingungen**, **Nutzungsrechte** und **Datenschutz** zu prüfen, insbesondere wenn Daten kommerzieller Anbieter (z. B. IMDb, TMDb) nachgenutzt werden sollen.

```{admonition} Was ist eine "robots.txt"?
:class: hinweis, dropdown
Eine `robots.txt.` ist eine einfache Textdatei in dem Hauptverzeichnis einer Website, in der vorgegeben wird, aus welchen Bereichen der Website Daten extrahiert werden dürfen und aus welchen nicht. Dort wird ebenfalls das Verhalten der Datenextraktion selbst festgelegt - insbesondere in welchen zeitlichen Abständen das Scraping erlaubt ist, um den Server nicht zu überlasten.
```

```{figure} ../assets/02_forschungsdaten_fdm/abb_k02_webscraping.png
---
align: center
width: 60%
name: webscraping-code
---
Illustratives Beispiel eines Webscraping-Skripts
```

```{admonition} Siehe auch:
:class: seealso
Detaillierte Informationen zum Thema Webscraping gibt es in unserer
 <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-2/intro.html" class="external-link" target="_blank">QUADRIGA Fallstudie: "Quantitative Analyse der kommunikativen Barrierearmut des Berliner Senats (2011-2024). Eine Fallstudie"</a>
 ```

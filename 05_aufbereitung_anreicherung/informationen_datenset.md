# Informationen zum Datenset

````{margin}
```{admonition} Siehe auch:
:class: hinweis
Ausführliche Infos zur Projektbeschreibung und den Forschungsinhalten finden sich im Kapitel [Teilprojekt](../02_forschungsdaten_fdm/teilprojektbeschreibung.md) sowie auf der SFB-Projektseite.
````

`````{admonition} Projektdaten und Publikation –  Teilprojekt C05
:class: story

Das filmwissenschaftliche Teilprojekt <a href="https://www.sfb-intervenierende-kuenste.de/teilprojekte/C/C05/index.html" class="external-link" target="_blank">"C05 Intervenierende Weltentwürfe: Audiovisualität des Klimawandels"</a> des <a href="https://www.sfb-intervenierende-kuenste.de/" class="external-link" target="_blank">"Sonderforschungsbereichs 1512 "Intervenierende Künste"</a> der Freien Universität Berlin forscht zur Audiovisualität des Klimawandels. 

````{admonition} Forschungsfrage
:class: keypoint
Die primäre Forschungsfrage des Projektes lautet: <br>
Wie modulieren audiovisuelle Darstellungsweisen in Film, Dokumentation und Social Media Wahrnehmungsszenarien des anthropogenen Klimawandels und wie zirkulieren diese Strategien durch Transfers verschiedener Formate der Bildproduktion zwischen Wissenschaft, Journalismus, Unterhaltung und Aktivismus?
````

Die dabei entstandenen [Forschungsdaten](../02_forschungsdaten_fdm/forschungsdaten.md) wurden für die Publikation aufbereitet und auf Github sowie Zenodo publiziert. Welche Komponenten das Datenset genau enthält und wie es strukturiert ist, soll im Folgenden erläutert werden.
`````
## Das Projektrepository

Das Ergebnis der Datenaufbereitung, Bereinigung sowie Anreicherung ist ein öffentlich zugängliches <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset" class="external-link" target="_blank">Datenset</a> mit dem Titel: *Intervening World Projections: Audiovisuality of Climate Change – Dataset*

`````{margin}
````{admonition} Zitierhinweis
:class: citation-information

> Grotkopp, M., Pfeilschifter, Y., & Demir, D. (2026). Intervening World Projections: Audiovisuality of Climate Change – Dataset (Version 1.0.0) [Data set]. https://github.com/SFB1512-C05-climate-film
`````

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_sfb_repository_github.png
---
align: center
width: 100%
name: sfb repository github
---
Das Projektrepository *Intervening World Projections* auf <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset" class="external-link" target="_blank">Github</a>
```
## Überblick über das Datenset

Das Datenset umfasst vier zentrale Datentypen, wobei aufgrund urheberrechtlicher Bestimmungen lediglich die Sekundärdaten publiziert werden:

`Primärdaten` ➡️ werden **nicht** publiziert: 

* Film- und Videomaterial (`.mp4` und `.mkv`) 

`Sekundärdaten` ➡️ werden publiziert: 

* Annotationsdaten: 78 Annotationspakete in den Formaten `.azp` und `.json`
* Moviebarcodes: 303 Visualisierungen im Format `.png`
* Metadaten: tabellarische Beschreibungen des Korpus in den Formaten `.xlsx`, `.csv`, `.html` und `.json`
Metadatenschema im `.yml` Format

Die Metadaten dienen einerseits der Dokumentation und Beschreibung und andererseits der Strukturierung und Verknüpfung der einzelnen Datensätze. 

### Struktur und Zusammenhang der Daten

Die Annotationsdaten bilden das analytische Fundament des Korpus und erfassen expressive Bewegungs- und Gestaltungsmuster (Stichpunkt: Modulation von Wahrnehmungsszenarien durch audiovisuelle Gestaltungsweisen wie Bewegung, Kamera, Montage, Farbe, Licht usw.). Diese werden **angereichert** mit Moviebarcodes, durch die filmische Farb- und Helligkeitsdramaturgien und -veläufe über die gesamte Filmdauer sichtbar und analytisch greifbar werden. 

Die **Metadaten** sind das zentrale Verbindungselement zwischen den Datentypen. Zum einen ermöglichen sie die Identifikation der einzelnen Filme und sammeln zusätzliche Informationen über sie. Zum anderen erlauben sie eine Zuordnung der Annotationen sowie Visualisierungen und strukturieren die gesamte Organisation des Datensatzes für eine potentielle Nachnutzung. 

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_datensatz_architektur.png
---
align: center
width: 90%
name: datensatz architektur
---
Architektur des Datensatzes
```
## Herkunft und Erhebung der Metadaten

Die Metadaten wurden während des Projektverlaufs manuell erhoben und in einer tabellarischen Struktur dokumentiert. Aufgrund des überschaubaren Korpus konnte eine kuratierte und kontrollierte Erfassung somit auch manuell erfolgen. 

Für größere Korpora und Datensätze und Projekte mit einem gewissen technischen Know How oder der Initiative sich einzuarbeiten, eignen sich alternativ auch automatisierte bzw. semi-automatisierte Verfahren der Extraktion von Metadaten. So etwa über API Keys, also Programmierschnittstellen, die Metadaten, beispielsweise mit einem `Python-Skript` aus externen Datenbanken abrufen und als `dataframe`, also eine strukturierte maschinenlesbare Tabelle, speichern. Der API Key der Seite <a href="https://www.omdbapi.com/apikey.aspx " class="external-link" target="_blank">OMDb</a> ist kostenlos, für andere Filmdatenbanken können Entgelte anfallen. 

```{admonition} Benötigte Kenntnisse
:class: hinweis
Es werden mindestens Python Grundlagen sowie KI-Unterstützung für den Code **oder** vertiefende Kenntnisse in Python sowie API und Datenverarbeitungskenntnisse hierfür benötigt.
```

## Bereitstellung und Nachnutzung

Alle Bestandteile des Datensets werden in offenen und langfristig nutzbaren Format bereitgestellt und durch Metadaten sowie Dokumentationen ergänzt.

```{admonition} Langzeitarchivierung und facheigene Repositorien
:class: important
Neben der Veröffentlichung auf Github sowie Zenodo unter offenen Lizenzen ist für eine gesicherte Langzeitarchivierung die Publikation in hochschuleigenen Repositorien empfohlen. Ebenso ist die Publikation in facheigenen Repositorien wie beispielsweise media/rep/ für eine größere Öffentlichkeitswirksamkeit sinnvoll. Dazu auch mehr im Kapitel [Dateninfrastrukturen](../06_publikation_repositorien/dateninfrastrukturen.md).
```

## DMP

````{margin}
```{admonition} Was ist ein DMP
:class: hinweis
Zum Nachlesen: [Datenmanagementplan](../02_forschungsdaten_fdm/datenmanagementplan.md).
```
````

Die hier überblicksartig skizzierten Informationen zum Datenset sind im Prinzip Kurzfassungen der in einem **DMP** festgehaltenen Inhalte. Auf Basis der <a href="https://www.fu-berlin.de/sites/forschungsdatenmanagement/materialien/handreichungen/dmp/index.html#vorlagen" class="external-link" target="_blank">DMP-Vorlage der FU Berlin</a> sowie des <a href="https://rdmorganiser.github.io/ " class="external-link" target="_blank">RDMO-Standardkatalogs </a> stellen wir exemplarisch einen [Projekt-DMP](../assets/05_aufbereitung_anreicherung/doc_k05_dmp_sfb1512_c05.pdf) zum Download zur Verfügung. Dieser kann als Vorlage für die Erstellung eines eigenen DMPs genutzt werden. 

Die Erstellung eines DMPs ist der erste Schritt, um das Fundament für eine nachhaltige Datenpublikation zu ermöglichen. In den nächsten Kapiteln gehen wir die weiteren Schritte zur systematischen Aufbereitung der Forschungsdaten für die Publikation auf Repositorien durch. Doch zunächst möchten wir eine schnell erlernbare und gut reproduzierte Methode zur Anreicherung von Filmannotationsdaten anhand von Moviebarcodes vorstellen. 







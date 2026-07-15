# Systematische Datenaufbereitung 

`````{admonition} Story
:class: story

Die Annotationsdaten wurden erhoben, die [Moviebarcodes](../05_aufbereitung_anreicherung/moviebarcodes.md) aus den Filmdateien extrahiert. Projektintern lagen bereits Dokumentationen und Filmlisten vor, allerdings uneinheitlich und ohne konkrete Systematik. Für eine Datenpublikation ist allerdings die Systematisierung unerlässlich: Daten müssen strukturiert, nachvollziehbar und interoperabel sein. Der erste Schritt ist also die systematische Aufbereitung des gesamten Korpus. Dafür wurde ein projektspezifischer Metadatenstandard entwickelt.

````{admonition} Leitfrage
:class: keypoint
Wie lassen sich unorganisierte [Forschungsdaten](../02_forschungsdaten_fdm/forschungsdaten_fiwi.md) für eine Nachnutzung systematisieren?
````
````{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_rohdaten_systematisierung.png
---
align: center
width: 100%
name: systematisierung
---
Von den Rohdaten zur Systematisierung (KI-generiert)
````
`````

(projekt-metadatenschema)=
## Das Projekt-Metadatenschema: Beschreibungen und DC/EN-Mapping

````{margin}
```{admonition} Was sind Metadatenstandards?
:class: hinweis
Mehr Informationen zu Metadatenstandards gibt es im Kapitel [Metadaten & Metadatenstandards](../03_metadaten/toc_03.md)
```
````

Das für das SFB-Projekt entwickelte Metadatenschema orientiert sich an den Basiselementen des [DC-Schemas](../03_metadaten/allgemeine_standards.md) und des [EN 15744](../03_metadaten/metadaten_filmwissenschaft.md). Zentrale Identifikationsfelder wie `Titel`, `Identifier`, `Produktionsland`, `Jahr`, `Regie` und `Laufzeit` entsprechen standardnahen Metadatenelementen. Sie dienen einerseits der formalen Einordnung sowie Identifizierbarkeit, andererseits können durch die erfassten Elemente auch weitere Untersuchungen am Korpus ermöglicht werden, wie zum Beispiel Berechnungen von Länderanteilen oder Produktionszeiträumen. 

```{admonition} Wie können die Metadaten genutzt werden?
:class: hinweis
Im Kapitel [Diskriminierungssensible Überprüfung](../05_aufbereitung_anreicherung/diskriminierungssensible_überprüfung.md) führen wir Beispielhaft anhand der Korpusmetadaten punktuell eine Überprüfung mit Fokus auf diskriminierungsensible Aspekte durch.
```

In der Forschungspraxis lässt sich allerdings häufig kein Schema vollständig auf den wissenschaftlichen Kontext übertragen. Dies liegt insbesondere daran, dass Forschungsprojekte eigene Untersuchungsmethoden, Korpusdefinitionen und Analysekateogorien mitbringen, die in den allgemeinen Standards keine Entsprechung finden.

Für das Teilprojekt C05 bedeutet dies konkret: Das Metadatenschema wurde projektspezifisch entwickelt, in weiten Teilen lassen sich die Element jedoch auf das DC/EN-Schema mappen.

Die folgende Tabelle zeigt alle `13 Felder` des Korpusmetadatenschemas mit ihren Entsprechungen in Dublin Core (DC) und EN 15744.
Felder ohne Mapping sind projektspezifische Erweiterungen ohne direkte Entsprechung in einem der beiden Standards.

<style>
.table-clean {
    border-collapse: collapse;
    width: 100%;
    font-size: 15px;
}
.table-clean th {
    text-align: left;
    padding: 8px 6px;
    border-bottom: 1px solid #ccc;
    font-weight: bold;
}
.table-clean td {
    padding: 8px 6px;
    border-bottom: 1px solid #eee;
    vertical-align: top;
}
</style>

<table class="table-clean">
  <tr>
    <th>Feld</th>
    <th>Beschreibung</th>
    <th>Dublin Core</th>
    <th>EN 15744</th>
    <th>Kommentar</th>
  </tr>
  <tr>
    <td><code>title</code></td>
    <td>Originaltitel der audiovisuellen Ressource in Originalsprache</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#title">dc:title</a></td>
    <td>Title</td>
    <td>Standardfeld mit direkter Entsprechung</td>
  </tr>
  <tr>
    <td><code>object_id</code></td>
    <td>Projektspezifischer eindeutiger Identifier (ID) des Objekts (audiovisuelle Ressource)</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#identifier">dc:identifier</a></td>
    <td>Identifier</td>
    <td>Projektspezifischer lokaler Identifier</td>
  </tr>
  <tr>
    <td><code>imdb_id</code></td>
    <td>Externer IMDb-Identifier</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#identifier">dc:identifier</a></td>
    <td>Identifier</td>
    <td>Externe Kennung</td>
  </tr>
  <tr>
    <td><code>classification</code></td>
    <td>Korpusspezifisches strukturelles Format des Objekts (audiovisuelle Ressource)</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#type">dcterms:type</a></td>
    <td>Genre</td>
    <td>Aufteilung folgt nach Werktyp und Filmgattung</td>
  </tr>
  <tr>
    <td><code>country</code></td>
    <td>Land der Produktion nach ISO 3166-1 alpha-2</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#spatial">dcterms:spatial</a></td>
    <td>Country of Reference</td>
    <td>Geographischer Kontext</td>
  </tr>
  <tr>
    <td><code>year</code></td>
    <td>Jahr der Erstveröffentlichung im Produktionsland</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#issued">dcterms:issued</a></td>
    <td>Year of Reference</td>
    <td>Standardfeld</td>
  </tr>
  <tr>
    <td><code>director</code></td>
    <td>Vorname Nachname der regieführenden Person(en); bei mehreren Personen getrennt durch Semikolon</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#creator">dcterms:creator</a></td>
    <td>Credits</td>
    <td>Zentrale Referenzperson; anpassen für inklusive Credit-Praktiken</td>
  </tr>
  <tr>
    <td><code>runtime_min</code></td>
    <td>Laufzeit in Minuten, menschenlesbar</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#extent">dcterms:extent</a></td>
    <td>Original Duration</td>
    <td>Nicht normiert</td>
  </tr>
  <tr>
    <td><code>duration_iso8601</code></td>
    <td>Laufzeit nach ISO 8601 duration format, maschinenlesbar</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#extent">dcterms:extent</a></td>
    <td>Original Duration</td>
    <td>Normiert</td>
  </tr>
  <tr>
    <td><code>season_episode</code></td>
    <td>Staffel- und Episodennummer für serielle Formate</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#isPartOf">dcterms:isPartOf</a></td>
    <td>Series / Serial</td>
    <td>Nach etabliertem Standard: S0XE0X</td>
  </tr>
  <tr>
    <td><code>episode_title</code></td>
    <td>Originaltitel der Serienepisode in Originalsprache</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#title">dc:title</a></td>
    <td>Title</td>
    <td>Standardfeld mit direkter Entsprechung</td>
  </tr>
  <tr>
    <td><code>modes_intervention</code></td>
    <td>Projektspezifische Analysekategorie</td>
    <td>––</td>
    <td>––</td>
    <td>Aus dem Korpus heraus entwickelt</td>
  </tr>
  <tr>
    <td><code>annotation_data</code></td>
    <td>Zugehörige Annotationsdaten</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#relation">dcterms:relation</a></td>
    <td>Relationship</td>
    <td>Abgeleitete oder zugehörige Ressource</td>
  </tr>
  <tr>
    <td><code>moviebarcode</code></td>
    <td>Zugehöriger Moviebarcode</td>
    <td><a target="_blank" href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#relation">dcterms:relation</a></td>
    <td>Relationship</td>
    <td>Abgeleitete oder zugehörige Ressource</td>
  </tr>
</table>

```{admonition} Hinweis zum Mapping
:class: important
Nicht jedes Element lässt sich sauber auf die Standards beziehen. Das Feld `classification` beispielsweise kombiniert Werktyp und Darstellungsmodi (fiktional, dokumentarisch) bzw. Filmgattung und bildet die korpusinternen Aufteilungen ab.
```

Ein beispielhafter Metadatensatz für eine audiovisuelle Ressource im `json`-Format sieht so aus:

```json
{
  "title": "Everything Will Change",
  "object_id": "f029e",
  "imdb_id": "tt13086274",
  "classification": "documentary",
  "country": "DE; NL",
  "year": 2021,
  "director": "Marten Persiel",
  "runtime_min": "93 Min.",
  "duration_iso8601": "PT1H33M",
  "season_episode": "",
  "episode_title": "",
  "modes_intervention": "Post-anthropocentric reperspectivations",
  "annotation_data": true,
  "moviebarcode": true
}
```

```{admonition} Was ist JSON?
:class: hinweis
**JavaScript Object Notation** ist ein kompaktes Dateiformat in einfacher Textform, das den Datenaustausch zwischen verschiedenen Anwendungen ermöglicht. Informationen werden dabei in Form von Schlüssel-Wert-Paaren organisiert und können zu Objekten und Listen zusammengefasst werden. Ausführlichere Informationen zum Nachlesen gibt es {ref}`hier <json-format>`.
```

## Identifier, ISO-Standards und kontrollierte Vokabulare 

### Identifier 

Um die audiovisuellen Ressourcen und die Datensätze dauerhaft referenzierbar zu machen, braucht jedes Objekt (sowohl audiovisuelle Ressourcen als auch die Daten selbst) im Korpus einen stabilen, eindeutigen Identifier. Im Projekt wurden zwei Arten von Identifiern verwendet: ein projektspezifischer und ein externer.

Für den **projektspezifischen Identifier**  wird die Bezeichnung `object_id` verwendet. Die `object_id` folgt einem dreiteiligen Schema: 

<style>
.table-clean {
    border-collapse: collapse;
    width: 100%;
    font-size: 15px;
}

.table-clean th {
    text-align: left;
    padding: 8px 6px;
    border-bottom: 1px solid #ccc;
    font-weight: bold;
}

.table-clean td {
    padding: 8px 6px;
    border-bottom: 1px solid #eee;
    vertical-align: top;
}

.table-clean code {
    background-color: #f5f5f5;
    border: 1px solid #ddd;
    border-radius: 5px;
    padding: 1px 5px;
    font-size: 0.9em;
}
</style>

<table class="table-clean">
  <tr>
    <th>Teil</th>
    <th>Bedeutung</th>
    <th>Beispiel</th>
  </tr>
  <tr>
    <td><strong>Präfix</strong></td>
    <td>Typ des Objekts: <code>f</code> = Film/Dokumentarfilm, <code>e</code> = Episode, <code>v</code> = Video</td>
    <td><code>f</code></td>
  </tr>
  <tr>
    <td><strong>Nummer</strong></td>
    <td>Dreistellige fortlaufende Nummer in Aufnahmereihenfolge</td>
    <td><code>002</code></td>
  </tr>
  <tr>
    <td><strong>Suffix</strong></td>
    <td>Erster Buchstabe oder erste Ziffer des Originaltitels</td>
    <td><code>a</code> (→ <em>Anthropocene</em>)</td>
  </tr>
</table>

<br>

So sieht ein vollständiger Identifier, beispielsweise für den Film *Anthropocene: The Human Epoch* (R: 	Jennifer Baichwal, Edward Burtynsky, Nicholas de Pencier, CAN 2018) aus: `f002a`.

```{admonition} Warum nicht die Variante Titel + Jahr verwenden?
:class: important
Identifier wie `avatar_2009` wirken auf den ersten Blick einfach und sind intuitiv, jedoch nicht sehr robust und fehleranfällig. Denn Filmtitel können Sonderzeichen, Leerzeichen oder Umlaute enthalten, die die Maschinenlesbarkeit verhindern. Ebenso kann es mehrere Titel für einen Film geben, was eine stabile ID beeinträchtigt.
```

```{admonition} Fazit
:class: keypoint
Die Objekt-IDs setzen sich aus einem **Präfix**, einer **fortlaufenden numerischen Kennung** und einem **Suffix** zusammen. Die numerischen Bestandteile wurden im Zuge der sukzessiven Erweiterung des Korpus vergeben und folgen keiner inhaltlichen Logik, sondern  der projektinernen Erfassungsreihenfolge. 
```

Zusätzlich zu dem projektspezifischen Identifier wurde für jeden Film, wo möglich, ein IMDb-Identifer erfasst (z. B. `tt8399690`)- Dieser **externe Identifier** trägt die Bezeichtnung `imdb_id`. Er dient als stabile und öffentlich abrufbare Referenz und existiert unabhängig vom Projekt. So können Zusatzinformationen über die Filme von anderen Forschenden auch über die `imdb_id` eingesehen werden.

Warum wurde IMDb als externe Referenz verwendet und nicht beispielsweise die ISAN? <a href="https://www.isan.org/de" class="external-link" target="_blank">ISAN</a> (International Standard Audiovisual Number, ISO 15706) ist der offizielle ISO-Standard zur Identifikation audiovisueller Werke, vergleichbar mit der ISBN für Bücher. In der Praxis sind ISANs allerdings sehr lückenhaft vergeben und ohne institutionellen Zugang nur schwer einsehbar. IMDb-IDs hingegen sind sehr etabliert und frei zugänglich. Die Datenbank enthält zudem eine umfangreiche Menge an katalogisierten Werken, wodurch das Auffinden von audiovisuellen Ressourcen vereinfacht wird. Alternative größere Filmdatenbanken sind unter anderem <a href="https://www.themoviedb.org/?language=de-DE" class="external-link" target="_blank">The Movie Database (TMDb)</a> sowie <a href="https://www.omdb.org/de/de" class="external-link" target="_blank">The Open Movie Database (OMDb)</a>. Da IMDb eine kommerziell betriebene Datenbank ist, ist bei der Nachnutzung der Daten Vorsicht geboten. Hierzu mehr im Kapitel [Diskriminierungssensible Überprüfung](../05_aufbereitung_anreicherung/diskriminierungssensible_überprüfung.md).


Welche Anforderungen allgemein für die Entwicklung guter Identifer zu beachten sind, haben wir hier in übersichtlicher Form zusammengefasst:

```{admonition} Anforderungen an gute Identifier
:class: Keypoint
* **Eindeutigkeit**: Jedes Datenobjekt und jede Ressource bekommt eine ID, die nur einmal vorkommt
* **Persistenz**: Die ID bleibt dauerhaft, auch wenn sich Titel oder Metadaten ändern
* **Logik und Strukturiertheit**: Die ID muss einer konsistenten Logik entsprechen
* **Maschinenlesbarkeit**: Keine Leerzeichen, Umlaute oder Sonderzeichen, im besten Fall durchgehende Nummern/Buchstaben
* **Referenzierbarkeit**: Die ID sollte in allen Metadatenressourcen als Primärschlüssel dienen
```

### Kontrollierte Vokabulare

Kontrollierte Vokabulare legen fest, welche Werte für ein Feld zulässig sind. Sie werden eingesetzt, um Inkonsistenzen (z.B. durch Tippfehler) oder unterschiedliche Schreibweisen zu verhindern (z.B. "Dokumentarfilm" vs. "Doku"). Dadurch ermöglichen sie eine präzisere Filterung, Suche und maschinelle Auswertung. 

In den Korpusmetadaten wurden für zwei Felder kontrollierte Vokabulare festgelegt:

1. `classification`
2. `modes_intervention`

````{margin}
```{admonition} Inhalte der Unterprojekte
:class: hinweis
Mehr Informationen zum Teilprojekt und den Unterprojekten (UPs)  gibt es im Kapitel [Teilprojekt](../02_forschungsdaten_fdm/teilprojektbeschreibung.md).
```
````

Wie bereits oben beschrieben, bildet das Element bzw. Feld `classification` die Aufteilungen des untersuchten Gesamtkorpus (sowie den Teilkorpora von UP 1, UP 2 und UP 3) ab. Diese Aufteilung folgt nach Werktyp (Episode, Video) und Filmgattung (Spielfilm, Dokumentarfilm). Folgende Werte sind für das Feld zugelassen:

* `feature film`
* `documentary`
* `episode`
* `video`


Das Feld `modes_intervention` (Modi der Intervention) ist eine aus dem Korpus des Projekts heraus entwickelte Analysekategorie, die versucht, die Zirkulation audiovisueller Strategien zu erfassen. Hierfür wurden die audiovisuellen Strategien übergeordneten Mustern und Konfliktlinien zugeordnet, die als **Modi der Intervention** beschrieben werden. 

Es handelt sich um ein kontrolliertes Vokabular mit sieben Werten:

1. `destabilization / restabilization`
2. `escalation / de-escalation`
3. `disruptive scaling`
4. `non-linear temporalities`
5. `post-anthropocentric reperspectivations`
6. `unintended consequences`
7. `collisions`

Das Feld ist optional und wird nur für annotierte Objekte befüllt. 

```{admonition} Definitionen der Modi
:class: hinweis
Zum Nachlesen finden sich ausführliche Definitionen der Modi in der <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset/blob/main/documentation/tables_README.md" class="external-link" target="_blank">Projektdokumentation </a>
auf Github.
```

(iso-standards)=
### ISO-Standards

Für zwei Felder werden sogenannte **ISO-Standards** als kontrollierte Vokabulare eingesetzt. 

```{admonition} Was sind ISO-Standards bzw. Normen?
:class: hinweis
ISO Normen sind weltweit anerkannte, konsensbasierte, schriftlich festgelegte Standards zur Definition für Materialien, Produkte, Dienstleistungen oder Verfahren. Sie werden von der <a href="https://www.iso.org/home.html" class="external-link" target="_blank">International Organization for Standardization</a> herausgebracht und sind nicht bindend, jedoch aber in vielen Kontexten zur Qualitätssteigerung, Sicherung und Effizienz etabliert.
```

Durch die Verwendung von ISO-Standards wird sichergestellt, dass die Daten maschinenlesbar, interoperabel und unabhängig von Sprache, Kultur oder Konvention interpretierbar sind. 

1. `country`: kodiert nach <a href="https://www.iso.org/iso-3166-country-codes.html" class="external-link" target="_blank">ISO 3166-1 alpha-2</a>, dem internationalen Standard für Ländercodes. Statt "Deutschland", “Germany”, "GER" oder "DEU" wird einheitlich "DE" verwendet. 
2. `duration_iso8601`: kodiert nach <a href="https://www.iso.org/iso-8601-date-and-time-format.html" class="external-link" target="_blank">ISO 8601</a>, dem internationalen Standard für Datums- und Zeitangaben. Laufzeiten werden im Format `PT[Stunden]H[Minuten]M` angegeben, z.B. `PT1H32M` für 92 Minuten. Das Feld ergänzt `runtime_min` (`92. Min.`), welches für die menschliche Lesbarkeit im Arbeitskontext beibehalten wird. **Maschinenlesbar und interoperabel ist jedoch nur die ISO-kodierte Variante.**

Beide Beispiele zeigen, wie kontrolliertes Vokabular durch externe Normen eingesetzt werden kann. Die Wertliste wird also folglich nicht selbst definiert, sondern von einem etablierten Standard übernommen.

```{admonition} Wo sind kontrollierte Vokabulare zu finden?
:class: seealso
Je nach Disziplin und Anwendungsfall gibt es unterschiedliche Quellen:

* <a href="https://www.iso.org/iso-3166-country-codes.html" class="external-link" target="_blank">ISO 3166-1</a> für Ländercodes
* <a href="https://www.iso.org/iso-639-language-codes.html" class="external-link" target="_blank">ISO 639</a> für Sprachcodes
* <a href="https://www.dublincore.org/specifications/dublin-core/dcmi-terms/" class="external-link" target="_blank">DCMI Metadata Terms</a> für heterogene Metadatenelemente
* <a href="https://www.getty.edu/research/tools/vocabularies/aat/" class="external-link" target="_blank">Getty Art & Architecture Thesaurus (AAT)</a> für Kunst- und Kulturbegriffe
* <a href="https://www.dnb.de/gnd" class="external-link" target="_blank">GND (Gemeinsame Normdatei)</a> der Deutschen Nationalbibliothek für Personen, Orte, Sachbegriffe

**Für filmwissenschaftliche Begriffe:**

* <a href="https://www.fiafnet.org/pages/e-resources/glossary.html" class="external-link" target="_blank">FIAF Glossary of Filmographic Terms</a> für Filmterminologien 
* <a href="https://pbcore.org/elements" class="external-link" target="_blank">PBCore </a> für audiovisuelle Ressourcen und Inhalte
```

## Relationale Verknüpfung des Datensets

Neben den Korpusmetadaten, die das Kernelement der Referenzierbarkeit und Dokumentation des Datensatzes bilden, gibt es noch zwei weitere Metadaten-Files:
1. `annotation_medadata` für die <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset/tree/main/data/annotations" class="external-link" target="_blank">Annotationsdatensätze</a>
2. `moviebarcode_metadata` für die <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset/tree/main/data/moviebarcodes" class="external-link" target="_blank">Moviebarcodes</a>

Wie in den [Informationen zum Datenset](../05_aufbereitung_anreicherung/informationen_datenset.md) ausgeführt, handelt es sich hier um ein relationales Prinzip der Datenverknüpfung. Hauptverknüpfungselement ist dabei der projektinterne Identifier, die `object_id`. Jedes `azp` File sowie jede `png` hat einen einzigen, eindeutigen Identifier, der sich aus der `object_id` ableitet und somit den einzelnen audiovisuellen Ressourcen zugeordnet werden kann. In den Metadaten finden sich zudem zusätzliche Informationen, wie beispielsweise das Datum der Erstellung oder technische Komponenten. 

Alle hier beschriebenen Metadaten-Dateien stehen auf <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset/tree/main/data/metadata" class="external-link" target="_blank">Github </a> in den Exportformaten (`xlsx`, `csv`, `html`, `json`) zur Verfügung. Einzelheiten zu den einzelnen Formaten gibt es im nächsten Kapitel.

(metadatenschema-template)=
## Das Metadatenschema als Template

Das im Rahmen des Projekts entwickelte Metadatenschema steht als downloadbares [Template](../assets/05_aufbereitung_anreicherung/doc_k05_corpus_metadata_schema_climate_film_c05.yml) im sogenannten `yaml`-Format zur Verfügung. Das Template dient als nachnutzbare Vorlage für die strukturierte Beschreibung von filmographischen Metadatensätzen und definiert die relevanten Metadatenelemente in einem maschinenlesbaren Format. Somit kann es als Ausgangspunkt für eigene Metadatenschemata aber auch zur Dokumentation, Validierung oder zur automatisierten Weiterverarbeitung in andere Formate genutzt werden. Selbstverständlich kann die Vorlage an die Bedürfnisse des eigenen Forschungskontexts angepasst werden. Im Abschnitt {ref}`Metadatenvalidierung <metadaten-validierung>` wird gezeigt, wie die Metadaten anhand des `yaml`-Schemas validiert werden.

````{admonition} Was ist eine YAML-Datei und wie kann sie genutzt werden?
:class: hinweis
`yaml` (YAML Ain't Markup Language) ist ein menschenlesbares Datenformat zur strukturierten Speicherung von Informationen. Es ist besonders kompakt und gut lesbar, da es auf Einrückungen statt auf Klammern oder Tags setzt. Im Kontext von Forschungsdaten werden `yaml`-Dateien häufig für die Dokumentation von Metadatenschemata genutzt, da Felder, Datentypen aber auch Regeln für eine Nachnutzung beschrieben werden können.

Zum Öffnen und Bearbeiten der `yaml`-Datei kann ein kostenloser Code-Editor genutzt werden. In dieser OER nutzen wir für alle Beispiele <a href="https://code.visualstudio.com/" class="external-link" target="_blank">Visual Studio Code (VS Code)</a> von Microsoft, da die Software kostenfrei verfügbar und auch für Einsteiger:innen leicht zugänglich ist. Alternativ können ebenso andere, auch nicht kommerziell betriebene Text- oder Code-Editoren verwendet werden.
````
`````{dropdown} YAML im Detail erklärt
Eine `yaml` besteht aus drei Grundbausteinen. 

**1. Schlüssel-Wert-Paare (Mappings)** 

Sie sind das häufigste Element und können mit einem Formularfeld verglichen werden:

```yaml
title: "Anthropocene"
year: "2018"
```

**2. Listen (Sequenzen)**

Hier stehen mehrere Werte unter einem Schlüssel, eingeleitet mit einem Bindestrich `-`:


```yaml
vocabulary:
  - documentary
  - feature film
  - episode
```

**3. Mehrzeilige Texte**

Mit `>` (Zeilenumbrüche werden zu Leerzeichen) oder `|` (Zeilenumbrüche bleiben erhalten):

```yaml
description: >
  Ein langer Text der über
  mehrere Zeilen geht.
```

`````

Die `yaml`-Datei ist maschinenlesbar und dokumentiert alle Felder mit Typ, Pflichtangaben, DC/EN-Mapping, Validierungsregeln (Pattern/Muster), kontrollierten Vokabularen und Beschreibungen. Die Pattern folgen einer bestimmten Logik und basieren auf sogenannten "regulären Ausdrücken" (*Regular Expressions*, kurz: Regex). Sie regeln, in welchem Format ein Wert vorliegen soll, beispielsweise für `year`:

```text
"^[0-9]{4}$"

^ = Anfang des Wertes
$ = Ende des Wertes
[0-9] = Ziffer von 0 bis 9
+ = beliebig oft
{4} = genau viermal
```

Werden eigene, abweichende Felder verwendet, deren Werte ebenfalls einem bestimmten Muster folgen, kann mit Unterstützung von KI eine passende Regex-Regel erstellt werden. Hierfür genügt es, die gewünschte Pattern-Logik im Prompt zu beschreiben. Die KI kann diese Anforderungen anschließend in einen Regex-Ausdruck übersetzen.

(yaml-schema)=
### Das YAML-SCHEMA 

```yaml
schema:
  name: corpus_metadata_schema_climate_film_c05
  version: "1.0.0"
  fields:
    - name: title
      type: string
      required: true
      dc-mapping: "dc:title"
      en15744-mapping: "Title"
      description: "Original title of the audiovisual resource in its original language"
      example: "Anthropocene: The Human Epoch"

    - name: object_id
      type: string
      required: true
      dc-mapping: "dc:identifier"
      en15744-mapping: "Identifier"
      pattern: "^[fev][0-9]{3}[a-z0-9]$"
      description: >
        Project-specific unique identifier (ID) for the object (audiovisual resource);
        Composed of three parts: a classification prefix (f = feature film or documentary,
        e = episode, v = video), a three-digit sequential number, and a suffix
        consisting of the first letter or digit of the original title
      example: "f002a"
      notes: Can be adjusted for project purposes

    - name: imdb_id
      type: string
      required: true
      dc-mapping: "dc:identifier"
      en15744-mapping: "Identifier"
      description: "External IMDb identifier"
      note: Other standards for external identifiers such as ISAN can also be used
      example: "tt8399690"

    - name: classification
      type: string
      required: true
      dc-mapping: "dcterms:type"
      en15744-mapping: "Genre"
      vocabulary:
        - feature film
        - documentary
        - episode
        - video
      description: "Corpus-specific structural format of the object (audiovisual resource)"
      example: "documentary"
      notes: > 
        Can be adjusted for project purposes. No exact correspondence to EN 15744 or DC;
        this field combines work type and genre as a corpus-specific simplification
    
    - name: country
      type: string
      required: true
      dc-mapping: "dcterms:spatial"
      en15744-mapping: "Country of Reference"
      standard: ISO 3166-1 alpha-2
      separator: "; "
      description: "Country/countries of origin"
      example: "CA"
      note: >
        No exact correspondence to DC
    
    - name: year
      type: string
      required: true
      dc-mapping: "dcterms:issued"
      en15744-mapping: "Year of Reference"
      pattern: "^[0-9]{4}$" # Four digits 
      description: "Year of initial release in the country of origin"
      example: "2018"

    - name: director
      type: string
      required: true
      dc-mapping: "dcterms:creator"
      en15744-mapping: "Credits"
      separator: "; "
      description: "First and last name of the director(s); multiple directors are separated with semicolon"
      example: "Jennifer Baichwal; Edward Burtynsky; Nicholas de Pencier"
      notes: Can be adjusted for more inclusive credit practices

    - name: runtime_min
      type: string
      required: false
      dc-mapping: "dcterms:extent"
      en15744-mapping: "Original Duration"
      pattern: "^[0-9]+ Min\\.$"
      description: "Runtime in minutes, human-readable"
      example: "87 Min."
    
    - name: duration_iso8601
      type: string
      required: true
      dc-mapping: "dcterms:extent"
      en15744-mapping: "Original Duration"
      standard: ISO 8601 duration
      pattern: "^PT([0-9]+H)?([0-9]+M)?$"
      description: "Runtime following ISO 8601 duration format, machine-readable"
      example: "PT1H27M"
    
    - name: season_episode
      type: string
      required: false
      dc_mapping: "dcterms:isPartOf"
      en15744_mapping: "Series / Serial"
      pattern: "^S[0-9]{2}E[0-9]{2}$"
      description: >
        Season and episode number for serial formats.
        Only relevant if classification = "episode"
      example: "S01E04"
      notes: >
        Follows the widely used de-facto convention. 
        No official ISO standard exists for this format

    - name: episode_title
      type: string
      required: false
      dc-mapping: "dc:title"
      en15744-mapping: "Title"
      description: "Original title of the series episode in its original language"
      example: "To the Ends of the Earth"
      notes: Only relevant if classification = "episode"
    
    - name: modes_intervention
      type: string
      required: false
      vocabulary:
      - Destabilization / Restabilization
      - Escalation / de-escalation
      - Disruptive scaling
      - Non-linear temporalities
      - Post-anthropocentric reperspectivations
      - Unintended Consequences
      - Collisions
      description: "Project-specific analysis categories"
```

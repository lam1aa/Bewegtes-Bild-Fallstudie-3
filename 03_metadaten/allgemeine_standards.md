# Allgemeine Metadatenstandards

```{image} ../assets/03_metadaten/abb_k03_metadatenstandard.png
---
align: center
width: 80%
name: metadatenstandard
---
```

````{margin}
```{admonition} Markup-Sprachen/XML
:class: hinweis
Mehr Infos zum Thema `XML` gibt es im {ref}`vorigem Kapitel <markup-sprachen>`.
```
````
<br>

Das System der Strukturierung von Metadaten wird als **Metadatenstandard** bezeichnet. Metadatenstandards sind also Klassifizierungssysteme. Häufig liegen diese Standards in `XML` vor und geben bereits eine Struktur vor, wobei der Einsatz von kontrolliertem Vokabular bei der Standardisierung der Inhalte hilft (z.B. <a href="https://www.getty.edu/research/tools/vocabularies/" class="external-link" target="_blank">Getty Thesaurus</a>).

> "Dies reicht von kontrollierten Wortlisten, die fehlerhafte oder unterschiedliche Schreibweisen von Konzepten vereinheitlichen, über Taxonomien und Thesauri, die Über- und Unterbegriffe wie auch Synonyme zu Konzepten enthalten, bis hin zu Ontologien, die Eigenschaften und Relationen zwischen Konzepten modellieren."

```{admonition} Was sind Taxonomien und Ontologien?
:class: hinweis, dropdown
Taxonomien sind Benennungssysteme, bestehend aus kontrolliertem Vokabular, um Dinge und Objekte zu bezeichnen. Ontologien sind Wissensmodelle, die Informationen als relationale Strukturen organisieren und Konzepte systematisieren.
```
Es gibt eine Vielzahl von fächerübergreifenden, generischen Metadatenstandards. Zwei der bekanntesten stellen wir kurz vor. 

## Dublin Core

Ein weit verbreiteter, generischer Standard zur Beschreibung von Dokumenten und anderen Objekten ist der sogenannte <a href="https://www.dublincore.org/" class="external-link" target="_blank">Dublin Core</a>. Er besteht aus einem Set aus 15 allgemeinen, weit verbreiteten <a href="https://www.dublincore.org/specifications/dublin-core/usageguide/elements/" class="external-link" target="_blank">Elementen </a> (siehe auch <a href="https://www.ietf.org/rfc/rfc2413.txt" class="external-link" target="_blank">hier</a>), darunter beispielsweise `title`, `creator`, `subject` oder `description`, und wird vielseitig für verschiedenste Ressourcen eingesetzt  – von digitalen Objekten in Repositorien über Webseiten bis hin zu Bibliotheksbeständen.

```{figure} ../assets/03_metadaten/abb_k03_dublin_core.png
---
align: center
width: 75%
name: dublin-core
---
Dublin Core und die 15 Elemente 
```
### Die 15 Elemente des DC und ihre Beschreibungen
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
    <th>Element</th>
    <th>Beschreibung</th>
  </tr>
  <tr>
    <td><strong>dc:title</strong></td>
    <td>Titel der Ressource (Name, Bezeichnung)</td>
  </tr>
  <tr>
    <td><strong>dc:creator</strong></td>
    <td>Person oder Organisation, die die Ressource geschaffen hat</td>
  </tr>
  <tr>
    <td><strong>dc:subject</strong></td>
    <td>Themen, Schlagworte oder Klassifikationen</td>
  </tr>
  <tr>
    <td><strong>dc:description</strong></td>
    <td>Beschreibung, Zusammenfassung oder Abstract der Ressource</td>
  </tr>
  <tr>
    <td><strong>dc:publisher</strong></td>
    <td>Herausgebende Institution, die die Ressource veröffentlicht</td>
  </tr>
  <tr>
    <td><strong>dc:contributor</strong></td>
    <td>Weitere Personen oder Organisationen, die zur Ressource beigetragen haben</td>
  </tr>
  <tr>
    <td><strong>dc:date</strong></td>
    <td>Relevantes Datum (z.&nbsp;B. Erstellung, Veröffentlichung)</td>
  </tr>
  <tr>
    <td><strong>dc:type</strong></td>
    <td>Art bzw. Typ der Ressource (z.B. Text, Bild, Dataset)</td>
  </tr>
  <tr>
    <td><strong>dc:format</strong></td>
    <td>Format/Medium der Ressource (z.B. PDF, PNG, audio/mpeg, txt/xml)</td>
  </tr>
  <tr>
    <td><strong>dc:identifier</strong></td>
    <td>Eindeutige Kennung/Identifikator der Ressource (z.B. DOI, URN, ISBN, URL)</td>
  </tr>
  <tr>
    <td><strong>dc:source</strong></td>
    <td>Ursprungsquelle, aus der die Ressource hervorgeht oder abgeleitet ist</td>
  </tr>
  <tr>
    <td><strong>dc:language</strong></td>
    <td>Sprache der Ressource (z.B. ISO-639-Code)</td>
  </tr>
  <tr>
    <td><strong>dc:relation</strong></td>
    <td>Beziehungen zu anderen Ressourcen (z.B. Teil-von, Version, Referenz)</td>
  </tr>
  <tr>
    <td><strong>dc:coverage</strong></td>
    <td>Räumliche oder zeitliche Abdeckung (Ort, Region, Zeitraum)</td>
  </tr>
  <tr>
    <td><strong>dc:rights</strong></td>
    <td>Rechte, Lizenzen und Nutzungsbedingungen der Ressource</td>
  </tr>
</table>

### Vor- und Nachteile des DC-Metadatenschemas

✅ **Vorteile**
* Weit verbreitet und international genutzt
* Disziplinübergreifend
* Einfacher Einstieg und geringe Komplexität
* Interoperabel

❌ **Nachteile**
* Eher ungeeignet für komplexere Forschungs- oder Fachdaten 
* Keine spezifische Struktur für für Versionierung oder Zitation von Forschungsdaten
* Uneinheitliche Nutzungsmöglichkeiten

## DataCite 

Das <a href="https://schema.datacite.org/" class="external-link" target="_blank">DataCite</a> Schema ist eine strukturierte Liste bestehend aus Kern-Metadaten und ihren Eigenschaften. Es wird insbesondere für die bibliographische Beschreibung von Forschungsdaten, für Publikation, Zitation sowie die Registrierung von DOIs genutzt. Bestimmte Elemente, wie z.B. `Autor`oder `Titel`, sind verpflichtende Bestandteile, andere Elemente, wie z.B. `Fachbereich` oder `Beschreibung`, werden empfohlen oder sind optional. Das Metadatenschema sowie praxisnahe <a href="https://schema.datacite.org/meta/kernel-4.6/" class="external-link" target="_blank">Anwendungsbeispiele </a> werden in `XML` und `JSON` zur Verfügung gestellt. 
Ein DataCite <a href="https://dhvlab.gwi.uni-muenchen.de/datacite-generator/" class="external-link" target="_blank">Metadatengenerator </a> (aktuell für die Schema Version 4.6.) der Ludwig-Maximilians-Universität München generiert durch Eingabe der Metadatenfelder automatisch ein DataCite-`XML` Schema. Dieses kann heruntergeladen und in einem Repositorium der Wahl den Forschungsdaten beigefügt werden. Mehr Informationen zur Anwendung gibt es auf der 
<a href="https://github.com/UB-LMU/datacite-metadata-generator" class="external-link" target="_blank">Github-Page</a>.

```{figure} ../assets/03_metadaten/abb_k03_data_cite.png
---
align: center
width: 85%
name: data-cite
---
Elemente des DataCite Schemas - *notwendig* (links) & *empfohlen* (rechts)
```
### Vor- und Nachteile des DataCite-Metadatenschemas

✅ **Vorteile**
* Enge Verknüpfung mit DOIs
* Zitierbare Referenzierung von Daten in Publikationen
* International etablierter Standard in Forschungsdateninfrastrukturen
* Interoperabel

❌ **Nachteile**
* Komplexer und voraussetzungsreich
* Weniger geeignet als universeller Minimalstandard
* Fokus liegt auf Zitation und Publikation, weniger auf inhaltliche Beschreibungen

Beide Metadatenstandards sind auch in den Digital Humanities etabliert und bieten einen guten Einstieg. Welcher am Ende für das eigene Projekt genutzt werden soll, hängt von verschiedenen Variablen der jeweiligen Datensätze ab. Für eigene Projekte ist es daher ratsam, sich frühzeitig über geeignete Metadatenschemata zu informieren. Der folgende Fragenkatalog soll dabei helfen, eine passende Auswahl zu treffen.

## Praxisnaher Fragenkatalog für die Auswahl des Metadatenschemas

<div style="
  border: 1px solid #E5E5E5;
  padding: 1.4rem 1.6rem;
  margin: 2rem 0;
  border-radius: 6px;
">

<details style="margin-bottom:1rem;">
  <summary style="font-weight:600; cursor:pointer;">
    1. Umfang und Komplexität der Daten
  </summary>
  <ul style="margin-top:0.6rem;">
    <li>Handelt es sich um komplexe oder überschaubare Daten?</li>
    <li>Gibt es verschiedene Datentypen (z.B. Texte, Audio, Video, Bilder usw.) oder ist der Datenbestand homogen?</li>
  </ul>
</details>

<details style="margin-bottom:1rem;">
  <summary style="font-weight:600; cursor:pointer;">
    2. Inhaltliche Aspekte
  </summary>
  <ul style="margin-top:0.6rem;">
    <li>Welche Bestandteile der Datensätze sollen in den Metadatendokumentationen beschrieben werden (z. B. Inhalt, Struktur, Entstehungskontext, Methoden, Rechte)?</li>
    <li>Werden grundlegende bibliographische Angaben benötigt oder fachspezifische?</li>
  </ul>
</details>

<details style="margin-bottom:1rem;">
  <summary style="font-weight:600; cursor:pointer;">
    3. Publikation und Zitation
  </summary>
  <ul style="margin-top:0.6rem;">
    <li>Soll das Schema insbesondere für die Publikation und Zitation genutzt werden (DOIs)?</li>
    <li>Sollen die Forschungsdaten langfristig referenzierbar sein?</li>
  </ul>
</details>

<details style="margin-bottom:1rem;">
  <summary style="font-weight:600; cursor:pointer;">
    4. Ressourcen und Kompetenzniveau
  </summary>
  <ul style="margin-top:0.6rem;">
    <li>Welche zeitlichen und technischen Ressourcen bzw. Kapazitäten gibt es im Projekt, um sich ggf. auch in komplexere Schemata einzuarbeiten?</li>
    <li>Stehen Personen mit Vorwissen zu Metadatenstandards oder technischen Formaten (z. B. XML, TEI, RDF) zur Verfügung?</li>
  </ul>
</details>

<details>
  <summary style="font-weight:600; cursor:pointer;">
    5. Minimalstandard oder mehr?
  </summary>
  <ul style="margin-top:0.6rem;">
    <li>Reicht für den Zweck des Projektes ein Minimalstandard (z. B. wenige, generische Felder), oder sind detaillierte, fachlich spezialisierte Metadaten erforderlich?</li>
  </ul>
</details>

</div>

Allgemeine, generische Schemata sind ein guter Einstieg für Projektanfänge. Häufig decken sie jedoch die Erfordernisse des jeweiligen Fachs nicht genügend ab. In der Praxis werden Metadatenschemata daher konfiguriert oder angepasst, um die Fach- bzw. Projektspezifika zu adressieren. Daran anknüpfend rückt im nächsten Kapitel die Filmwissenschaft in den Fokus, um fachspezifische Metadatenstandards exemplarisch zu vertiefen.
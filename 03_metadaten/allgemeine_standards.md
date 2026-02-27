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



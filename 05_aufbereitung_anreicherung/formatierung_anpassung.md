# Formate, Konvertierung, Dokumentation

## Dateiformate

Werden Forschungsdaten in Repositorien veröffentlicht, so ist es wichtig, Dateiformate zu wählen, die einen langfristigen Zugang sichern und die Nachnutzbarkeit bzw. Wiederverwendung durch Dritte ermöglichen. Grundsätzlich empfiehlt es sich nach den 
{ref}`FAIR-Prinzipien<leitlinien-fair>` **offene** und  **nicht-proprietäre Formate** zu wählen, darunter zählen beispielsweise Formate wie `csv` oder `json`, hierzu gleich mehr. Doch was bedeutet offen und nicht-proprietär genau?

Nicht-proprietäre Formate sind Formate, die sich ohne den "dazugehörigen Anwendungs-, Hilfs- oder Systemprogrammen öffnen, bearbeiten und speichern lassen."  Das bedeutet, dass keine spezifische, ggf. kostenpflichtige Software zur Verarbeitung und Weiterverwendung der Daten notwendig ist. Dies ist eine Grundvoraussetzung dafür, dass Daten langfristig nutzbar sind und bleiben – unabhängig davon, ob eine bestimmte Software, Programme oder Tools in 10 oder 20 Jahren noch verfügbar sind. Für die Speicherung in nicht-proprietäre Formate ist es notwendig, die Daten zu exporten bzw. zu konvertieren. 

```{admonition} Datenverlust bedenken
:class: danger
<a href="https://forschungsdaten.info/fdm-allgemein/veroeffentlichen-und-archivieren/dateiformate" class="external-link" target="_blank">forschungsdaten.info</a> empfiehlt, möglichst beide Formate, also das Original sowie die konvertierte Version, parallel zu veröffentlichen, da es bei der Konvertierung ggf. zu Datenverlust kommen kann.
```

Neben der Notwendigkeit der Langzeitsicherung spielen auch andere Prinzipien dabei eine wichtige Rolle: **Maschinenlesbarkeit** und **Interoperabilität**. Maschinenlesbare Formate ermöglichen es, die Daten automatisiert zu verarbeiten, zu filtern und in andere Systeme zu importieren. Interoperabilität heißt, dass Daten mit unterschiedlichen Tools und in unterschiedlichen Kontexten genutzt werden können, ohne an ein bestimmtes System gebunden zu sein.

Im Rahmen des Projekt-Repositoriums stellen wir die Korpus,- Annotations- und Moviebarcodemetadaten in den Formaten `xlsx`, `csv`, `html` und `json` zur Verfügung.

```{admonition} An Formatkonvertierung aller Forschungsdaten denken!
:class: important
Neben den Metadaten, werden die Annotationspakete ebenfalls als `json`-Export bereitgestellt, die Moviebarcodes sind bereits als `png` Dateien ein offenes Format. Alle gängigen Annotationstools verfügen über Exportfunktionen, mehr Informationen können in den jeweiligen begleitenden Dokumentationen oder Manuals der verwendeten Tools nachgelesen werden.
```
Im Folgenden werden die (Export-)Formate kurz vorgestellt.

### XLSX (Microsoft Excel Open XML)

`xlsx` ist das native Dateiformat für Tabellenkalkulationen von Microsoft Excel. Im Projektkontext dient es als **primäres Arbeitsformat**. Die Masterdatei der Korpusmetadaten wird in Excel gepflegt, da das Format mehrere Tabellenblätter, Kommentarfunktionen, bedingte Formatierungen, Listen uvm. ermöglicht. Diese Funktionen sind im Laufe von kontinuierlichen Arbeitsprozessen sehr hilfreich. 
`xlsx` wird jedoch nicht als primäres Publikationsformat verwendet, da es ein proprietäres Format ist. Wie von forschungsdaten.info empfohlen, wird es jedoch parallel mit publiziert.

### CSV (Comma-Separated Values)

`csv` ist ein einfaches, textbasiertes Format für tabellarische Daten. Gespeichert werden die Werte üblicherweise durch ein Komma `,` als Trennzeichen. Es ist das am weitesten verbreitete offene Formate für strukturierte Daten und kann von nahezu jeder Software gelesen werden (Texteditor, Python, R).
`csv` eignet sich gut für den Datenaustausch und maschinelle Verwertbarkeit, hat aber auch einige Nachteile. Es unterstützt beispielsweise keine komplexeren oder verschachtelten Datenstrukturen.

Ein generischer Beispieldatensatz eines CSV-Eintrags kann so aussehen: 

```text
title;year;country;director;genre
The Lighthouse;2019;US;Robert Eggers;Drama
Portrait of a Lady on Fire;2019;FR;Céline Sciamma;Romance
Spirited Away;2001;JP;Hayao Miyazaki;Animation
Parasite;2019;KR;Bong Joon-ho;Thriller
The Zone of Interest;2023;GB;Jonathan Glazer;Drama
```
Wie hier zu erkennen ist, werden die Feldtrennzeichen durch ein Semikolon `;` getrennt. **Warum ist das so?** Im deutschsprachigen Raum entspricht das Semikolon als Trennzeichen den verbreiteten Standardkonventionen von Tabellenkalkulationsprogrammen wie Microsoft Excel, da das Komma üblicherweise als Dezimaltrennzeichen genutzt wird. International ist jedoch das Komma das etablierte Trennzeichen. Beide Varianten sind möglich und erfordern etwaiige Abwegungen von Vor- und Nachteilen. 

(json-format)=
### JSON (JavaScript Object Notation)

json ist ein einfaches und kompaktes Format für strukturierte Daten, das ebenfalls in einer lesbaren Textform vorliegt und den Datenaustausch zwischen verschiedenen Anwendungen (z.B. Webanwendungen, APIs) ermöglicht. Informationen werden dabei in Form von Schlüssel-Wert-Paaren organisiert und können zu Objekten und Listen zusammengefasst werden. Im Gegensatz zu CSV kann JSON hierarchische und verschachtelte Strukturen abbilden. 

Der generische Beispieldatensatz (gekürzt) als `json`-Eintrag sieht dann so aus:

```json
[
  {
    "title": "The Lighthouse",
    "year": 2019,
    "country": "US",
    "director": "Robert Eggers",
    "genre": "Drama"
  },
  {
    "title": "Portrait of a Lady on Fire",
    "year": 2019,
    "country": "FR",
    "director": "Céline Sciamma",
    "genre": "Romance"
  }
]
```

`````{dropdown} JSON im Detail erklärt

Die Grundstruktur eines `json`-Dokuments besteht aus:

**1. Objekten**

```json
{
  "title": "Anthropocene: The Human Epoch",
  "year": 2018,
  "director": "Jennifer Baichwal"
}
```

Links steht der Schlüssel (*key*), rechts der zugehörige Wert (*value*).

**2. Listen (Arrays)**

Mehrere Objekte können in einer Liste zusammengefasst werden:

```json
[
  {
    "title": "Anthropocene: The Human Epoch",
    "year": 2018
  },
  {
    "title": "Before the Flood",
    "year": 2016
  }
]
```

Die eckigen Klammern markieren Listenanfang und -ende. Eine Liste kann mehrere Objekte enthalten. Dies entspricht mehreren Zeilen einer Tabelle.

`json` kennt nur wenige grundlegende Datentypen, die in vielen Programmiersprachen ebenfalls zum Einsatz kommen (z. B. Python):

* String (Text): `"title": "Anthropocene"`
* Number (Zahl): `"year": 2018`
* Boolean: `true`, `false`
* Null: `"episode": null`
* Object:`{ ... }`
* Array: `[ ... ]`

`````

Im Projekt wird `json` als ein alternatives Publikationsformat zur Verfügung gestellt, da es eine direkte Einbindung in digitale Anwendungen ermöglicht und somit das Nachnutzungspotenzial stärkt.

### HTML (HyperText Markup Language)

Als viertes Format wird ein interaktives, durchsuchbares `html`-Dokument bereitgestellt. Dies erlaubt Nutzenden, die Metadaten direkt im Browser zu durchsuchen und zu filtern – ohne zusätzliche Software- oder Programmierkenntnisse. Die `html`-Variante richtet sich also vornehmlich an Nutzende, die unkomplizierte Recherchen am Datensatz vornehmen wollen. 

Was ist `html`? `html` ist eine Auszeichnungssprache (Markup-Language) zur Strukturierung und Darstellung von Inhalten im Web. Anders als `csv` oder `json` dient `html` nicht primär dem Datenaustausch, sondern der Beschreibung von Inhalten wie Texte mit Hyperlinks, Bildern, Überschriften, Absätzen usw. 
`html` basiert auf sogenannten Tags, die den Inhalt eines Dokuments (semantisch) gliedern. Jedes Element besteht aus einem öffnenden Tag, dem Inhalt und einem schließenden Tag:

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_html_tags_elemente.png
---
align: center
width: 75%
name: html elemente
---
Anatomie eines HTML-Elements, © Mozilla Contributors <a href="https://developer.mozilla.org/de/docs/Learn_web_development/Core/Structuring_content/Basic_HTML_syntax" class="external-link" target="_blank">MDN Web Docs</a>, CC BY-SA 
```

`````{dropdown} HTML im Detail erklärt

Das Grundgerüst eines `html`-Dokuments besteht aus ineinander verschachtelten Elementen. Diese Elemente markieren, welche Funktion ein Inhalt innerhalb der Webseite hat.

**1. Grundgerüst eines HTML-Dokuments**

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>

  </body>
</html>
```

Der Kopfbereich (`<head>`) ist unsichtbar und enthält Metainformationen über die Webseite. Der Bodybereich (`<body>`) ist der sichtbare Teil, dieser definiert den Aufbau einer Website. 

**2. Wichtige `hmtl`-Elemente**

`html` verwendet Tags, um Inhalte zu markieren. Die häufigsten Elemente sind:

* Überschriften: `<h1>` bis `<h6>`
* Absätze: `<p>`
* Links: `<a>`
* Bilder: `<img>`
* Listen: `<ul>`, `<ol>`, `<li>`
* Tabellen: `<table>`, `<tr>`, `<th>`, `<td>`
* Container/Bereiche: `<div>`, `<section>`

**3. Tabellen für strukturierte Daten**

Für tabellarische Metadaten können `html`-Tabellen verwendet werden:

```html
<table>
  <tr>
    <th>title</th>
    <th>year</th>
    <th>director</th>
  </tr>
  <tr>
    <td>The Lighthouse</td>
    <td>2019</td>
    <td>Robert Eggers</td>
  </tr>
</table>
```

Dabei steht `<table>` für die Tabelle, `<tr>` für eine Tabellenzeile, `<th>` für eine Kopfzelle und `<td>` für eine Datenzelle.

`````
```{admonition} Weiterführende Informationen
:class: seealso
* <a href="https://developer.mozilla.org/de/docs/Learn_web_development/Core/Structuring_content/Basic_HTML_syntax" class="external-link" target="_blank">MDN Web Docs</a>
* <a href="https://wiki.selfhtml.org/wiki/HTML/Tutorials/Grundger%C3%BCst" class="external-link" target="_blank">SELFHTML</a>
* <a href="https://www.theodinproject.com/lessons/foundations-introduction-to-html-and-css" class="external-link" target="_blank">The Odin Project</a>
```

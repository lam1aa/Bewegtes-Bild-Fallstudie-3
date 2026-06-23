# Versionierung, Lizenzierung, Zitierfähigkeit 

`````{admonition} Story
:class: story

```{figure} ../assets/06_publikation_repositorien/abb_k06_semver_license_pid.png
---
align: center
width: 80%
name: semver-license-pid
---
Versionieren, lizenzieren, zitieren (KI-generiert)
```

Die [systematische Aufbereitung der Daten](../05_aufbereitung_anreicherung/systematische_aufbereitung.md) ist abgeschlossen und die zu publizierenden Datensätze sowie Metadaten liegen in [offenen Formaten](../05_aufbereitung_anreicherung/formatierung_anpassung.md) vor. Auch die notwendigen {ref}`Dokumentationsdateien  <dokumentation>` (`README.md`, Guides, Tutorials usw.) wurden erstellt, um die Daten zu kontextualisieren und die angewandten Methoden nachvollziehbar zu machen. Doch wie geht es anschließend weiter?

Das filmwissenschaftliche Teilprojekt <a href="https://www.sfb-intervenierende-kuenste.de/teilprojekte/C/C05/index.html" class="external-link" target="_blank">"C05 Intervenierende Weltentwürfe: Audiovisualität des Klimawandels"</a> hat bereits mehrere Publikationswege evaluiert und sich dazu entschieden, das Datenset in einem ersten Veröffentlichungsschritt auf GitHub/Zenodo zu publizieren. Mehr Informationen zu Repositorien können im Kapitel [Publikationswege und -formate](../04_einführung_publikation/publikationswege_formate.md) abgerufen werden.

Bevor die Daten auf GitHub hochgeladen werden, sollten zunächst Fragen der Versionierung, Lizenzvergabe und Zitierfähigkeit berücksichtigt werden. Die folgenden drei Abschnitte erläutern die dafür relevanten Grundlagen praxisnah und exemplarisch.
`````

## Versionierung

Die Versionierung von Forschungsdaten ermöglicht eine eindeutige Referenzierung und Nachvollziehbarkeit bestimmter Veröffentlichungsstände eines Datensatzes. Sie trägt dazu bei, Änderungen transparent zu dokumentieren und unterschiedliche Versionen digitaler Forschungsartefakte voneinander abzugrenzen.

Für die Versionierung existieren unterschiedliche Ansätze. Ein besonders verbreitetes System zur Versionierung ist <a href="https://semver.org/" class="external-link" target="_blank">Semantic Versioning</a>: kurz "SemVer". Ursprünglich in der Softwareentwicklung etabliert, wird es heute auch für Forschungsdaten aller Art angewandt. SemVer dokumentiert kleinteilig alle Versionsnummern und Änderungsverläufe publizierter oder publikationsreifer Software und Daten bzw. Datensätze. 

Neben SemVer werden auch andere Versionierungsschemata verwendet, beispielsweise fortlaufende Versionsnummern (v1, v2...) oder datumsbasierte Versionierungen (siehe: <a href="https://calver.org/)" class="external-link" target="_blank">CalVer</a>). Für GitHub-basierte Workflows hat sich SemVer jedoch als Standard etabliert. Da das vorliegende Projekt die Daten auf GitHub/Zenodo publiziert, soll das Schema hier vorgestellt werden. 

### Wie funktioniert das Schema?

Das Schema folgt dem Prinzip eines dreistelligen Nummernsystems:

1. `MAJOR`, z.B. **2**.0.0 → Es wurden grundlegende bzw. inkompatible Änderungen durchgeführt, bestehende Codes oder andere Programme aus vorigen Versionen funktionieren womöglich nicht mehr

2. `MINOR`: z.B. 2.**1**.0 → Neue Funktionen wurden hinzugefügt, alte Versionen funktionieren aber noch, sie sind also abwärtskompatibel

3. `PATCH`: z.B.  2.1.**1** → Kleine Bugfixes oder Tippfehler, es wird nichts Strukturelles verändert, alles ist weiterhin abwärtskompatibel 


Neben der dreistelligen Versionsnummerierung gibt es zusätzlich noch sogenannte "pre-realease version labels" bzw "pre-release tags". Sie kennzeichnen Entwicklungsstadien vor der offiziellen Veröffentlichung und signalisieren Nutzenden so, dass eine Version noch nicht vollständig oder stabil ist.

Die Zeitleiste einer Version kann beispielsweise so aussehen:

```text
alpha → beta → release candidate → finale Version

0.1.0-alpha.1 → 0.1.0-beta.1 → 1.0.0-rc.1 → 1.0.0
```

* `alpha` steht für die frühe Entwicklungsphase, die Version ist also noch nicht vollständig bzw. in einem Rohbau und anfällig für Fehler - wird eher für interne Testungen genutzt
* `beta` beschreibt eine weitestgehend fertige Entwicklungsstufe, die breiter getestet wird und in denen Fehler weiterhin auftreten können
* `rc` ist die Abkürzung für "release candidate" und markiert einen quasi fertige, publikationsreife Version 
* Die finale Version entspricht dann einem `MAJOR` Release 

```{admonition} Schreibweise pre-release labels
:class: important
Die pre-release labels werden immer mit einem Bindestrich an die Versionsnummer angehängt, wie oben im Beispiel zu sehen ist.
```
Für Forschungsdaten ist die Verwendung von pre-release version labels je nach Projektkontext abzuwägen. Bei abgeschlossenen Projekten mit gesetztem Laufzeitende liegen die Datensätze zur Publikation meist vollständig vor und können auf Version 1.0.0 publiziert werden, da oft keine wesentlichen Änderungen zu erwarten sind. Die Nutzung von pre-release tags ist insbesondere dann sinnvoll, wenn abzusehen ist, dass wesentliche Entwicklungen oder Änderungen eintreten werden. 

## Lizenzierung

Neben der Versionierung, ist weiterer zentraler Schritt der Publikation die Vergabe von Lizenzen. Forschende und Forschungsprojekte sollten sich frühzeitig mit der Frage der Lizenzierung auseinandersetzen, um etwaige lizenzrechtliche Unschlüssigkeiten oder Unsicherheiten bereits im Vorfeld zu klären. Denn Lizenzen legen fest, unter welchen Bedingungen andere Personen die Forschungsdaten **nutzen, bearbeiten oder weitergeben** dürfen.

### Die Creative Commons Lizenzen (CC) im Überblick

Insbesondere für kreative Werke und Texte, aber auch für Forschungsdaten oder Annotationen haben sich die <a href="https://creativecommons.org/" class="external-link" target="_blank">Creative-Commons-Lizenzen </a> als übergreifender, internationaler Standard etabliert. 

#### Was ist CC?
> Creative Commons (CC) ist eine Non-Profit-Organisation, die in Form vorgefertigter Lizenzverträge eine Hilfestellung für Urheber zur Freigabe rechtlich geschützter Inhalte anbietet.

Es werden sechs Standards-Lizenzverträge angeboten, die für die Publikation und Verbreitung kreativer Inhalte oder Ressourcen genutzt werden können, um die rechtlichen Bedingungen zu definieren. Sie bestehen aus kombinierbaren Modulen, die unterschiedliche Nutzungsrechte festlegen.

````{margin}
```{admonition} Siehe auch:
:class: seealso
Detaillierte Beschreibungen zu den Modulen und ihren Eigenschaften gibt es auf <a href="https://forschungsdaten.info/fdm-allgemein/rechte-und-pflichten/forschungsdaten-veroeffentlichen/creative-commons-lizenzen" class="external-link" target="_blank">forschungsdaten.info</a>.
```
````

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
  <thead>
    <tr>
      <th>Modul</th>
      <th>Bedeutung</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>BY</strong> – Namensnennung</td>
      <td>Urheber:in muss genannt werden</td>
    </tr>
    <tr>
      <td><strong>SA</strong> – Share Alike</td>
      <td>Weitergabe nur unter gleicher Lizenz</td>
    </tr>
    <tr>
      <td><strong>NC</strong> – Non-Commercial</td>
      <td>Nur nicht-kommerzielle Nutzung</td>
    </tr>
    <tr>
      <td><strong>ND</strong> – No Derivatives</td>
      <td>Keine Bearbeitungen erlaubt</td>
    </tr>
  </tbody>
</table>

<br>

Daraus ergeben sich sechs Lizenzkombinationen sowie zusätzlich die Lizenz <a href="https://creativecommons.org/publicdomain/zero/1.0/" class="external-link" target="_blank">CC0</a> (= vollständiger Rechteverzicht bzw. Public Domain Dedication):

<a href="https://creativecommons.org/licenses/by/4.0/" class="external-link" target="_blank">CC BY</a> ·
<a href="https://creativecommons.org/licenses/by-sa/4.0/" class="external-link" target="_blank">CC BY-SA</a> ·
<a href="https://creativecommons.org/licenses/by-nd/4.0/" class="external-link" target="_blank">CC BY-ND</a> ·
<a href="https://creativecommons.org/licenses/by-nc/4.0/" class="external-link" target="_blank">CC BY-NC</a> ·
<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/" class="external-link" target="_blank">CC BY-NC-SA</a> ·
<a href="https://creativecommons.org/licenses/by-nc-nd/4.0/" class="external-link" target="_blank">CC BY-NC-ND</a> ·
<a href="https://creativecommons.org/publicdomain/zero/1.0/" class="external-link" target="_blank">CC0</a>

Wer im Sinne der {ref}`FAIR-Prinzipien <leitlinien-fair>` handelt will, sollte für Forschungsdaten die möglichst offene Lizenz <a href="https://creativecommons.org/licenses/by/4.0/" class="external-link" target="_blank">CC BY 4.0</a> wählen, da sie die Nachnutzung und Zitierbarkeit unter Namensnennung sicherstellt.

```{admonition} Keine Lizenzangabe
:class: caution
Ohne explizite Lizenzangabe gilt automatisch das Urheberrecht, das heißt, dass eine Nachnutzung ohne Rückfrage rechtlich nicht erlaubt ist.
```

#### Was ist der Unterschied zwischen 4.0 und 3.0?

Die CC-Versionen 4.0 sind die aktuellen und überarbeiteten Lizenzverträge, welche ausdrücklich empfohlen werden. Ab Version 4.0 decken die CC-Lizenzen ebenfalls Datenbankrechte ab. Insofern sind die Lizenzen auch explizit für Forschungsdaten geeignet. Forschungsdateninfo weist darauf hin, dass bei früheren Versionen die Schutzwirkung fraglich ist.

#### Welche Lizenz passt zu meinen Daten?

Um die Auswahl der Lizenz zu erleichtern, haben Barbara Klute und Jöran Muuß-Merholz für <a href="https://wb-web.de/material/medien/die-cc-lizenzen-im-uberblick-welche-lizenz-fur-welche-zwecke-1.html" class="external-link" target="_blank">wb-web</a> eine Entscheidungsgrafik erstellt:

```{figure} ../assets/06_publikation_repositorien/abb_k06_lizenzwahl.jpg
---
align: center
width: 85%
name: lizenzwahl
---
Grafik von Barbara Klute und Jöran Muuß-Merholz für <a href="https://wb-web.de/material/medien/die-cc-lizenzen-im-uberblick-welche-lizenz-fur-welche-zwecke-1.html" class="external-link" target="_blank">wb-web</a> © CC BY SA 3.0
```

Ebenso kann mit dem <a href="https://creativecommons.org/chooser/" class="external-link" target="_blank">Creative Commons License Chooser</a> eine passende Lizenzempfehlung durch Ausfüllen des Minimalfragebogens ausgegeben werden.

```{figure} ../assets/06_publikation_repositorien/abb_k06_cc_chooser.png
---
align: center
width: 85%
name: cc-license-chooser
---
Fragebogen des CC License Choosers
```

```{admonition} Unwiderruflichkeit von CC-Lizenzen 
:class: caution
Eine einmal vergebene Lizenz kann nicht zurückgezogen werden. Ein Werk kann also auch dann noch weiterhin gemäß den ursprünglichen Lizenzbedingungen genutzt werden, wenn der/die Urheber:in die Lizenz nachträglich ändern möchte. Neue Versionen eines Datensatzes können jedoch unter einer anderen Lizenz veröffentlicht werden. 
Für die Praxis bedeutet dies, dass die Lizenzvergabe **vor** der Publikation sorgfältig zu prüfen ist. Nachträgliche Änderungen (z.B. von CC BY zu CC BY-NC) gelten dann nur für neue Versionen, nicht für bereits veröffentlichte Stände.
```

### Lizenz für Code und Skripte


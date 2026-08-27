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

(versionierung)=
## Versionierung

Die Versionierung von Forschungsdaten ermöglicht eine eindeutige Referenzierung und Nachvollziehbarkeit bestimmter Veröffentlichungsstände eines Datensatzes. Sie trägt dazu bei, Änderungen transparent zu dokumentieren und unterschiedliche Versionen digitaler Forschungsartefakte voneinander abzugrenzen.

Für die Versionierung existieren unterschiedliche Ansätze. Ein besonders verbreitetes System zur Versionierung ist <a href="https://semver.org/" class="external-link" target="_blank">Semantic Versioning</a>: kurz "SemVer". Ursprünglich in der Softwareentwicklung etabliert, wird es heute auch für Forschungsdaten aller Art angewandt. SemVer dokumentiert kleinteilig alle Versionsnummern und Änderungsverläufe publizierter oder publikationsreifer Software und Daten bzw. Datensätze {cite}`PrestonWerner_2013`. 

Neben SemVer werden auch andere Versionierungsschemata verwendet, beispielsweise fortlaufende Versionsnummern (v1, v2...) oder datumsbasierte Versionierungen (siehe: <a href="https://calver.org/)" class="external-link" target="_blank">CalVer</a>). Für GitHub-basierte Workflows hat sich SemVer jedoch als Standard etabliert. Da das vorliegende Projekt die Daten auf GitHub/Zenodo publiziert, soll das Schema hier vorgestellt werden. 

### Wie funktioniert das Schema?

Das Schema folgt dem Prinzip eines dreistelligen Nummernsystems:

1. `MAJOR`, z. B. **2**.0.0 → Es wurden grundlegende bzw. inkompatible Änderungen durchgeführt, bestehende Codes oder andere Programme aus vorigen Versionen funktionieren womöglich nicht mehr

2. `MINOR`: z. B. 2.**1**.0 → Neue Funktionen wurden hinzugefügt, alte Versionen funktionieren aber noch, sie sind also abwärtskompatibel

3. `PATCH`: z. B.  2.1.**1** → Kleine Bugfixes oder Tippfehler, es wird nichts Strukturelles verändert, alles ist weiterhin abwärtskompatibel 


Neben der dreistelligen Versionsnummerierung gibt es zusätzlich noch sogenannte "pre-realease version labels" bzw "pre-release tags". Sie kennzeichnen Entwicklungsstadien vor der offiziellen Veröffentlichung und signalisieren Nutzenden so, dass eine Version noch nicht vollständig oder stabil ist.

Die Zeitleiste einer Version kann beispielsweise so aussehen:

```text
alpha → beta → release candidate → finale Version

0.1.0-alpha.1 → 0.1.0-beta.1 → 1.0.0-rc.1 → 1.0.0
```

* `alpha` steht für die frühe Entwicklungsphase, die Version ist also noch nicht vollständig bzw. in einem Rohbau und anfällig für Fehler - wird eher für interne Testungen genutzt
* `beta` beschreibt eine weitestgehend fertige Entwicklungsstufe, die breiter getestet wird und in denen Fehler weiterhin auftreten können
* `rc` ist die Abkürzung für "release candidate" und markiert eine quasi fertige, publikationsreife Version 
* Die finale Version entspricht dann einem `MAJOR` Release 

```{admonition} Schreibweise pre-release labels
:class: important
Die pre-release labels werden immer mit einem Bindestrich an die Versionsnummer angehängt, wie oben im Beispiel zu sehen ist.
```
Für Forschungsdaten ist die Verwendung von pre-release version labels je nach Projektkontext abzuwägen. Bei abgeschlossenen Projekten mit gesetztem Laufzeitende liegen die Datensätze zur Publikation meist vollständig vor und können auf Version 1.0.0 publiziert werden, da oft keine wesentlichen Änderungen zu erwarten sind. Die Nutzung von pre-release tags ist insbesondere dann sinnvoll, wenn abzusehen ist, dass wesentliche Entwicklungen oder Änderungen eintreten werden. 

(lizenzierung)=
## Lizenzierung

Neben der Versionierung, ist weiterer zentraler Schritt der Publikation die Vergabe von Lizenzen. Forschende und Forschungsprojekte sollten sich frühzeitig mit der Frage der Lizenzierung auseinandersetzen, um etwaige lizenzrechtliche Unschlüssigkeiten oder Unsicherheiten bereits im Vorfeld zu klären. Denn Lizenzen legen fest, unter welchen Bedingungen andere Personen die Forschungsdaten **nutzen, bearbeiten oder weitergeben** dürfen.

### Die Creative Commons Lizenzen (CC) im Überblick

Insbesondere für kreative Werke und Texte, aber auch für Forschungsdaten oder Annotationen haben sich die <a href="https://creativecommons.org/" class="external-link" target="_blank">Creative-Commons-Lizenzen </a> als übergreifender, internationaler Standard etabliert. 

#### Was ist CC?
> "Creative Commons (CC) ist eine Non-Profit-Organisation, die in Form vorgefertigter Lizenzverträge eine Hilfestellung für Urheber zur Freigabe rechtlich geschützter Inhalte anbietet" {cite}`CreativeCommonsDeutschland_2020`.

Es werden sechs Standards-Lizenzverträge angeboten, die für die Publikation und Verbreitung kreativer Inhalte oder Ressourcen genutzt werden können, um die rechtlichen Bedingungen zu definieren. Sie bestehen aus kombinierbaren Modulen, die unterschiedliche Nutzungsrechte festlegen {cite}`Forschungsdateninfo_CC_oJ`.

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

Wer im Sinne der {ref}`FAIR-Prinzipien <leitlinien-fair>` handelt will, sollte für Forschungsdaten die möglichst offene Lizenz <a href="https://creativecommons.org/licenses/by/4.0/" class="external-link" target="_blank">CC BY 4.0</a> wählen, da sie die Nachnutzung und Zitierbarkeit unter Namensnennung sicherstellt {cite}`Forschungsdateninfo_CC_oJ`.

```{admonition} Keine Lizenzangabe
:class: caution
Ohne explizite Lizenzangabe gilt automatisch das Urheberrecht, das heißt, dass eine Nachnutzung ohne Rückfrage rechtlich nicht erlaubt ist. Andere Forschende sind: 
> "...nur im Rahmen der gesetzlichen Schranken zur Nutzung von urheberrechtlich geschützten Materialien berechtigt, z. B. durch das Zitatrecht (§ 51 UrhG) oder für eigene bzw. gemeinschaftliche, nicht-kommerzielle, wissenschaftliche Forschung (§ 60c UrhG)" {cite}`Brettschneider_2021`.
```

#### Was ist der Unterschied zwischen 4.0 und 3.0?

Die CC-Versionen 4.0 sind die aktuellen und überarbeiteten Lizenzverträge, welche ausdrücklich empfohlen werden {cite}`UniversityMinnesota_oJ`. Ab Version 4.0 decken die CC-Lizenzen ebenfalls Datenbankrechte ab. Insofern sind die Lizenzen auch explizit für Forschungsdaten geeignet. forschungsdaten\.info weist darauf hin, dass bei früheren Versionen die Schutzwirkung fraglich ist {cite}`Forschungsdateninfo_CC_oJ`.

#### Welche Lizenz passt zu meinen Daten?

Um die Auswahl der Lizenz zu erleichtern, haben Barbara Klute und Jöran Muuß-Merholz für <a href="https://wb-web.de/material/medien/die-cc-lizenzen-im-uberblick-welche-lizenz-fur-welche-zwecke-1.html" class="external-link" target="_blank">wb-web</a> eine Entscheidungsgrafik erstellt:

```{figure} ../assets/06_publikation_repositorien/abb_k06_lizenzwahl.jpg
---
align: center
width: 95%
name: lizenzwahl
---
Grafik von Barbara Klute und Jöran Muuß-Merholz für <a href="https://wb-web.de/material/medien/die-cc-lizenzen-im-uberblick-welche-lizenz-fur-welche-zwecke-1.html" class="external-link" target="_blank">wb-web</a> © CC BY SA 3.0
```

Ebenso kann mit dem <a href="https://creativecommons.org/chooser/" class="external-link" target="_blank">Creative Commons License Chooser</a> eine passende Lizenzempfehlung durch Ausfüllen des Minimalfragebogens ausgegeben werden.

```{figure} ../assets/06_publikation_repositorien/abb_k06_cc_chooser.png
---
align: center
width: 95%
name: cc-license-chooser
---
Fragebogen des CC License Choosers
```

```{admonition} Unwiderruflichkeit von CC-Lizenzen 
:class: caution
Eine einmal vergebene Lizenz kann nicht zurückgezogen werden. Ein Werk kann also auch dann noch weiterhin gemäß den ursprünglichen Lizenzbedingungen genutzt werden, wenn der/die Urheber:in die Lizenz nachträglich ändern möchte. Neue Versionen eines Datensatzes können jedoch unter einer anderen Lizenz veröffentlicht werden. 
Für die Praxis bedeutet dies, dass die Lizenzvergabe **vor** der Publikation sorgfältig zu prüfen ist. Nachträgliche Änderungen (z. B. von CC BY zu CC BY-NC) gelten dann nur für neue Versionen, nicht für bereits veröffentlichte Stände {cite}`Kreutzer_2016`. 
```

### Lizenzen für Code und Software

Für Programmcode oder beispielsweise Pythonskripte und Software jeglicher Art gelten CC-Lizenzen als ungeeignet, da software-spezifische Komponenten wie Kompatibilität oder Abhängigkeiten nicht mit definiert werden. Daher gibt es für Codes, Software und Skripte eigene Lizenzen:

````{margin}
```{admonition} Was bedeutet "Copyleft"
:class: hinweis
Das Copyleft Lizenzmodell erlaubt Nutzenden die freie Bearbeitung und Verbreitung eines Werkes (z. B. Erweiterung, Veränderung), sofern jegliche Bearbeitung unter die Lizenz des ursprünglichen Werkes gestellt wird {cite}`Wikipedia_Copyleft_2024`.
```
````

* <a href="https://opensource.org/license/mit" class="external-link" target="_blank">MIT License</a>: sehr offen, minimale Bedingungen, Namensnennung erforderlich

* <a href="https://www.apache.org/licenses/LICENSE-2.0" class="external-link" target="_blank">Apache License 2.0</a>: wie MIT, zusätzlich mit explizitem Patentschutz

* <a href="https://www.gnu.org/licenses/gpl-3.0.html" class="external-link" target="_blank">GNU General Public License (GPL) 3.0</a>: Copyleft – abgeleitete Werke müssen ebenfalls unter der GPL veröffentlicht werden

* <a href="https://www.gnu.org/licenses/agpl-3.0.html" class="external-link" target="_blank">GNU Affero General Public License (AGPL) 3.0</a>: wie GPL, Copyleft gilt zusätzlich für die Nutzung über Netzwerke und Server, insbesondere bei Webanwendungen

### Lizenzierung in der Filmwissenschaft

Die Lizenzierung von Forschungsdaten und Forschungsmaterial ist durch das geltende Urheberrecht an audiovisuellem Material recht komplex. Primärdaten wie Filme, Filmausschnitte, Screenshots oder Videomaterial sind urheberrechtlich geschützt und können in der Regel **nicht offen publiziert werden**. Eine Ausnahme ist das Bildzitatrecht, das unter bestimmten Bedingungen greift (in Deutschland geregelt in §51 des Urheberrechtsgesetzes (UrhG)).

Für die Publikation von {ref}`Primär- und Sekundärdaten  <primär-sekundär>` gelten folgende Empfehlungen:

* **Primärdaten** (z. B. Film-, Bild- und Videomaterial): Können aufgrund des Urheberrechts in der Regel nicht publiziert werden, es sei denn, die Rechte wurden ausdrücklich eingeholt oder das Material ist Public Domain. In diesem Fall gilt die **Ursprungslizenz** des Materials.
* **Sekundärdaten** (z. B. Annotationen, Metadaten, Analysen, Transkripte, Dokumentationen usw.): Können unter CC-Lizenz publiziert werden, da sie eigenständige wissenschaftliche Werke darstellen.

(sonderfall-moviebarcodes)=
#### Sonderfall Moviebarcodes

Moviebarcodes stellen einen Sonderfall dar und sind nicht lizenzierungspflichtig. Informationen zur konkreten rechtlichen Einordnung gibt es {ref}`hier <rechtliche-einordnung>`. Sofern keine projektspezifischen Anforderungen entgegenstehen, empfiehlt sich die Wahl einer der beiden hier vorgestellten Varianten:

**Variante 1**: Hinweis in der Lizenz-Dokumentation

```{code-block} text

Die in diesem Verzeichnis enthaltenen PNG-Dateien ("Moviebarcodes")
sind automatisch erzeugte, rein schematische Darstellungen von Farb-
und Helligkeitsverläufen audiovisueller Werke.

Sie stellen keine eigenständigen kreativen Werke dar und sind daher
nicht von der Hauptlizenz des Datensets erfasst.

An diesen Visualisierungen werden keine Urheberrechte geltend gemacht.
```

**Variante 2**: CC0 - Public Domain Dedication

```{code-block} text

Die in diesem Verzeichnis enthaltenen PNG-Dateien ("Moviebarcodes")
werden unter CC0 1.0 Universal (Public Domain Dedication) 
veröffentlicht: https://creativecommons.org/publicdomain/zero/1.0/

Soweit rechtlich möglich, verzichten die Autor:innen auf alle
urheberrechtlichen und verwandten Schutzrechte an diesen Dateien.
```

Beide Varianten sind praktikable Möglichkeiten, um die Lizenzierung konkret für die Moviebarcodes zu bestimmen. 

```{admonition} Weiterführende Ressourcen
:class: seealso
* Klimpel, P. & Rack, F. (2023). 
<a href="https://docs.nfdi4culture.de/ta6-audiovisuelle-materialien-urheberrecht-in-forschung-und-lehre/" class="external-link" target="_blank">
Audiovisuelle Materialien in Forschung und Lehre – eine Übersicht zu urheberrechtlichen Aspekten
</a>. NFDI4Culture
* <a href="https://irights.info/artikel/audiovisuelle-medien-forschung-lehre/31993" class="external-link" target="_blank">iRights.info</a>, Urheberrecht und kreatives Schaffen in der digitalen Welt
```
#### Fallbeispiel: Lizenzierung des Projektdatensatzes

Wie kann die konkrete Lizenzierung für einen filmwissenschaftlichen Datensatz mit heterogenen Forschungsdaten aussehen? Anhand des Projektdatensatzes <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset" class="external-link" target="_blank">Intervening World Projections: Audiovisuality of Climate Change – Dataset</a> kann exemplarisch gezeigt werden, wie eine Mehrfachlizenzierung sinnvoll umgesetzt werden kann.

<table class="table-clean">
  <thead>
    <tr>
      <th>Ressource</th>
      <th>Lizenz</th>
      <th>Begründung</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Korpus-Metadatenschema (<code>yml</code>)</td>
      <td>
        <a href="https://creativecommons.org/publicdomain/zero/1.0/" class="external-link" target="_blank">
          CC0 1.0 Universal (Public Domain Dedication)
        </a>
      </td>
      <td>Offene Nachnutzung angestrebt, auch für kommerzielle Zwecke nutzbar</td>
    </tr>
    <tr>
      <td>Annotationsdaten (<code>azp</code>, <code>json</code>)</td>
      <td>
        <a href="https://creativecommons.org/licenses/by-sa/4.0/" class="external-link" target="_blank">
          Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
        </a>
      </td>
      <td>Eigenständige wissenschaftliche Werke, offene Nachnutzung erwünscht</td>
    </tr>
    <tr>
      <td>Metadaten und Dokumentation (verschiedene Formate)</td>
      <td>
        <a href="https://creativecommons.org/licenses/by-sa/4.0/" class="external-link" target="_blank">
          Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
        </a>
      </td>
      <td>Offenheit im Sinne der FAIR-Prinzipien</td>
    </tr>
    <tr>
      <td>Moviebarcodes (<code>png</code>)</td>
      <td>Keine Lizenz</td>
      <td>Kein urheberrechtlicher Schutz als eigenständige Werke</td>
    </tr>
    <tr>
      <td>Primärdaten (<code>mp4</code>, <code>mkv</code>)</td>
      <td>—</td>
      <td>Nicht publiziert, da urheberrechtlich geschütztes Filmmaterial</td>
    </tr>
  </tbody>
</table>

<br>

Die vollständige Lizenzdokumentation ist in der <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset?tab=License-1-ov-file" class="external-link" target="_blank">LICENSE.md</a> im Repository des Datensatzes hinterlegt.

```{admonition} Was ist eine LICENSE-Datei?
:class: hinweis
Ähnliche wie die `README`-Datei, ist eine `LICENSE.md` eine einfache Textdatei im {ref}`Markdown-Format <ergebnis-interpretieren>`, die die rechtlichen Nutzungsbedingungen eines Datensatzes oder Repositoriums definiert. Es wird als Best Practice empfohlen, die Lizenzdatei dem Projektrepository hinzuzufügen.
```

```{admonition} Weiterführende Links und Ressourcen zum Thema Lizenzen
:class: seealso 
* forschungsdaten.info: <a href="https://forschungsdaten.info/fdm-allgemein/rechte-und-pflichten/forschungsdaten-veroeffentlichen/creative-commons-lizenzen" class="external-link" target="_blank">Creative-Commons-Lizenzen</a>
* <a href="https://creativecommons.org/chooser/" class="external-link" target="_blank">Creative Commons License Chooser</a>
* <a href="https://de.creativecommons.net/was-ist-cc/" class="external-link" target="_blank">Creative Commons: Was ist CC?</a>
* <a href="https://creativecommons.org/faq/" class="external-link" target="_blank">Creative Commons: FAQs</a>
* Uni Tübingen: <a href="https://uni-tuebingen.de/einrichtungen/universitaetsbibliothek/forschen-publizieren/open-access/faq-recht-im-open-access/#c2452476" class="external-link" target="_blank">Bildzitat & Bildrechte</a>
* wb-web: <a href="https://wb-web.de/material/medien/die-cc-lizenzen-im-uberblick-welche-lizenz-fur-welche-zwecke-1.html" class="external-link" target="_blank">Die CC-Lizenzen im Überblick – Welche Lizenz für welche Zwecke?</a>
* GitHub-Dokumentation: <a href="https://docs.github.com/de/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository" class="external-link" target="_blank">Ein Repository lizenzieren</a>
```

(daten-zitieren)=
## Daten zitierbar machen

Im letzten Teil dieses Kapitels soll es nun um die Zitierfähigkeit der Daten gehen. Wie Publikationen, so sollten auch Forschungsdaten korrekt angegeben und zitiert werden. Um die eigenen Forschungsdaten zitierbar zu machen, gibt es unterschiedliche Wege. In dem Kapitel zu [allgemeinen Metadatenstandards](../03_metadaten/allgemeine_standards.md) sind wir bereits kurz auf {ref}`Dublin Core <dublin-core-header>` und {ref}`DataCite <data-cite-header>` eingegangen. Neben diesen Varianten, ist die Nutzung des sogenannten Citation File Format (CFF) für Daten und Software, insbesondere in Git-Repositorien, sehr verbreitet. 

Die `CITATION.cff` ist eine standardisierte Metadatendatei im {ref}`YAML-Format <metadatenschema-template>`, die beschreibt, wie ein Datensatz oder eine Software korrekt zitiert werden soll. Sie wird von GitHub und Zenodo direkt unterstützt. Wer das Repo besucht, kann die Zitationsinformationen also mit einem Klick exportieren.

```{figure} ../assets/06_publikation_repositorien/abb_k06_cff_github.png
---
align: center
width: 100%
name: cff-github
---
Zitieren des Repositoriums über die `CITATION.cff`
```

Ohne explizite Zitierstandards werden Forschungsdaten oder Software entweder inkonsistent oder gar nicht zitiert. Mit Formaten wie der `CITATION.cff` können diese Probleme minimiert werden, indem maschinenlesbare Zitiermetadaten direkt in den jeweiligen Repositorien hinterlegt werden. 

### Aufbau einer CITATION.cff

Wie eine `CITATION.cff` aufgebaut ist, zeigt folgender Eintrag – übernommen aus der <a href="https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-citation-files" class="external-link" target="_blank">Dokumentation</a> von GitHub:

```yaml
cff-version: 1.2.0
message: "If you use this software, please cite it as below."
authors:
- family-names: "Lisa"
  given-names: "Mona"
  orcid: "https://orcid.org/0000-0000-0000-0000"
- family-names: "Bot"
  given-names: "Hew"
  orcid: "https://orcid.org/0000-0000-0000-0000"
title: "My Research Software"
version: 2.0.4
doi: 10.5281/zenodo.1234
date-released: 2017-12-18
url: "https://github.com/github-linguist/linguist"
  ```

Für die Erstellung einer `CITATION.cff` kann ein kostenloser Code- und Text-Editor wie <a href="https://code.visualstudio.com/" class="external-link" target="_blank">VS Code</a> genutzt werden.

```{admonition} Generierung/Validierung
:class: important
Vor der Publikation sollte die `CITATION.cff` auf ihre Korrektheit überprüft werden. Dafür steht 
<a href="https://citation-file-format.github.io/cff-initializer-javascript/#/" class="external-link" target="_blank">cffinit (CITATION.cff Generator)</a> zur Verfügung. Der Generator zeigt nicht nur Fehler an, sondern kann auch als interaktives Formular zur Erstellung einer `CITATIION.cff` genutzt werden und wird ausdrücklich zur Nutzung empfohlen.
```


````{margin}
```{admonition} Siehe auch:
:class: seealso
Mehr Informationen zu **persistenten Identifikatoren** gibt es in unserer  <a href="https://quadriga-dk.github.io/Tabelle-Fallstudie-1/Markdown/5_2_PID.html" class="external-link" target="_blank">QUADRIGA Fallstudie: "Reproduzierbarkeit von Datenanalysen: Ein Fallbeispiel aus dem Nationalen Bildungsbericht"</a>.
```
````

Wichtig für die Zitierfähigkeit der Daten ist in jedem Fall ein **persistenter Identifikator** (kurz: PID). Dies ist für Forschungsdaten häufig eine DOI (**D**igital **O**bject **I**dentifier), also ein eindeutiger und permanenter Identifikator für digitale Objekte wie beispielsweise wissenschaftliche Aufsätze, Publikationen, Forschungsdaten oder Videos. Ähnlich wie eine ISBN-Nummer, dienen DOI's dazu, Objekte im Internet dauerhaft auffindbar und zitierbar zu machen. Eine DOI besteht häufig aus einer Aneinanderreihung von Zahlen. Die Kennung beginnt immer mit 10, zum Beispiel: `doi:10.1000/199` {cite}`FUBerlin_DOI_oJ`.
Die DOI sollte in der `CITATION.cff` angegeben werden. Viele Repositorien vergeben DOIs bei einer Publikation automatisch. Eine Übersicht für Repositorien mit DOI-Vergabe findet sich {ref}`hier <repositorien-doivergabe>`. 

```{admonition} DOI-Vergabe und GitHub
:class: hinweis
Für die Vergabe von DOIs wird GitHub in der Regel mit einem Repositorium wie Zenodo verknüpft. Das vorliegende Projekt nutzt ebenfalls diese Kombination. Nach der Publikation auf Zenodo wird die DOI für das Repositorium generiert und kann anschließend in der `CITATION.cff` ergänzt werden. Es empfiehlt sich, im Vorfeld einen Platzhalter (Beispiel-DOI oder Ähnliches) für die DOI einzutragen, um ggf. Fehlermeldungen bei der Validierung der DOI zu vermeiden.
```

```{admonition} Weiterführende Links und Ressourcen zum Thema Datenzitation
:class: seealso
* forschungsdaten.info: <a href="https://forschungsdaten.info/fdm-allgemein/finden-und-nachnutzen/forschungsdaten-nachnutzen#c1554" class="external-link" target="_blank">Forschungsdaten nachnutzen</a>
* <a href="https://citation-file-format.github.io/" class="external-link" target="_blank">Citation File Format (CFF)</a>
* Zenodo-Dokumentation: <a href="https://help.zenodo.org/docs/github/describe-software/" class="external-link" target="_blank">Describe software</a>
```
Sind die Grundlagen zur Versionierung, Lizenzierung und Zitierfähigkeit geklärt, rückt die Veröffentlichung einen Schritt näher. Ein Aspekt, der im Vorfeld jedoch häufig unterschätzt wird, ist die Kuratierung und Organisation der Daten. Diesem Thema widmet sich das folgende Kapitel. 

## Literatur

```{bibliography}
:filter: docname in docnames
```

# Kuratierung & Organisation

```{admonition} Story
:class: story
Das filmwissenschaftliche Teilprojekt der FU Berlin hat sich nun alle wichtigen Grundlagen zur [Versionierung, Lizenzierung und Zitierfähigkeit](./versionierung_lizenzierung.md) angeschaut und die wichtigen Durchführungsschritte dazu eingeleitet. 
Doch bevor das Datenset und alle notwendigen Dateien tatsächlich in das Repository auf GitHub hochgeladen werden können, fehlt noch ein häufig vernachlässigter Bestandteil der Arbeit mit Forschungsdaten: Das Aufräumen und Organisieren der Daten. Im Projektalltag sind Daten und Dateien häufig lokal oder auf verschiedenen Clouddiensten gleichzeitig verstreut, unterschiedlich benannt und in inkonsistenten Ordnerstrukturen abgelegt. Vor der Veröffentlichung müssen sie also kuratiert, vereinheitlicht und publikationsreif strukturiert werden. Die wichtigsten Schritte hierzu werden in den nachfolgenden Abschnitten behandelt.
```

## Ordnerstrukturen

Eine durchdachte Ordnerstruktur bildet die Basis eines nachnutzbaren Datensets. Sie erleichtert dabei nicht nur den eigenen Arbeitsprozess, sondern sorgt dafür, dass externe Nutzer:innen die publizierten Daten erschließen können. Grundsätzlich gilt: Eine Ordnerstruktur ist dann gut, wenn sie einer außenstehenden Person deutlich macht, wo welche Daten zu finden sind und wie sie zusammenhängen {cite}`RatSWD_2023`.

### Richtlinien für Ordnerstrukturen


Die folgenden Empfehlungen haben sich nach dem <a href="https://www.konsortswd.de/ueber-uns/" class="external-link" target="_blank">Rat für Sozial- und Wirtschaftsdaten</a> sowie dem <a href="https://www.forschungsdaten-bildung.de/" class="external-link" target="_blank">Verbund Forschungsdaten Bildung</a> als Best Practice etabliert {cite}`VerbundFDB_Dateien_oJ,RatSWD_2023`:

* Die Struktur ist **hierarchisch** gegliedert und umfasst **maximal drei Unterordner-Ebenen**
* Die Benennung ist **klar, konsistent und selbsterklärend**
* Eine {ref}`README-Datei <dokumentation>` im Wurzelverzeichnis dokumentiert die Struktur und ihre Logik
* In Projekten mit mehreren Beteiligten werden **Verantwortlichkeiten** festgelegt: Wer darf neue Ordner anlegen? Wer verwaltet den Zugriff?

Weitere Dokumentationsdateien – zum Beispiel zu einer bestimmten Methode eines konkretes Datentyps – können den jeweiligen zugehörigen Ordnern beigelegt werden.

### Beispiel: Repository-Ablage des Projektdatensatzes


Für die Publikation auf GitHub hat das Projekt eine Ordnerstruktur entwickelt, die die unterschiedlichen Datentypen klar voneinander trennt. Das folgende Baumdiagramm zeigt die Ablagestruktur und kann als Orientierung für das eigene Projekt dienen. Die Ablage kann ebenso direkt in dem Projektrepository <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset" class="external-link" target="_blank">"Intervening World Projections: Audiovisuality of Climate Change"</a> eingesehen werden.

```text
intervening-world-projections-dataset/ # Rootverzeichnis
│
├── assets/                  # Visualisierungen und weitere Ressourcen
├── data/                    # Forschungsdaten
│   ├── annotations/         # Annotationsdaten (azp, json)
│   │   ├── f001a.azp
│   │   ├── f001a.json
│   │   └── ...
│   ├── moviebarcodes/       # Visualisierungen (png)
│   │   ├── f001a_barcode.png
│   │   └── ...
│   └── metadata/            # Korpusmetadaten (xlsx, csv, html, json)
│
├── documentation/           # Dokumentationen, Tutorials und Guidelines
├── schema/                  # corpus-metadata-schema.yml
│
├── .gitignore               # Von Git ignorierte Dateien
├── CITATION.cff             # Zitationshinweis
├── LICENSE.md               # Lizenzierung des Datensets
└── README.md                # Zentrale Dokumentationsdatei des Repositoriums
```

In dieser Struktur werden Forschungsdaten (`data/`), Dokumentationsdateien (`documentation/`), das projekteigene 
{ref}`YAML-Schema <yaml-schema>`, sowie projektweite Dateien (LICENSE, CITATION) voneinander getrennt.  Innerhalb von `data/` sind die drei Datentypen – Annotationen, Moviebarcodes und Metadaten – in eigenen Unterordnern organisiert.

Desweiteren ist es ratsam, Ordner (hier: `assets/`) für Bilder oder Visualisierungen anzulegen, die für Erklärungs- und Veranschaulichungszwecke genutzt werden aber nicht Teil des Datensets sind. 

## Dateibenennung

Neben der Ordnerstruktur ist ein konsistentes **Dateibenennungssystem** entscheidend dafür, dass Dateien auffindbar, maschinell verarbeitbar und für Dritte verständlich sind. In Projekten, an denen mehrere Personen beteiligt sind, entstehen ohne klare Regeln schnell Benennungschaos und Versionskonflikte.

```{admonition} Definieren von Regeln
:class: important
Es sollten klare Regeln definiert werden. Die Benennungsregeln sollten in einem projektinternen Dokument (z. B. einer README "Dateibenennungssystem/Dateibenennungsregeln"), festgehalten und für alle Projektmitglieder zugänglich gemacht werden {cite}`RatSWD_2023`. Dabei sollte zwischen der projektinternen Dateibenennung und der Benennung der zu publizierenden Daten unterschieden und diese gegebenenfalls klar voneinander getrennt werden, sollte es konkrete Abweichungen geben.
```

### Richtlinien für Dateinamen 

Die folgenden Konventionen gelten laut dem Verbund Forschungsdaten Bildung und dem <a href="https://mantra.ed.ac.uk/organisingdata/" class="external-link" target="_blank">Research Data Management Training (MANTRA)</a> der University of Edinburgh als Standard {cite}`UniversityEdinburgh_2022,VerbundFDB_Dateien_oJ`: 

```{admonition} Dateinamen - die wichtigsten Aspekte
:class: keypoint
* **Kurz, aber aussagekräftig**: Dateinamen so kurz wie möglich, so lang wie nötig. Als Richtwert gilt eine maximale Länge von 30 Zeichen; zusammen mit dem Ordnerpfad sollte die Gesamtlänge 255 Zeichen (Windows-Limit) nicht überschreiten
* **Maschinenlesbar**: Keine Leerzeichen, Umlaute (ä, ö, ü) oder Sonderzeichen (`$`, `@`, `%`, `#`, `&`, `!`, `/`). Erlaubt: Buchstaben `a–z`, Ziffern `0–9`, Unterstriche `_` und Bindestriche `-`
* **Einheitlich und konsistent**: Immer dieselben Elemente in derselben Reihenfolge verwenden
* **Selbsterklärend**: Der Name sollte den Inhalt der Datei beschreiben, auf generische Bezeichnungen wie `daten`, `final`, `neu` verzichten
```

### Schreibweisen für zusammengesetzte Namen

Für zusammengesetzte Datei- und Ordnernamen haben sich diese vier Konventionen als Best Practice gezeigt {cite}`RatSWD_2023`:

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
      <th>Schreibweise</th>
      <th>Beispiel</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>snake_case</td>
      <td><code>corpus_metadata_v1.csv</code></td>
    </tr>
    <tr>
      <td>kebab-case</td>
      <td><code>corpus-metadata-v1.csv</code></td>
    </tr>
    <tr>
      <td>camelCase</td>
      <td><code>corpusMetadataV1.csv</code></td>
    </tr>
    <tr>
      <td>PascalCase</td>
      <td><code>CorpusMetadataV1.csv</code></td>
    </tr>
  </tbody>
</table>
<br>

Die Namen sollten den *Inhalt* beschreiben und dabei "so kurz wie möglich, aber so lange wie nötig" sein, um die Dateien oder Ordner verständlich zu machen {cite}`RatSWD_2023`.


Für Forschungsdaten und Dokumentationsdateien hat sich `snake_case` als gut lesbare und weitverbreitete Konvention etabliert. Sie wird auch im {ref}`Metadatenschema <projekt-metadatenschema>` dieses Projekts verwendet. 

 **Nicht empfohlen** sind Dateibenennungen wie `Beispieldatei_final`, `Beispieldatei_final2`, `Beispieldatei_FINAL_wirklich` `Beispieldatei_Bearbeitung_neu`. Sie lassen keine sinnvolle Sortierung zu, signalisieren keinen klar definierten Versionsstand und sind für andere unverständlich und nicht interpretierbar {cite}`VerbundFDB_Dateien_oJ`. 

```{admonition} Dateibenennung im Projektrepository
:class: hinweis
Die Annotationsdaten (`azp`, `json`) und Moviebarcodes (`png`) tragen die Objekt-ID als Dateinamen. So ist sichergestellt, dass die jeweiligen Daten durch die Metadaten identifiziert und zugeordnet werden können.

So trägt beispielsweise der Film *Anthropocene: The Human Epoch* (R: Jennifer Baichwal, Edward Burtynsky, Nicholas de Pencier, CAN 2018) die Objekt-ID `f002a`. Die korrespondierende Moviebarcodedatei trägt den Namen `mb_f002a_0`, wobei die angehängte Zahl am Ende (Suffix) festlegt, ob es sich um einen Moviebarcode für den gesamten Film `0` oder für eine annotierte Szene handelt (Szene 1 =  `mb_f002a_1`, Szene 2 =  `mb_f002a_2` usw.).

Alle weiteren Dateien (Metadaten und Dokumentationen) sind kleingeschrieben und durch snake_case getrennt. 
```

## Versionierung ohne Git

Im Abschnitt zur {ref}`Versionierung <versionierung>` im vorigen Kapitel wurde <a href="https://semver.org/" class="external-link" target="_blank">Semantic Versioning</a> (SemVer) für Git-basierte Workflows vorgestellt. Wenn keine Versionskontrolle mit Git verwendet wird, etwa in frühen Projektphasen oder bei der Zusammenarbeit über Cloud-Dienste, lässt sich folgendes, überschaubares Versionierungssystem übernehmen, das sich aus SemVer ableiten lässt. **Im Dateinamen** kann zwischen größeren und kleineren Änderungen unterschieden werden {cite}`VerbundFDB_Dateien_oJ`:

```
corpus_metadata_v1-0.csv   →   corpus_metadata_v2-0.csv   (größere Änderung)
corpus_metadata_v1-0.csv   →   corpus_metadata_v1-1.csv   (kleinere Änderung)
```

In einer gesonderten Versionstabelle,  z. B. in einer Dokumentationsdatei oder in einem eigenen sogennanten `CHANGELOG.md`, kann der Änderungsverlauf zusätzlich dokumentiert werden:

<table class="table-clean">
  <thead>
    <tr>
      <th>Version</th>
      <th>Datum</th>
      <th>Geändert von</th>
      <th>Änderungen</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1.0</td>
      <td>2024-03-01</td>
      <td>KL</td>
      <td>Erstveröffentlichung</td>
    </tr>
    <tr>
      <td>1.1</td>
      <td>2024-06-15</td>
      <td>RS</td>
      <td>Korrekturen in Spalte <code>year</code></td>
    </tr>
    <tr>
      <td>2.0</td>
      <td>2025-01-10</td>
      <td>LD</td>
      <td>Neues Feld <code>country_iso</code> ergänzt</td>
    </tr>
  </tbody>
</table>

```{admonition} Was ist ein Changelog?
:class: hinweis
Ein Changelog ist ein Änderungsprotokoll, zumeist angelegt als reine Textdatei, die wesentliche Änderungen einer Software oder einer Website dokumentiert. Sie kann ebenfalls für Forschungsdaten eingesetzt werden und ist Teil einer guten Dokumentationspraxis. Changelogs werden nicht nur intern verwendet, sie können ebenfalls im Repositorium mit publiziert werden. Vor allem bei Projekten mit größeren Datenmengen sowie vielen Änderungsverläufen lohnt sich ein öffentlich zugängliches Änderungsprotokoll. Für Git-basierte Workflows kann jedoch auch die Versionskontrolle von GitHub genutzt werden, so wie es das Projektrepository handhabt. Wie ein Changelog aufgebaut ist und worauf es zu achten gilt, kann auf <a href="https://keepachangelog.com/en/1.1.0/" class="external-link" target="_blank">Keep a Changelog</a> abgerufen werden {cite}`Lacan_2019`.
```

## Datensicherung und Backup

Wie kann Datenverlust minimiert oder vermieden werden? Datensicherung ist, wie die Organisation und Kuratierung der Daten, kein einmaliger Schritt, sondern eine prozessbegleitende Aufgabe. Oftmals werden Sicherungsstrategien bereits in [Datenmanagementplänen](../02_forschungsdaten_fdm/datenmanagementplan.md) festgehalten. In der Praxis gerät die Sicherung der Daten jedoch häufig in Vergessenheit. Daher soll es in diesem Abschnitt darum gehen, bewährte Sicherungsstrategien und Aspekte der Datensicherung vorzustellen.

### Speicherorte und Speicherlösungen

Vor der Festlegung einer geeigneten Backup-Strategie ist es ratsam, die Wahl des Speicherortes zu klären. Nach dem Rat für Sozial- und Wirtschaftsdaten sind dabei relevante Kriterien {cite}`RatSWD_2023`:

* Speicherplatz: Wie groß ist das Datenvolumen insgesamt?
* Datenzugang: Wer braucht Zugang?
* Teamarbeit: Ist simultanes Arbeiten an Dateien notwendig?
* Speicherort: Befinden sich die Daten auf Servern innerhalb der EU? Bei personenbezogenen Daten ist dies datenschutzrechtlich relevant.
* Zugriffsbeschränkungen: Können einzelne Ordner für bestimmte Personen gesperrt werden?
* Speicherdauer: Viele tragbare Speichermedien (USB-Sticks, externe Festplatten, CDs) können die für gute wissenschaftliche Praxis geforderte Aufbewahrungsdauer von mindestens zehn Jahren nicht garantieren.

Für kollaborative Forschungsprojekte empfiehlt sich die Nutzung instituitioneller Server- und Clouddienste. Diese bieten einen zentralen Zugang sowie die professionelle Administration und werden zudem von der jeweiligen Einrichtung auf Datenschutzkonformität geprüft.

Neben institutionellen Server- und Clouddiensten stehen diese weiteren Speicherlösungen zur Verfügung: tragbare Speicher (💾 USB-Sticks, externe Festplatten) , lokale Speicher ( 💻 Desktop-PC, Notebook), ☁️ Cloud-Dienste anderer Einrichtungen.

### Backup-Strategie

Als Faustregel für Backups hat sich die **3-2-1-Regel** bewährt {cite}`RatSWD_2023`:

```{figure} ../assets/06_publikation_repositorien/abb_k06_3-2-1_regel.png
---
align: center
width: 85%
name: 3-2-1-regel
---
3-2-1-Regel
```

Ein Beispiel hierfür kann folgendermaßen aussehen:


```text
Arbeitskopie
💻 Lokaler Rechner
       │
       ├──────────► 🌐 GitHub
       │             (Versionierung/zweite Kopie)
       │
       └──────────► 📦 Zenodo
                     (Archivierung/dritte Kopie)
```

**3 Kopien**:

* 💻 Arbeitsrechner
* 🌐 GitHub
* 📦 Zenodo

**2 Speichertypen**:

* lokaler Datenträger
* Online-Repositorien/Cloud

**1 externer Standort**:

* GitHub oder Zenodo

Darüber hinaus sollten folgende Maßnahmen ebenfalls mitbedacht werden:

1. Automatische Backups bevorzugen: Manuelle Backups sind fehleranfällig, mit automatischen Backups sind regelmäßige Speicherprozesse sichergestellt.
2. Verantwortlichkeiten festlegen: Eine hauptverantwortliche Person festlegen, um etwaige Verwirrungen und Unklarheiten zu minimieren.
3. Backups kontrollieren: In regelmäßigen Abständen sollte geprüft werden, ob die Datenwiederherstellung aus dem Backup tatsächlich funktioniert.
4. Aufbewahrungsdauer definieren: Bereits zu Projektbeginn sollte festgelegt werden, wie lange Backups aufbewahrt werden – und wann sie zuverlässig gelöscht werden.

```{admonition} Langzeitarchivierung
:class: important
Ein Backup sichert den Arbeitsstand **während** des Projekts gegen Datenverlust. Es ersetzt keine langfristige Archivierung in einem Repositorium. Die Frage nach der Langzeitarchivierung ist Gegenstand des nächsten Kapitels.
```

```{admonition} Weiterführende Links und Ressourcen
:class: seealso
* <a href="https://www.forschungsdaten-bildung.de/datenmanagement/organisieren/dateien-organisieren/" class="external-link" target="_blank">VerbundFDB: Dateien organisieren</a> – Praxistipps zu Ordnerstrukturen, Dateibenennung und Versionierung
* <a href="https://mantra.ed.ac.uk/organisingdata/" class="external-link" target="_blank">MANTRA – Organising Data</a> – Interaktives Online-Training der University of Edinburgh
* <a href="https://researchdata.org/organizing-data/" class="external-link" target="_blank">Support Your Data – Organizing Data</a> – Best Practices zur Organisation, Dokumentation und Strukturierung von Forschungsdaten
```

Die Kuratierung und Organisation von Forschungsdaten ist ein essentieller Bestandteil des Datenmanagements und der Projektarbeit insgesamt. Sie sollte nicht als abschließender Arbeitsschritt, sondern als kontinuierlicher Prozess verstanden werden. Mit diesen Vorarbeiten sind die Voraussetzungen für eine strukturierte Bereitstellung und Veröffentlichung des Datensets geschaffen. Die letzte Sektion dieser Fallstudie zeigt Schritt für Schritt, wie das Datenset über ausgewählte Dateninfrastrukturen publiziert werden kann. 

... LOS GEHT'S 🚀 ➡️ ➡️ ➡️

## Literatur

```{bibliography}
:filter: docname in docnames
```

# Datenbereinigung und Dokumentation 

*Dieser Abschnitt gibt einen kurzen Überblick über grundlegende Ansätze der Datenbereinigung. Für ausführliche Informationen verweisen wir unten auf weiterführende Ressourcen.*

Neben der Formatkonvertierung ist auch eine Bereinigung und Vereinheitlichung der Daten als Vorbereitung auf die Publikation notwendig. Dabei soll sichergestellt werden, dass der Datensatz **konsistent, fehlerfrei und maschinenlesbar** ist. Auf welche Komponenten zu achten ist und wie es konkret im Projekt umgesetzt wurde, fassen wir hier zusammen:

```{admonition} Datenbereinigung: Die wichtigsten Aspekte
:class: Keypoint
1. Strukturierung der Daten bzw. Datenmodellierung: 
    * Feste Spalten (`title`, `year`, `director` usw.) 
    * Eine Zeile = eine audiovisuelle Ressource 

2. Vereinheitlichung von Schreibweisen und Einträgen:
    * Einheitliche Groß- und Kleinschreibung
    * Entfernung von Leerzeichen, konsistente Verwendung von Sonderzeichen
    * Einheitliche Werte wie z.B. `TRUE` / `FALSE`
    * Konventionen für Feldwerte durch konsistente Verwendung von Trennzeichen – empfohlen mit Semikolon (";") oder       Tabulator
    * Leere Felder statt beliebige Werte

3. Verwendung kontrollierter Vokabulare:
    * Normierte Felder und ISO-Standards
    * Klare Klassifikationen zur Vermeidung von Fehlern (`feature film`, `documentary` usw.); keine Mischformen (`doc`oder `Doku`)

4. Einheitliche Benennung von Spalten und Feldern: 
    * `snake_case` für maximale Kompatibilität mit anderen Datensystemen (`object_id`, `duration_iso8601`)

5. Vergabe stabiler IDs

6. Entfernung von Formatierungen (Farben, Kommentare, Formeln usw.)
```

Ein gängiges und bewährtes Open-Source-Tool für die Datenbereinigung ist <a href="https://openrefine.org/" class="external-link" target="_blank">OpenRefine</a>, das ohne Programmierkenntnisse genutzt werden kann. 

```{admonition} Weiterführende Ressourcen zur Datenbereinigung
:class: seealso
* <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-2/bereinigung/toc.html" class="external-link" target="_blank">QUADRIGA Fallstudie: "Studentische Filme an der Filmuniversität Babelsberg zur Wendezeit (1985-1999)"</a>
* <a href="https://openrefine.org/docs" class="external-link" target="_blank"> OpenRefine user manual</a>
* <a href="https://programminghistorian.org/en/lessons/cleaning-data-with-openrefine " class="external-link" target="_blank">Tutorial Programming Historian zu OpenRefine und Data Cleaning</a>
```

(metadaten-validierung)=
## Metadatenvalidierung

Im Kapitel zur systematischen Aufbereitung der Korpusmetadaten wird {ref}`ein Metadatenschema als Template <metadatenschema-template>` im `yaml`-Format vorgestellt, das genutzt wird, um die filmografischen Projektmetadaten durch kontrolliertes Vokabular, ISO-Standards und feste Muster für Schreibweisen von Werten (z.B: für `year` das pattern `"^[0-9]{4}$"` = `2018`) zu definieren, es werden also **Regeln** festgelegt. Über dieses `yaml`-Schema lassen sich mit einem Python-Skript die erfassten Metadaten im `csv`-Format auf Abweichungen oder Fehler überprüfen bzw. validieren. Das Ergebnis des Skripts ist ein Validation-Report, also eine Datei, die die gefundenen Probleme und Fehler dokumentiert. 

Das `yaml`-Schema beschreibt:

```text
Wie die Metadaten aussehen sollen (definiert Regeln).
```

Das Python-Skript prüft:

```text
Ob die CSV-Datei diese Regeln einhält.
```

Der Report zeigt:

```text
Welche Stellen abweichen und korrigiert werden müssen.
```

Bevor der Python-Code ausgeführt wird, sollte im Vorfeld folgende Ordnerstruktur lokal angelegt werden:

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_ordnerstruktur_validation.png
---
align: center
width: 85%
name: ordnerstruktur-validation
---
Ordnerstruktur für die Metadaten-Validierung
```

Die `csv`-Datei wird also unter `data` abgelegt und das `yaml`-Schema unter `schema`. Der Einfachheit halber wurden die Dateinamen abgekürzt bzw. angepasst. Dies kann zur testweisen Durchführung übernommen werden. 

Um den Python-Code anschließend ausführen zu können, muss die Python-Umgebung aktiviert werden. Hierzu bitte die Schritt-für-Schritt Anleitung aus dem vorigen Abschnitt {ref}`Python-Umgebung einrichten <python-umgebung>` befolgen. Wichtig ist, dass das Notebook in den Ordner `metadata_validation` navigiert wird. Dort wird anschließend das Notebook mit dem Code gespeichert. 

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_ordnerstruktur_validation_markierung.png
---
align: center
width: 85%
name: validierung-mit-markierung
---
Ordnerstruktur mit Notebook-Ablage
```

Anschließend kann folgender Python-Code in der Codezelle abgesetzt werden:

```python
# Die Pakete installieren (falls nicht bereits installiert)
%pip install pandas pyyaml

import pandas as pd
import yaml
import re

# Dateipfade
CSV_FILE = "data/corpus_metadata.csv" # Eingabedatei
SCHEMA_FILE = "schema/corpus_metadata_schema.yml" # YAML-Schema zur Regelprüfung
REPORT_FILE = "validation_report.md" # Ausgabedatei 

# CSV einlesen
df = pd.read_csv(CSV_FILE, sep=";", dtype=str).fillna("")
df.columns = df.columns.str.strip()

# YAML-Schema einlesen
with open(SCHEMA_FILE, "r", encoding="utf-8") as file:
    schema = yaml.safe_load(file)

fields = schema["schema"]["fields"]

errors = []

# Validierung
for field in fields:
    field_name = field["name"]
    required = field.get("required", False)
    pattern = field.get("pattern")
    vocabulary = field.get("vocabulary")

    # Prüfen, ob die Spalte in der CSV vorhanden ist
    if field_name not in df.columns:
        if required:
            errors.append(
                f"FEHLENDE SPALTE: '{field_name}' ist Pflichtfeld, fehlt aber in der CSV."
            )
        continue

    # Werte in der Spalte prüfen
    for row_number, value in df[field_name].items():
        value = value.strip()
        excel_row = row_number + 2

        # Pflichtfeld leer?
        if required and value == "":
            errors.append(
                f"ZEILE {excel_row}: Pflichtfeld '{field_name}' ist leer."
            )

        # Muster / Pattern prüfen
        if pattern and value != "":
            if not re.fullmatch(pattern, value):
                errors.append(
                    f"ZEILE {excel_row}: Wert '{value}' in '{field_name}' passt nicht zum erwarteten Muster: {pattern}"
                )

        # Kontrolliertes Vokabular prüfen
        if vocabulary and value != "":
            if value not in vocabulary:
                errors.append(
                    f"ZEILE {excel_row}: Wert '{value}' in '{field_name}' ist nicht erlaubt. Erlaubt sind: {vocabulary}"
                )

# Report schreiben
with open(REPORT_FILE, "w", encoding="utf-8") as report:
    report.write("# Validation Report\n\n")

    if errors:
        report.write(f"Es wurden {len(errors)} Problem(e) gefunden.\n\n")
        for error in errors:
            report.write(f"- {error}\n")
    else:
        report.write("Keine Probleme gefunden. Alle geprüften Felder entsprechen dem Schema.\n")

# Ergebnis im Notebook anzeigen
print("Validierung abgeschlossen.")
print(f"Geprüfte Datensätze: {len(df)}")
print(f"Geprüfte Schemafelder: {len(fields)}")
print(f"Gefundene Probleme: {len(errors)}")
print(f"Bericht gespeichert als: {REPORT_FILE}")

if errors:
    print("\nErste gefundene Probleme:")
    for error in errors[:10]:
        print("-", error)
else:
    print("\nKeine Probleme gefunden.")
```

(ergebnis-interpretieren)=
### Das Ergebnis interpretieren

Im gewählten Ordnerverzeichnis sollte nun ein sogenanntes Markdown-Dokument mit der Endung `.md` gespeichert sein. Dieses Markdown-Dokument kann mit einem Code- und Text-Editor wie VS Code geöffnet werden (im Abschnitt {ref}`Dokumentation <dokumentation>` kommen wir auf das Markdown-Format zurück.)

```{admonition} Was ist Markdown?
:class: hinweis
Markdown ist eine leichte Auszeichnungssprache, die mit einfachen Zeichen (bzw. einer schnell lesbaren und lernbaren Syntax) Formatierungen ausdrückt: *kursiv* oder **fett** zeigen Betonungen an, Listen sehen wie tatsächliche Listen aus. Markdown-Dateien sind also im Klartext geschrieben und werden beispielsweise von Plattformen wie GitHub, Zenodo oder Jupyter Book gerendered, es wird also eine menschenfreundliche Darstellung erzeugt.
```

Wenn in der Ausgabedatei alles korrekt ist und mit dem Schema übereinstimmt, dann steht im Report:

```text
Keine Probleme gefunden.
```
Wurden Abweichungen identifiziert, dann steht im Report so etwas wie:

```text
ZEILE 181: Wert '124 Min' in 'runtime_min' passt nicht zum erwarteten Muster: "^[0-9]+ Min\\.$"
```

In diesem Beispiel weicht das Muster beispielsweise ab, weil ein erwarteter Punkt `.` am Ende nach `Min.` fehlt. 

`````{admonition} Validierungs-Skript nachnutzen
:class: keypoint
Das Validierungs-Skript selbst ist nicht an ein bestimmtes Metadatenschema gebunden. Es liest die zu prüfenden Felder, Pflichtangaben, Pattern-Regeln und kontrollierte Vokabulare direkt aus dem eingebundenen `yaml`-Schema. Derselbe Workflow kann dadurch auch für angepasste Schemata genutzt werden. Wichtig ist, dass das Schema in der Grundstruktur folgendes enthalten muss:
```yaml
schema:
  fields:
    - name:
      required:
      pattern:
      vocabulary:
```
Ebenso müssen entsprechend bei Abweichungen die Dateipfade und -namen angepasst werden.
`````

(dokumentation)=
## Dokumentation

Gut dokumentierte Forschungsdaten sind sowohl ein wichtiger interner Bestandteil des Forschungsprozesses als auch für die Publikation unerlässlich. In den Kapiteln zum [Forschungsdatenmanagement](../02_forschungsdaten_fdm/toc_02.md) sowie zum Thema [Datenmanagementpläne](../02_forschungsdaten_fdm/datenmanagementplan.md) haben wir bereits alle grundlegenden Aspekte hierfür zusammengefasst. 

Um die Daten jedoch auch für Nutzende verständlich zu machen, braucht es offene Dokumentationsformate, die gemeinsam mit den eigentlichen Daten veröffentlicht werden.

In diesem Projekt haben `README`-Dateien und Tutorials diese Funktion übernommen.

### Was ist eine README-Datei?

Eine `README` ist eine einfache Textdatei, üblicherweise im {ref}`Markdown-Format <ergebnis-interpretieren>`, die Informationen zu einem Datensatz, einem Repository oder einem Ordner enthält. 

Markdown ist sehr beutzerfreundlich und kann schnell erlernt werden. Es werden dabei einfache Zeichen zur Formatierung von Text verwendet, die gängisten listen wir hier auf:

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
      <th>Element</th>
      <th>Syntax</th>
      <th>Ergebnis</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Kursiv</td>
      <td><code>*Text*</code></td>
      <td><em>Text</em></td>
    </tr>
    <tr>
      <td>Fett</td>
      <td><code>**Text**</code></td>
      <td><strong>Text</strong></td>
    </tr>
    <tr>
      <td>Überschrift</td>
      <td><code>## Überschrift</code></td>
      <td>Abschnittsüberschrift</td>
    </tr>
    <tr>
      <td>Link</td>
      <td><code>[Linktext](URL)</code></td>
      <td>Klickbarer Link</td>
    </tr>
    <tr>
      <td>Liste</td>
      <td><code>- Punkt</code></td>
      <td>Aufzählung</td>
    </tr>
    <tr>
      <td>Nummerierte Liste</td>
      <td><code>1. Punkt</code></td>
      <td>Nummerierte Liste</td>
    </tr>
    <tr>
      <td>Code</td>
      <td><code>`code`</code></td>
      <td><code>code</code></td>
    </tr>
    <tr>
      <td>Bild</td>
      <td><code>![Alternativtext](bild.png)</code></td>
      <td>Bild</td>
    </tr>
    <tr>
      <td>Zitat</td>
      <td><code>&gt; Zitat</code></td>
      <td>Zitatblock</td>
    </tr>
  </tbody>
</table>

<br>

Weitere Details zur Syntax können im offiziellen <a href="https://www.markdownguide.org/getting-started/" class="external-link" target="_blank">Markdown Guide</a> oder auf <a href="https://markdown.de/" class="external-link" target="_blank">markdown.de</a> nachgelesen werden. 

### Beispielhafter Aufbau einer README-Datei

Um eine eigene `README` zu schreiben, wird lediglich ein Text-Editor wie beispielsweise VS Code oder <a href=" https://obsidian.md/ " class="external-link" target="_blank">Obsidian</a> benötigt. Hierzu ein neues Dokument erstellen und mit der Endung `.md` speichern.

Wie eine finale `README`-Datei für publizierte Forschungsdaten aussehen kann, zeigt das Datenset des <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset" class="external-link" target="_blank">Projektrepositorys</a>. Desweiteren steht eine entsprechende Vorlage hier zur Verfügung:

````{margin}
```{admonition} Lizenz- und Zitationshinweis
:class: hinweis
Mehr zum Thema Zitation `CITATION.cff` und Lizenzen `LICENSE.MD` gibt es im Kapitel [TODO:LINK].
```
````


```markdown
# [Titel des Datensatzes oder des Repositoriums]

Informationen zum Projekt, Institution, Fördergeber, ggf. Verweis auf DMP

Kurze Beschreibung: Worum geht es, aus welchem Projekt stammen die Daten, was sind zentrale Forschungsfragen?

## Methoden und Tools

Welche Methoden liegen der Datenerhebung zu Grunde? Welche Tools oder Skripte wurden verwendet?

## Inhalte des Datensets / Repositoriums

- Kurze Übersicht der enthaltenen Dateien und Ordner (ggf. als Liste).
- Welche Dateiformate liegen vor, warum wurden sie gewählt?
- Beschreibung der enthaltenen Tabellen/Dateien, ihrer Spalten und Datentypen.
- Ggf. Verweis auf ein separates Datenschema oder Codebook.
→ Empfehlung: damit die README nicht zu lang wird, sollten mehrere Dokumentationsdateien anlegt werden

## Lizenz

Unter welcher Lizenz stehen die Daten? Verweis auf LICENSE-Datei.

## Autor:innen, Zitation, Kontakt

Verweis auf Zitationshinweis, zum Beispiel durch eine CITATION.cff

Auflistung der beteiligten Autor:innen und Contributor 
```

Neben der `README` kann es - je nach Projektkontext - auch sinnvoll sein weitere Anleitungen, Guides, Codebooks oder Dokumentationen bereitzustellen. Dies erleichtert die Nachnutzung der Daten und schafft mehr Transparenz für Nutzende.

Mit der Aufbereitung, Bereinigung und Dokumentation der Forschungsdaten sind die wesentlichen Voraussetzungen für die Publikation geschaffen. Bevor im sechsten Lernmodul [Publikation von Datensets in einem Repositorium](../06_publikation_repositorien/toc_06.md) die konkreten Schritte der Veröffentlichung behandelt werden, greift der folgende Exkurs die vorgestellten Überlegungen und Impulse zu [diskriminierungssensiblen Metadaten](../03_metadaten/diskriminierungssensible_metadaten.md) wieder auf und führt eine punktuelle exemplarische Überprüfung anhand der Korpusmetadaten des Projektes durch.

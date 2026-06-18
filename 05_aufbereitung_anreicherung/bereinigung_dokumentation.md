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
    * `snake_case` für maximale Kompatibilität mit anderen Datensystemen (`object_id`, `runtime_iso`)

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

## Metadatenvalidierung

Im Kapitel zur systematischen Aufbereitung der Korpusmetadaten wird {ref}`ein Metadatenschema als Template <metadatenschema-template>` im `yaml`-Format vorgestellt, das genutzt wird, um die filmographischen Projektmetadaten durch kontrolliertes Vokabular, ISO-Standards und feste Muster für Schreibweisen von Werten (z.B: für `year` das pattern `"^[0-9]{4}$"` = `2018`) zu definieren, es werden also **Regeln** festgelegt. Über dieses `yaml`-Schema lassen sich mit einem Python-Skript die erfassten Metadaten im `csv`-Format auf Abweichungen oder Fehler überprüfen bzw. validieren. Das Ergebnis des Skripts ist ein Validation-Report, also eine Datei, die die gefundenen Probleme und Fehler dokumentiert. 

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

### Das Ergebnis interpretieren

Wenn in der Ausgabedatei alles korrekt ist und mit dem Schema übereinstimmt, dann steht im Report:

```text
Keine Probleme gefunden.
```
Wurden Abweichungen identifiziert, dann steht im Report so etwas wie:

```text
ZEILE 181: Wert '124 Min' in 'runtime_min' passt nicht zum erwarteten Muster: "^[0-9]+ Min\\.$"
```

In diesem Beispiel weicht das Muster beispielsweise ab, weil ein erwarteter Punkt `.` am Ende nach `Min.` fehlt. 
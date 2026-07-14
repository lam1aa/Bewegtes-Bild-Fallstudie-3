---
orphan: true
---

# 1. Metadaten validieren und einen Validation-Report erstellen – mit Visual Studio Code

## Voraussetzungen

Für die Validierung der Metadaten werden benötigt:

* **Python 3**
* **Visual Studio Code (VS Code)**
* Die Python-Erweiterung für VS Code
* Die Python-Bibliotheken **pandas** und **PyYAML**

Python und VS Code sollten bereits installiert sein. Falls dies noch nicht geschehen ist, kann die Einrichtung entsprechend der vorherigen Anleitung [CSV zu JSON mit VS Code](./doc_python_workflow_csv_to_json_v001.md) erfolgen.

## 1.1. Projektordner anlegen

Zunächst einen Projektordner anlegen, beispielsweise

```text
metadata_validation
```

Innerhalb dieses Ordners werden zwei Unterordner angelegt:

```text
metadata_validation
│
├── data
├── schema
```

Danach sollten die bereitgestellten Dateien der OER (das `yaml`-Schema sowie der `csv`-Beispieldatensatz) in den Ordnern wie folgt abgelegt werden:

```text
metadata_validation
│
├── data
│   └── doc_k05_beispieldatensatz.csv
│
├── schema
│   └── doc_k05_corpus_metadata_schema_climate_film_c05.yml
```

Diese Ordnerstruktur entspricht dem Aufbau, den das Python-Skript erwartet.

## 1.2. Projektordner in VS Code öffnen

Öffnen Sie VS Code. Wählen Sie anschließend

`Datei` → `Ordner öffnen`

und öffnen Sie den Ordner

```text
metadata_validation
```

## 1.3. Python-Datei erstellen

Im Hauptordner sollte eine neue Datei erstellt werden mit dem Namen:

```text
validate_metadata.py
```

In diese Datei wird später das bereitgestellte Validierungsskript eingefügt. Das Skript wird hier im Drop-Down bereitgestellt und kann direkt in die Datei `validate_metadata.py` kopiert werden.

`````{dropdown} Das Python-Validierungsskript
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
`````

## 1.4. Terminal öffnen

In VS Code wählen Sie

`Terminal` → `Neues Terminal`

Das Terminal öffnet sich automatisch im Projektordner.

## 1.5. Benötigte Bibliotheken installieren

Falls die Bibliotheken noch nicht installiert wurden, geben Sie im Terminal ein:

```bash
pip install pandas pyyaml
```

oder

```bash
py -m pip install pandas pyyaml
```

Die Installation muss nur einmal erfolgen.

## 1.6. Python-Skript einfügen

Das bereitgestellte Python-Skript kann nun vollständig in `validate_metadata.py` kopiert werden. Da das Skript nun als normale Python-Datei ausgeführt wird und nicht mehr in einem Jupyter Notebook, muss die erste Zeile entfernt werden

```python
%pip install pandas pyyaml
```

Diese Notebook-Anweisung wird durch die Installation im Terminal ersetzt.

Nun müssen ggf. die Dateinamen im Skript angepasst werden.

Beispielsweise:

```python
CSV_FILE = "data/doc_k05_beispieldatensatz.csv"

SCHEMA_FILE = "schema/doc_k05_corpus_metadata_schema_climate_film_c05.yml"

REPORT_FILE = "validation_report.md"
```

Dabei gilt:

* **CSV_FILE** verweist auf die zu prüfende CSV-Datei.
* **SCHEMA_FILE** verweist auf das YAML-Schema mit den Validierungsregeln.
* **REPORT_FILE** legt den Namen des erzeugten Validation-Reports fest.


## 1.7. Skript ausführen

Nach dem Speichern der Datei, kann das Skript im Terminal ausgeführt werden. Dazu kann folgender Befehl ins VS Code Terminal eingefügt werden:

```bash
python validate_metadata.py
```

Nach erfolgreicher Ausführung erscheint beispielsweise:

```text
Validierung abgeschlossen.
Geprüfte Datensätze: 50
Geprüfte Schemafelder: 14
Gefundene Probleme: 0
Bericht gespeichert als: validation_report.md
```

## Häufige Fehlermeldungen

### ModuleNotFoundError: No module named 'pandas'

Die Bibliothek wurde noch nicht installiert.

Lösung:

```bash
pip install pandas
```

### FileNotFoundError

Python findet die CSV-Datei oder das YAML-Schema nicht.

Prüfen Sie:

* Sind beide Dateien im richtigen Ordner?
* Stimmen die Dateinamen?
* Stimmen die Dateiendungen (`.csv` bzw. `.yml`)?
* Sind die Pfade im Skript korrekt angegeben?

### UnicodeDecodeError

Die CSV-Datei wurde nicht als UTF-8 gespeichert.

In Excel sollte die Datei als

**CSV UTF-8 (durch Trennzeichen getrennt) (*.csv)**

exportiert werden.

---

### ParserError beim Einlesen der CSV

In diesem Fall wurde die CSV-Datei häufig mit dem falschen Trennzeichen gespeichert.

Das Skript erwartet standardmäßig:

```text
sep=";"
```

Die CSV-Datei sollte daher semikolongetrennt und als UTF-8 gespeichert sein.
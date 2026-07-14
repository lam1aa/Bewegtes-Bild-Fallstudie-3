---
orphan: true
---

# 1. CSV in JSON konvertieren mit Python und Visual Studio Code

## Voraussetzungen

Für die Konvertierung einer `csv`-Datei in eine `json`-Datei werden benötigt:

* **Python 3**
* **Visual Studio Code (VS Code)**
* Die Python-Erweiterung für VS Code
* Die Python-Bibliothek **pandas**

## 1.1. Python-Erweiterung installieren

1. In VS Code den Reiter `Erweiterungen` öffnen (Symbol mit den vier Quadraten).
2. Suche nach

```
Python
```

Installieren Sie die offizielle Python-Erweiterung des Herausgebers **Microsoft**.

Dadurch erkennt VS Code automatisch Python-Dateien und kann diese ausführen.


## 1.2. Projektordner anlegen

Legen Sie einen neuen Ordner an, beispielsweise:

```
CSV_to_JSON
```

Kopieren Sie anschließend die `csv`-Datei in diesen Ordner.

Beispiel:

```
CSV_to_JSON
│
├── doc_k05_beispieldatensatz.csv
```


## 1.3. Projektordner in VS Code öffnen

In VS Code:

`Datei` → `Ordner öffnen`

und den zuvor angelegten Ordner auswählen.


## 1.4. Python-Datei erstellen

Im Projektordner eine neue Datei erstellen:

```
csv_to_json.py
```

Diese Datei enthält das Konvertierungsskript. Das Skript wird hier im Drop-Down bereitgestellt und kann direkt in die Datei `csv_to_json.py` kopiert werden.

`````{dropdown} Das Python-CSV-to-JSON-Skript
```python
import pandas as pd
import json
import re

# 1) Dateinamen festlegen
input_datei = "annotation_metadata.csv"   # 1. Name der Eingabedatei anpassen
output_datei = "annotation_metadata.json" # 2. Name der Ausgabedatei anpassen

# 2) CSV einlesen
# sep=";" → wichtig, weil Datei semikolon-getrennt ist
# dtype=str Hiermit werden alle Werte erstmal als Text eingelesen 
# die Typkonvertierung erfolgt erst im nächsten Schritt kontrolliert
df = pd.read_csv(input_datei, sep=";", dtype=str)

# 3) Leere Zellen als leere Strings statt NaN behandeln
# pandas füllt leere Felder standardmäßig mit NaN (Not a Number),
# in JSON wird das zu "null"-Werten, daher werden sie als "" gesetzt
df = df.fillna("")

# 4) Funktion zum Umwandeln einzelner Werte
def konvertiere_wert(wert):
    # Falls der Wert kein String ist, direkt zurückgeben
    if not isinstance(wert, str):
        return wert
    # Leerzeichen am Anfang und Ende entfernen
    wert = wert.strip()
    # TRUE / FALSE in echte JSON-Booleans umwandeln
    # (in CSV sind das Strings, in JSON sollten es true/false sein)
    if wert == "TRUE":
        return True
    if wert == "FALSE":
        return False
    # Ganzzahlen in int umwandeln (z.B. Jahreszahlen, Laufzeiten)
    if re.fullmatch(r"-?\d+", wert):
        return int(wert)
    # Alles andere bleibt Text
    return wert

# 5) Alle Zellen der Tabelle durch die Funktion laufen lassen
df = df.map(konvertiere_wert)

# 6) Tabelle in eine Liste von Datensätzen (Dictionaries) umwandeln
# orient="records" bedeutet: jede Zeile wird ein eigenes JSON-Objekt
daten = df.to_dict(orient="records")

# 7) Als JSON-Datei speichern
# ensure_ascii=False bedeutet: Sonderzeichen (Umlaute etc.) bleiben lesbar
# indent=2 sorgt für ein eingerücktes, menschenlesbares Format
with open(output_datei, "w", encoding="utf-8") as f:
    json.dump(daten, f, ensure_ascii=False, indent=2)

print(f"Fertig. JSON gespeichert als: {output_datei}")
```
`````

## 1.5. Terminal öffnen

In VS Code:

`Terminal` → `Neues Terminal`

Es öffnet sich unten ein Terminal. Dieses arbeitet automatisch im Projektordner.


## 1.6. Pandas installieren

Falls `pandas` noch nicht installiert wurde, im Terminal eingeben:

```bash
pip install pandas
```

oder

```bash
py -m pip install pandas
```

Nach erfolgreicher Installation erscheint eine Meldung ähnlich wie:

```text
Successfully installed pandas
```

Die Installation ist nur einmal erforderlich.

## 1.7. Python-Skript einfügen

Das bereitgestellte Python-Skript vollständig in die Datei kopieren.

```
csv_to_json.py
```

Es müssen lediglich diese beiden Zeilen angepasst werden:

```python
input_datei = "doc_k05_beispieldatensatz.csv"
output_datei = "doc_k05_beispieldatensatz.json"
```

Dabei gilt:

* `input_datei` = Name der vorhandenen `csv`-Datei
* `output_datei` = Name der neu zu erzeugenden `json`-Datei

Der restliche Code muss nicht verändert werden. Das Skript liest semikolongetrennte `csv`-Dateien ein, wandelt Datentypen wie Ganzzahlen und TRUE/FALSE-Werte in passende `json`-Typen um und speichert das Ergebnis als `json`-Datei.

## 1.8. Python-Datei ausführen

Im Terminal den folgenden Befehl eingeben:

```bash
python csv_to_json.py
```

Wenn alles erfolgreich war, erscheint:

```text
Fertig. JSON gespeichert als:
doc_k05_beispieldatensatz.json
```


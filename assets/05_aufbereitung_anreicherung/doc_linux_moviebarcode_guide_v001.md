---
orphan: true
---

# 2. Linux (Ubuntu)
## 2.1. Vorbereitungen
### 2.1.1. Installation von FFmpeg und ImageMagick

FFmpeg ist ein freies Multimedia-Framework, das wir benutzen werden, um einzelne Frames aus einer Videodatei zu extrahieren. Diese Frames werden anschließend mit dem freien Bildbearbeitungsprogramm ImageMagick zum fertigen MovieBarcode kombiniert.

Um beide Programme zu installieren, setzen Sie im Terminal folgende Befehle ab:

```Bash
sudo apt update
sudo apt install ffmpeg imagemagick -y
```

Überprüfen Sie anschließend die erfolgreiche Installation:

```Bash
ffmpeg -version
magick -version
```

>**Anmerkung**: Dieser Guide benutzt die auf dem Ubuntu-Repositorium bereitgestellte Version von ImageMagick. Dabei handelt es sich um eine veraltete Version, die jedoch deutlich einfacher und verlässlicher zu installieren ist. Sollte die Version auf dem Repositorium inzwischen aktualisiert worden sein, oder sollten Sie sich für eine aktuelle Version (7+) entscheiden und diese selbstständig installieren, müssen Sie den `convert` Befehl unter 2.2.3. gegen `magick`austauschen.

## 2.2. Erstellen des Barcodes

Legen Sie nun ein Arbeitsverzeichnis an und navigieren Sie im Terminal in das Arbeitsverzeichnis. Beispielsweise so, um ein Verzeichnis unter `/users/<dein_benutzername>/moviebarcode` anzulegen:

```Bash
mkdir ~/moviebarcode
cd ~/moviebarcode
```

Es empfiehlt sich, einen Verzeichnispfad und einen Dateinamen ohne Leerzeichen und Großbuchstaben zu verwenden.

Legen Sie in diesem Verzeichnis die Videodatei ab, aus der Sie den Barcode erzeugen wollen. Wir arbeiten für diesen Guide mit einem Beispielvideo, das den Dateinamen `barcode_test.mkv` trägt. In den folgenden Befehlen muss dieser Platzhalter entsprechend durch den Namen Ihrer Videodatei ersetzt werden.

Setzen Sie alle folgenden Befehle direkt im Arbeitsverzeichnis ab. 

### 2.2.1. Konzeption des finalen Barcodes

Um die Parameter für die Extraktion der Frames zu ermitteln, müssen wir zunächst die finalen Abmessungen des Barcodes festlegen. Im Zuge dieses Guides werden wir einen Barcode erstellen, der die Maße `2520 × 1080 px` hat, sowie eine kleinere Version mit `1680 × 720 px`. Die Maße orientieren sich dabei an der Auflösung des Quellvideos, aus dem der Barcode erzeugt werden soll, wobei hier die Höhe ausschlaggebend ist:

```Bash
ffprobe -v error -select_streams v:0 -show_entries stream=width,height barcode_test.mkv
```

Die Ausgabe sollte in etwa so aussehen:

```
[STREAM]  
width=1920  
height=1080  
[/STREAM]
```

Der `height`-Wert gibt die maximale sinnvolle Höhe des finalen Barcodes in Pixeln vor, da für alles, was darüber hinausgeht, zusätzliche Bildinformationen generiert werden müssten, die in der Quelldatei nicht vorhanden sind. Dies ist möglich, sollte aber grundsätzlich vermieden werden – außer die Quelldatei ist zu niedrig aufgelöst, um einen sinnvoll verwendbaren Barcode zu erzeugen.

Die Breite des finalen Barcodes lässt sich an dieser Stelle fast beliebig festlegen – auch wenn sehr kurze Quelldateien eventuell nicht genug Frames beinhalten, um die nötige Breite zu füllen. Dies stellt im Grunde kein Problem dar, kann jedoch dazu führen, dass der Barcode in der Breite gröber aufgelöst erscheint, da Frames mehrfach ausgegeben werden, um die X-Achse zu füllen.

Für den Zweck dieses Guides legen wir eine Breite von `2520 px` und – wie bereits beschrieben – eine Endauflösung von `2520 × 1080 px` fest.

### 2.2.2. Extrahieren der Einzelframes aus der Quelldatei

Um die Breite von `2520 px` zu füllen, benötigen wir 2520 Einzelframes aus der Quelldatei – ein Frame pro Pixelbreite. Um eine gleichmäßige Verteilung dieser Frames über die Laufzeit des Videos zu gewährleisten, muss zunächst die Laufzeit in Sekunden ermittelt werden.

```Bash
ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 .\barcode_test.mkv
```

Die Ausgabe ist die Dauer des Videos in Sekunden. In diesem Fall `297.708`. Hieraus lässt sich die Anzahl der nötigen Frames pro Sekunde (FPS) für die Laufzeit berechnen:

```Bash
awk 'BEGIN { print sprintf("%.3f", <Finale-Breite> / <Dauer-in-Sekunden>) }'

# Beispielsweise:
awk 'BEGIN { print sprintf("%.3f", 2520 / 297.708) }'
```

Dies ergibt einen auf drei Dezimalstellen gerundeten FPS-Wert – in diesem Fall `8.465`. Anschließend lassen sich mit folgendem Befehl die Frames extrahieren und dabei gleichzeitig auf jeweils `1 px` Breite reduzieren.

```Bash
ffmpeg -i barcode_test.mkv -vf "fps=8.465,scale=1:ih:flags=lanczos" frame_%04d.png
```

Der zuvor ermittelte FPS-Wert wird hier hinter `fps=` eingetragen, dabei ist darauf zu achten, dass die FPS-Zahl mit einem Punkt, nicht mit einem Komma, eingegeben wird. Das Argument `scale=1:ih` weist das Programm an, die Einzelframes jeweils auf 1 px Breite zu reduzieren und die Höhe beizubehalten. Falls Sie eine andere Höhe für den finalen Barcode wünschen, kann diese anstatt `ih` in Pixeln angegeben werden (beispielsweise: `scale=1:720` für eine Höhe von `720 px`).

Die Einzelframes werden durchnummeriert im Arbeitsverzeichnis abgelegt.

#### 2.2.2.1. Extraktion der Einzelframes als Bash-Script

Der Prozess des Ermittelns der FPS und der Extraktion der Einzelframes lässt sich mit folgendem Bash-Script automatisieren. Achten Sie dabei darauf, den Dateinamen Ihrer Quelldatei als Wert für `VIDEO` einzusetzen und die gewünschte Breite Ihres finalen Barcodes als Wert für `FRAME_COUNT`:

```Bash
VIDEO="barcode_test.mkv"
FRAME_COUNT=2520

# Videodauer ermitteln
DURATION=$(ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 "$VIDEO")

# Ziel-FPS berechnen
FPS=$(LC_NUMERIC=C awk "BEGIN { printf \"%.3f\", $FRAME_COUNT / $DURATION }")

echo "Dauer: $DURATION Sekunden, FPS: $FPS"

# Frames extrahieren
ffmpeg -i "$VIDEO" -vf "fps=$FPS,scale=1:ih:flags=lanczos" frame_%04d.png
```

### 2.2.3. Zusammenfügen der Einzelframes zum Barcode und Skalierung

Nun müssen die extrahierten Einzelframes nur noch zum finalen Barcode zusammengefügt werden:

```Bash
convert frame_*.png +append moviebarcode_1080.png
```

Anschließend können wir noch eine verkleinerte Version des Barcodes erzeugen:

```Bash
convert moviebarcode_1080.png -resize x720 moviebarcode_720.png
```

Der Parameter `x720` gibt hier die Höhe der skalierten Version in Pixeln an und kann entsprechend angepasst werden.

>**Anmerkung**: Dieser Guide benutzt die auf dem Ubuntu-Repositorium bereitgestellte Version von ImageMagick. Dabei handelt es sich um eine veraltete Version, die jedoch deutlich einfacher und verlässlicher zu installieren ist. Sollte die Version auf dem Repositorium inzwischen aktualisiert worden sein, oder sollten Sie sich für eine aktuelle Version (7+) entscheiden und diese selbstständig installieren, müssen Sie den `convert` Befehl gegen `magick` austauschen.


### 2.2.4. Automatisierung der gesamten Barcodeerstellung via Bash-Script

Tragen Sie die gewünschten Parameter in die ersten Zeilen ein:

```Bash
# Parameter
VIDEO="barcode_test.mkv"
FRAME_COUNT=2520
OUTFILE="moviebarcode"
PRIMARY_HEIGHT="1080"
SCALED_HEIGHT="720"

# Dauer ermitteln
DURATION=$(ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 "$VIDEO")
FPS=$(LC_NUMERIC=C awk "BEGIN { printf \"%.3f\", $FRAME_COUNT / $DURATION }")

echo "Dauer: $DURATION Sekunden, FPS: $FPS"

# Frames extrahieren
ffmpeg -i "$VIDEO" -vf "fps=$FPS,scale=1:$PRIMARY_HEIGHT:flags=lanczos" frame_%04d.png

# Zusammenfügen
convert frame_*.png +append "${OUTFILE}_${PRIMARY_HEIGHT}.png"

# Skalierte Version
convert "${OUTFILE}_${PRIMARY_HEIGHT}.png" -resize x$SCALED_HEIGHT "${OUTFILE}_720.png"

# Extrahierte Einzelframes löschen
rm frame_*.png
```


---
orphan: true
---

# 1. Windows
## 1.1. Vorbereitungen
### 1.1.1. Chocolatey installieren

Chocolatey ist ein Paketmanager für Windows-Betriebssysteme. Im Rahmen dieses Guides benutzen wir Chocolatey, um FFmpeg und ImageMagick zu installieren. Wenn Sie FFmpeg und ImageMagick bereits installiert haben oder manuell installieren möchten, können Sie diesen Schritt überspringen.

Öffnen Sie die PowerShell als Administrator (Windows-Taste + X, dann "Windows PowerShell (Admin)" auswählen).  
Setzen Sie dort folgenden Befehl ab:

```Shell
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Anschließend können Sie die erfolgreiche Installation überprüfen:

```Shell
choco --version
```

### 1.1.2. Installieren von FFmpeg und ImageMagick

FFmpeg ist ein freies Multimedia-Framework, das wir benutzen werden, um einzelne Frames aus einer Videodatei zu extrahieren. Diese Frames werden anschließend mit dem freien Bildbearbeitungsprogramm ImageMagick zum fertigen MovieBarcode kombiniert.

Um beide Programme mit Chocolatey zu installieren, setzen Sie in der PowerShell (Admin) folgenden Befehl ab:

```Shell
choco install ffmpeg imagemagick -y
```

Chocolatey installiert daraufhin die beiden Programme und eventuell nötige Abhängigkeiten. Gegebenenfalls werden Sie anschließend in der PowerShell dazu aufgefordert, Ihren Rechner neu zu starten. Starten Sie neu oder schließen Sie zumindest die aktuelle PowerShell-Instanz und öffnen Sie eine neue.  
Überprüfen Sie anschließend die erfolgreiche Installation:

```Shell
ffmpeg -version
```

und

```Shell
magick -version
```

Beide Befehle sollten Ihnen ohne Fehlermeldungen die Versionen des jeweiligen Programms anzeigen.

## 1.2. Erstellen des Barcodes

Legen Sie nun ein Arbeitsverzeichnis an und navigieren Sie in der PowerShell in das Arbeitsverzeichnis. Beispielsweise so, um ein Verzeichnis unter `C:\moviebarcode` anzulegen:

```Bash
mkdir C:\moviebarcode
cd C:\moviebarcode
```

Es empfiehlt sich, einen Verzeichnispfad und einen Dateinamen ohne Leerzeichen und Großbuchstaben zu verwenden.

Legen Sie in diesem Verzeichnis die Videodatei ab, aus der Sie den Barcode erzeugen wollen. Wir arbeiten für diesen Guide mit einem Beispielvideo, das den Dateinamen `barcode_test.mkv` trägt. In den folgenden Befehlen muss dieser Platzhalter entsprechend durch den Namen Ihrer Videodatei ersetzt werden.

Setzen Sie alle folgenden Befehle direkt im Arbeitsverzeichnis ab. 

### 1.2.1. Konzeption des finalen Barcodes

Um die Parameter für die Extraktion der Frames zu ermitteln, müssen wir zunächst die finalen Abmessungen des Barcodes festlegen. Im Zuge dieses Guides werden wir einen Barcode erstellen, der die Maße `2520 × 1080 px` hat, sowie eine kleinere Version mit `1680 × 720 px`. Die Maße orientieren sich dabei an der Auflösung des Quellvideos, aus dem der Barcode erzeugt werden soll, wobei hier die Höhe ausschlaggebend ist:

```Shell
ffprobe -v error -select_streams v:0 -show_entries stream=width,height "barcode_test.mkv"
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

### 1.2.2. Extrahieren der Einzelframes aus der Quelldatei

Um die Breite von `2520 px` zu füllen, benötigen wir 2520 Einzelframes aus der Quelldatei – ein Frame pro Pixelbreite. Um eine gleichmäßige Verteilung dieser Frames über die Laufzeit des Videos zu gewährleisten, muss zunächst die Laufzeit in Sekunden ermittelt werden.

```Shell
ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 .\barcode_test.mkv
```

Aus der Ausgabe lässt sich in der PowerShell die Anzahl der benötigten Frames pro Sekunde (FPS) für die Laufzeit berechnen:

```Shell
[math]::Round(<Finale-Breite> / <Dauer-in-Sekunden>, 3)

# Beispielsweise so:
[math]::Round(2520 / 297.708, 3)
```

Dies ergibt einen auf drei Dezimalstellen gerundeten FPS-Wert – in diesem Fall `8.465`. Anschließend lassen sich mit folgendem Befehl die Frames extrahieren und dabei gleichzeitig auf jeweils `1 px` Breite reduzieren:

```Shell
ffmpeg -i .\barcode_test.mkv -vf "fps=8.465,scale=1:ih:flags=lanczos" frame_%04d.png
```

Das Argument `scale=1:ih` weist das Programm hierbei an, die Einzelframes jeweils auf 1 px Breite zu reduzieren und die Höhe beizubehalten. Falls Sie eine andere Höhe für den finalen Barcode wünschen, kann diese anstatt `ih` in Pixeln angegeben werden (beispielsweise: `scale=1:720` für eine Höhe von `720 px`).

Die Einzelframes werden nun durchnummeriert im Arbeitsverzeichnis abgelegt. Achten Sie darauf, dass genügend Speicherplatz vorhanden ist.

#### 1.2.2.1. Extraktion der Einzelframes als PowerShell-Snippet

Der Prozess des Ermittelns der FPS und der Extraktion der Einzelframes lässt sich mit folgendem PowerShell-Snippet automatisieren. Achten Sie dabei darauf, den Dateinamen Ihrer Quelldatei als Wert für `$video` einzusetzen und die gewünschte Breite Ihres finalen Barcodes als Wert für `$frameCount`:

```Shell
$video = "barcode_test.mkv"
$frameCount = 2520

# Videodauer in Sekunden ermitteln
$duration = ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 $video
$duration = [double]::Parse($duration.Trim(), [System.Globalization.CultureInfo]::InvariantCulture)

# Ziel-FPS berechnen
$fps = [math]::Round($frameCount / $duration, 3)

Write-Output "Video-Dauer: $duration Sekunden"
Write-Output "Berechnete FPS: $fps"

# Frames extrahieren
ffmpeg -i $video -vf "fps=$fps,scale=1:ih:flags=lanczos" frame_%04d.png
```

### 1.2.3. Zusammenfügen der Einzelframes zum Barcode und Skalierung

Nun müssen die extrahierten Einzelframes nur noch zum finalen Barcode zusammengefügt werden:

```Shell
magick frame_*.png +append moviebarcode_1080.png
```

Anschließend können wir noch eine verkleinerte Version des Barcodes erzeugen:

```Shell
magick moviebarcode_1080.png -resize x720 moviebarcode_720.png
```

Der Parameter `x720` gibt hier die Höhe der skalierten Version in Pixeln an und kann entsprechend angepasst werden.

### 1.2.4. Erzeugung des gesamten Barcodes als PowerShell-Snippet

```Shell
$video = "barcode_test.mkv"
$frameCount = 2520

# Videodauer in Sekunden ermitteln
$duration = ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 $video
$duration = [double]::Parse($duration.Trim(), [System.Globalization.CultureInfo]::InvariantCulture)

# Ziel-FPS berechnen
$fps = [math]::Round($frameCount / $duration, 3)

Write-Output "Video-Dauer: $duration Sekunden"
Write-Output "Berechnete FPS: $fps"

# Frames extrahieren
ffmpeg -i $video -vf "fps=$fps,scale=1:ih:flags=lanczos" frame_%04d.png

# Einzelframes zusammenfügen
magick frame_*.png +append moviebarcode.png

# Skalierte Kopie erzeugen
magick moviebarcode.png -resize x720 moviebarcode_scaled.png
```

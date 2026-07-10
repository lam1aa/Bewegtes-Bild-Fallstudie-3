# Dateninfrastrukturen

```{admonition} Story
:class: story
Die Forschungsdaten des Projekts wurden kuratiert, sinnvoll benannt und in einer passenden und nachvollziehbaren 
Ordnerhierarchie strukturiert. (vgl. hierzu Kapitel [Kuratierung & Organisation](../06_publikation_repositorien/kuratierung_organisation.md. Diese Struktur kann direkt für den Upload der Daten in einem Repositorium übernommen werden. Der nächste Schritt ist die konkrete Publikation: Wie erstelle ich ein Repository? Wie lade ich die Daten hoch? Und wie stelle ich sicher, dass der Datensatz zitierfähig, versioniert und langzeitverfügbar ist?

          Forschungsprojekt
                 │
                 ▼
     📁 Daten organisiert
     📄 Dokumentiert
     🏷 Lizenziert
                 │
                 ▼
      🚀 Upload ins Repository
                 │
                 ▼
     🌍 Forschungsdatenpublikation
```

## Infrastrukturen

````{margin}
```{admonition} Hinweis: Repositorien
:class: hinweis
Mehr Informationen zu Repositorien gibt es im Kapitel [Publikationswege und -formate](../04_einführung_publikation/publikationswege_formate.md).
```
````

Für die Publikation von Forschungsdaten stehen unterschiedliche Infrastrukturen bzw. Repositorien zur Verfügung, die unterschiedliche Zwecke erfüllen:

* <a href="https://github.com/" class="external-link" target="_blank">GitHub</a> + <a href="https://zenodo.org/" class="external-link" target="_blank">Zenodo</a> : Versionierte Publikation mit DOI-Vergabe; geeignet für aktiv gepflegte Datensätze sowie kollaborative Arbeit → der vom Projekt gewählte primäre Weg
* <a href="https://refubium.fu-berlin.de/" class="external-link" target="_blank">Refubium</a>: Institutionelles Repositorium der Freien Universität Berlin für  Langzeitarchivierung; für FU-Projekte empfohlen; Kontakt über die Universitätsbibliothek
* <a href="https://mediarep.org/home" class="external-link" target="_blank">FID Media</a> (früher: media/rep): Fachrepositorium für Medienwissenschaft, betrieben an der Universität Marburg; geeignet für die fachspezifische Sichtbarkeit des Datensatzes

Für das vorliegende Projekt wurde GitHub als primäre Publikationsplattform gewählt, kombiniert mit Zenodo für die DOI-Vergabe sowie als zweiter externer Speicherort für die Archivierung und Sichtbarkeit der wissenschaftlichen Arbeit. Das Refubium der FU Berlin soll für die institutionelle Langzeitarchivierung genutzt werden. Es wird ebenso eine Publikation auf FID Media angestrebt. 

Die nachfolgenden Schritte zeigen praxisnah und reproduzierbar, wie ein Repository auf GitHub (+ Zenodo) erstellt und veröffentlicht werden kann. 

```{admonition} Hinweis: Plattform-Accounts
:class: hinweis
Hierzu wird sowohl ein GitHub-Account als auch ein Zenodo-Account benötigt. Beide Plattformen sind kostenlos und in den Digital Humanities etabliert.
```

## GitHub-Upload: Technische Voraussetzungen

Git lässt sich direkt über die Kommandozeile bedienen, das ist technisch möglich, aber für die meisten Anwendungsfälle eher umständliche, denn: jede Änderung wird sofort zu einem sogenannten *Commit*, was bei mehreren kleinen Korrekturen (Tippfehler, Formatierungen) schnell zu einer unübersichtlichen Versionsgeschichte führt. Wer an Dateien weiterarbeiten und mehrere Änderungen bündeln möchte, ist mit einer grafischen Oberfläche besser bedient.

```{admonition} Was ist ein Commit auf GitHub?
:class: hinweis
Ein Git-Commit ist ein permanenter Speicherpunkt und zeichnet Änderungen an einer oder mehreren Dateien auf. Git weist jedem Commit eine eindeutige ID zu. Damit wird Folgendes identifiziert:

* Die jeweiligen Änderungen
* Der Zeitpunkt der Änderungen
* Wer die Änderungen vorgenommen hat 

Mehr Informationen finden sich in Schritt 5 sowie auf der <a href="https://docs.github.com/de/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/about-commits " class="external-link" target="_blank">Dokumentationsseite </a> von GitHub.
```
Unsere Empfehlung: <a href="https://github.com/apps/desktop?locale=de-de" class="external-link" target="_blank">GitHub Desktop</a> für die Versionskontrolle und <a href="https://code.visualstudio.com/" class="external-link" target="_blank">Visual Studio Code (VS Code)</a> für die Bearbeitung der Dateien. Beide Tools sind kostenlos plattformübergreifend verfügbar und schnell erlernbar.

## Schritt-für-Schritt: Repository erstellen und befüllen

### Schritt 1: GitHub-Account und Organisation einrichten

1. GitHub-Account erstellen unter <a href="https://github.com/" class="external-link" target="_blank">GitHub</a>
2. Eine Organisation anlegen (z.B. `SFB1512-C05-climate-film`) oder sich als Member einer bestehenden Organisation mit den entsprechenden Zugriffsrechten eintragen lassen; zum Erstellen einer neuen Organisation rechts auf den Profil-Button klicken und anschließend auf → `Organizations` → `New organization`

```{figure} ../assets/06_publikation_repositorien/abb_k06_new_organization_git.png
---
align: center
width: 90%
name: new-organization-git
---
Neue Organisation in GitHub erstellen
```

3. In der Organisation: `New repository` → Name, Beschreibung und Sichtbarkeit (Public/Private) festlegen → Repository erstellen

```{figure} ../assets/06_publikation_repositorien/abb_k06_new_repository_git.png
---
align: center
width: 85%
name: new-repository-git
---
Neues Repository auf GitHub erstellen
```

```{admonition} Einstellungen verwalten
:class: hinweis
Die README-Datei sowie LICENSE können auch nachträglich hinzugefügt werden. Es wird empfohlen die beiden Häkchen deaktiviert zu lassen.
```

### Schritt 2: Repository klonen mit GitHub Desktop

1. GitHub Desktop öffnen und unter `Settings` mit dem GitHub-Account einloggen
2. Anschließend auf `File` → `Clone Repository` gehen
3. Unter dem Reiter **GitHub.com** das Repository auswählen (z.B. `SFB1512-C05-climate-film/intervening-world-projections-dataset`)
4. Lokalen Speicherort wählen, z.B. `~/Documents/intervening-world-projections-dataset`
5. Auf `Clone` klicken

```{figure} ../assets/06_publikation_repositorien/abb_k06_clone_repository_git.png
---
align: center
width: 65%
name: clone-repository
---
Repository klonen mit GitHub Desktop
```

Mehr Informationen und erste Schritte mit GitHub Desktop gibt es in der <a href="https://docs.github.com/de/desktop" class="external-link" target="_blank">GitHub-Dokumentation</a>.

### Schritt 3: Ordnerstruktur anlegen in VS Code und Dateien hochladen

Nach dem Klonen das Repository in VS Code öffnen (`Open in Visual Studio Code` in GitHub Desktop):

```{figure} ../assets/06_publikation_repositorien/abb_k06_open_vs_code.png
---
align: center
width: 85%
name: open-vs-code
---
Das Repository in VS Code öffnen
```

Dort sollte ebenfalls der GitHub-Account verknüpft werden. Hierzu links unten auf den Profil-Button klicken und einloggen.

Die Ordnerstruktur kann jetzt lokal angelegt werden, entweder durch Drag und Drop bereits vorbereiteter Ordner/Dateien oder durch Neuanlage direkt im Editor (vgl. Kapitel [Kuratierung & Organisation](../06_publikation_repositorien/kuratierung_organisation.md) zur empfohlenen Ordnerstruktur).

```{figure} ../assets/06_publikation_repositorien/abb_k06_ordner_anlegen_vs_code.png
---
align: center
width: 100%
name: ordner-vs-code
---
Ordner und Dateien anlegen in VS Code
```

```{admonition} Hinweis: Dateigrößen
:class: important
GitHub ist keine Plattform für große Datenmengen. Die Obergrenze pro Datei beträgt **50 MB**; Repositories sollten insgesamt 1 GB nicht überschreiten. Für größere Dateien (z.B. hochauflösende PNGs, Videos) gibt es zwei Alternativen:

* **Zenodo**: Dateien direkt dort hochladen (max. 50 GB pro Record)
* **Git LFS** (Large File Storage): Große Dateien über Git versionieren, ohne sie direkt im Repository zu speichern; erfordert jedoch zusätzliche Konfiguration!
```

Anschließend können die jeweiligen Dateien in ihre zugehörigen Ordner geladen werden. 

```{admonition} Hinweis: Ordner für Bilder
:class: hinweis
Visualisierungen und Bilder, die Erklärungszwecken dienen, sollten in einen separaten Ordner, z.B. `\assets`, gelegt werden. So können sie von den eigentlichen Datensätzen getrennt werden. 
```

### Schritt 4: Dokumentationsdateien anlegen

Einige Dateien werden von GitHub automatisch erkannt und besonders angezeigt, wenn sie im Wurzelverzeichnis (Root) des Repositories liegen und exakt so benannt sind:

* `README.md` → wird als Startseite des Repositories gerendert (vgl. Abschnitt {ref}`Dokumentation <dokumentation>`)
* `LICENSE` → wird als Lizenzinformation erkannt und verlinkt (vgl. Abschnitt {ref}`Lizenzierung <lizenzierung>`)
* `CITATION.cff` → wird als Zitationshinweis angezeigt (vgl. Abschnitt {ref}`Daten zitierbar machen <daten-zitieren>`)

Für Dokumentationsdateien wie `README.md` oder `LICENSE.md` empfiehlt sich bei der Bearbeitung eine Live Preview im Editor. In VS Code lässt sich diese mit `Cmd+Shift+V` (macOS) bzw. `Strg+Shift+V` (Windows/Linux) öffnen. So ist sofort 
sichtbar, wie die Datei auf GitHub gerendert aussehen wird.

### Schritt 5: Commit und Push

Wenn alle Dateien bereit sind, werden die Änderungen in GitHub Desktop als Commit zusammengefasst und anschließend auf GitHub hochgeladen (Push).

Der Commit kann entweder direkt über VS Code durchgeführt werden oder über GitHub Desktop. 

Wie bereits erwähnt, ist ein **Commit** ist ein gespeicherter Schnappschuss des Repositories zu einem bestimmten 
Zeitpunkt. Jeder Commit erhält eine kurze Beschreibung, die **Commit Message**, in der kurz und knapp dokumentiert werden sollte, was geändert wurde. In GitHub Desktop wird die Commit Message automatisch eingetragen, das Hinzufügen einer Beschreibung ist optional.


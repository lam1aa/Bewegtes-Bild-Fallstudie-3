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

1. GitHub Desktop öffnen und mit dem GitHub-Account einloggen
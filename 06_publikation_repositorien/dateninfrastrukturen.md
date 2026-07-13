# Dateninfrastrukturen

```{admonition} Story
:class: story
Die Forschungsdaten des Projekts wurden kuratiert, sinnvoll benannt und in einer passenden und nachvollziehbaren 
Ordnerhierarchie strukturiert. (vgl. hierzu Kapitel [Kuratierung & Organisation](../06_publikation_repositorien/kuratierung_organisation.md) ) Diese Struktur kann direkt für den Upload der Daten in einem Repositorium übernommen werden. Der nächste Schritt ist die konkrete Publikation: Wie erstelle ich ein Repository? Wie lade ich die Daten hoch? Und wie stelle ich sicher, dass der Datensatz zitierfähig, versioniert und langzeitverfügbar ist?

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
2. Eine Organisation anlegen (z.B. `SFB1512-C05-climate-film`) oder sich als Member/Owner einer bestehenden Organisation mit den entsprechenden Zugriffsrechten eintragen lassen; zum Erstellen einer neuen Organisation rechts auf den Profil-Button klicken und anschließend auf → `Organizations` → `New organization`

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

Wenn alle Dateien bereit sind, können die Änderungen als Commit zusammengefasst und anschließend auf GitHub hochgeladen (Push) werden.

Wie bereits erwähnt, ist ein **Commit** ein gespeicherter Schnappschuss des Repositories zu einem bestimmten 
Zeitpunkt. Jeder Commit erhält eine kurze Beschreibung, die **Commit Message**, in der kurz und knapp dokumentiert werden sollte, was geändert wurde. 

Der Commit kann entweder direkt über VS Code oder über GitHub Desktop durchgeführt werden. 

Jeder Commit erhält eine kurze Beschreibung, die **Commit Message**, in der kurz und knapp dokumentiert werden sollte, was geändert wurde. In GitHub Desktop wird die Commit Message automatisch eingetragen, das Hinzufügen einer Beschreibung ist hier optional.

```{figure} ../assets/06_publikation_repositorien/abb_k06_git_commit_message.png
---
align: center
width: 100%
name: github-desktop-commit-message
---
Commit Message über GitHub Desktop
```

Über `Commit to main` können die Änderungen anschließend in das Repository auf GitHub übertragen werden. 

In VS Code werden in der Quellcodeverwaltung die Änderungen angezeigt. Dort kann in der Spalte `Änderungen` die Commit Message eingetragen und mit `Commit` ausgeführt werden.

```{figure} ../assets/06_publikation_repositorien/abb_k06_git_commit_message_vs_code.png
---
align: center
width: 50%
name: vs-code-commit-message
---
Commit Message über VS Code
```

```{admonition} Hinweis: Commit Message Konventionen 
:class: hinweis
FÜr Commit Message empfiehlt sich die Verwendung oder Orientierung an <a href="https://www.conventionalcommits.org/en/v1.0.0/" class="external-link" target="_blank">Conventional Commits</a>. Conventional Commits sind ein standardisiertes Verfahren zur Erstellung von Git-Commits.

Beispiele:
* `feat: add corpus metadata CSV`
* `fix: correct country code for Geostorm`
* `update: README.md with dataset description`
```

#### Branches und Pull Requests

Bei kollaborativer Arbeit an einem Repository, wenn also mehrere Personen gleichzeitig Änderungen vornehmen, empfiehlt sich die Arbeit mit sogenannten **Branches** und **Pull Requests**.

Ein Branch ist eine parallele Version des Repositories (quasi eine Abzweigung), in der Änderungen vorgenommen werden können, ohne das Hauptrepository (also `main`) zu beeinflussen. Ist die Arbeit abgeschlossen, so kann der Branch über einen Pull Request in den Hauptzweig zurückgeführt werden, jeweils immer mit der Möglichkeit, die Änderungen vorher zu überprüfen und zu kommentieren. 

Zum Erstellen eines Branches im Repository den Reiter `Branches` öffnen und anschließend `New branch` auswählen. Nach Abschluss der Arbeiten im neuen Branch kann ein Pull Request erstellt werden. Hierzu entweder den Button `Compare & pull request` nutzen (dieser wird angezeigt, sofern Änderungen gegenüber `main` vorliegen) oder über `Pull requests` → `New pull request` den entsprechenden Branch auswählen und den Pull Request anlegen.

```{figure} ../assets/06_publikation_repositorien/abb_06_branch_pull_request.png
---
align: center
width: 100%
name: branch-pull-request-git
---
Ablauf: Branch und Pull Request erstellen auf GitHub
```

```{admonition} Achtung: Aktuellen Stand überprüfen
:class: danger
Insbesondere bei einer kollaborativen Arbeit am Repository ist es ratsam, vor Beginn einer neuen Arbeitssitzung sicherzustellen, dass das lokale Repository dem aktuellen Stand des sogenannten Remote-Repositorys, also dem Repository auf GitHub, entspricht. Über GitHub Desktop kann hierzu zunächst die aktuelle Branch (z.B. main) ausgewählt und anschließend über `Fetch origin` geprüft werden, ob zwischenzeitlich Änderungen veröffentlicht wurden. Liegen Aktualisierungen vor, können diese über `Pull origin` in das lokale Repository übernommen werden, bevor die weitere Bearbeitung in VS Code erfolgt.
```


```{admonition} Weiterführende Links
:class: seealso
Detaillierte Informationen zu Branches und Pull Requests gibt es auf den Dokumentationsseiten von GitHub:

* <a href="https://docs.github.com/de/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches" class="external-link" target="_blank">Branches</a>
* <a href="https://docs.github.com/de/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests" class="external-link" target="_blank">Pull Requests</a>
```

### ​​Schritt 6: Release, Versionierung und DOI

Wenn der Datensatz publikationsreif ist, wird ein **Release** erstellt, also eine benannte und getaggte Version des Repositories zu einem bestimmten Zeitpunkt. Releases folgen den Konventionen von <a href="https://semver.org/" class="external-link" target="_blank">Semantic Versioning</a> (SemVer): `MAJOR.MINOR.PATCH` (z.B. `v1.0.0`, vgl. hierzu den Abschnitt {ref}`Versionierung <versionierung>`).

Anschließend kann über die **Zenodo-GitHub-Integration** auf Zenodo automatisch ein DOI für den Release vergeben werden.

````{margin}
```{admonition} Wichtig: Zugriffsrechte
:class: important
Das Repository wird in Zenodo nur angezeigt, wenn die notwendigen Zugriffsrechte hierfür vorhanden sind. Wer nur Member und nicht Owner einer Organisation ist, hat keine erforderlichen Zugriffsrechte. 
```
````

1. Zenodo-Account mit GitHub verknüpfen (hierzu in Zenodo neben dem Profil auf den Drop-Down-Pfeil klicken und in dem sich öffnenden Menü `GitHub` auswählen)
2. Repository in Zenodo aktivieren
3. Auf GitHub einen Release erstellen:
     * Im Repository `Tags` öffnen → `Create a new release` auswählen; dann bei `Select a tag` die Option `Create a new tag` wählen und einen Versions-Tag (z.B. v1.0.0) vergeben
     * Einen aussagekräftigen Titel sowie Release Notes hinzufügen, denn diese dokumentieren die wichtigsten Änderungen gegenüber vorherigen Versionen; für die Strukturierung der Release notes können beispielsweise Empfehlungen wie <a href="https://keepachangelog.com/en/1.1.0/" class="external-link" target="_blank">Keep a Changelog</a> oder  <a href="https://www.conventionalcommits.org/en/v1.0.0/" class="external-link" target="_blank">Conventional Commits</a> herangezogen werden

```{figure} ../assets/06_publikation_repositorien/abb_k06_new_release_git.png
---
align: center
width: 100%
name: new-release-git
---
Einen neuen Release auf GitHub erstellen und taggen
```

5. Den Release anschließend veröffentlichen. Ist das GitHub-Repository mit Zenodo verknüpft, wird für den Release automatisch ein DOI generiert
6. Den DOI in `README.md`, `CITATION.cff` eintragen

### Schritt 7: Langzeitarchivierung und Fachrepositorien

Wie bereits erwähnt, empfehlen sich nach der Erstpublikation auf GitHub und Zenodo die Inanspruchnahme weiterer Publikationsorte für die fachspezifische Sichtbarkeit sowie die Langzeitverfügbarkeit nach den {ref}`FAIR-Prinzipien  <leitlinien-fair>` und den {ref}`DFG-Leitlinien <leitlinien-dfg>` (Aufbewahrung mind. 10 Jahre):

1. Institutionelles Repositorium, sofern von der Hochschule eines zur Verfügung gestellt wird
2. Für film- und medienwissenschaftliche Forschungsdaten kann auf FID Media (früher media/rep) verwiesen werden. Es ist geeignet für die fachspezifische Auffindbarkeit des Datensatzes. Was bei der Einreichung beachtet werden sollte und welche Schritte hierfür nötig sind, kann in der <a href="https://www.uni-marburg.de/de/fb09/medienwissenschaft/forschung/forschungsprojekte/mediarep/projektmitglieder" class="external-link" target="_blank">Handreichung für Autor:innen – in fünf Schritten zur Publikation auf FID Media Publish</a> eingesehen werden.

Weitere fachspezifische Repositorien können auf Repositorien-Findern wie <a href="https://www.re3data.org/" class="external-link" target="_blank">re3data – Registry of Research Data Repositories</a> sowie <a href="https://risources.dfg.de/" class="external-link" target="_blank">RIsources – Portal für Forschungsinfrastrukturen der DFG</a> gesucht werden.
Eine detailierte Auflistung von relevanten Repositorien und Repositorien-Findern in der Film- und Medienwissenschaft gibt es im Kapitel [Ressourcen und Entscheidungshilfen](../04_einführung_publikation/ressourcen_entscheidungshilfen.md).

## Checkliste: Workflow Datenpublikation

```{raw} html
<div class="interactive-checklist" id="github-publication-checklist">
  <p class="checklist-progress">
    Fortschritt: <strong><span class="completed-count">0</span> von 16</strong>
  </p>

  <label>
    <input type="checkbox" data-item="github-account">
    GitHub-Account erstellt
  </label>

  <label>
    <input type="checkbox" data-item="software-installed">
    VS Code und GitHub Desktop installiert
  </label>

  <label>
    <input type="checkbox" data-item="github-organisation">
    Organisation auf GitHub angelegt oder Zugriffsrechte erhalten
  </label>

  <label>
    <input type="checkbox" data-item="repository-created">
    Repository erstellt (Name, Beschreibung, Sichtbarkeit)
  </label>

  <label>
    <input type="checkbox" data-item="repository-cloned">
    Repository lokal geklont (GitHub Desktop)
  </label>

  <label>
    <input type="checkbox" data-item="folder-structure">
    Ordnerstruktur angelegt und Dateien eingepflegt (VS Code)
  </label>

  <label>
    <input type="checkbox" data-item="file-sizes">
    Dateigrößen geprüft (max. 50 MB pro Datei)
  </label>

  <label>
    <input type="checkbox" data-item="readme">
    <code>README.md</code> im Root-Verzeichnis vorhanden
  </label>

  <label>
    <input type="checkbox" data-item="license">
    <code>LICENSE</code> im Root-Verzeichnis vorhanden
  </label>

  <label>
    <input type="checkbox" data-item="citation">
    <code>CITATION.cff</code> vorhanden und ausgefüllt
  </label>

  <label>
    <input type="checkbox" data-item="commit-messages">
    Commit Messages nach Conventional Commits verfasst
  </label>

  <label>
    <input type="checkbox" data-item="committed-pushed">
    Änderungen committed und gepusht
  </label>

  <label>
    <input type="checkbox" data-item="release">
    Release erstellt und getaggt (SemVer)
  </label>

  <label>
    <input type="checkbox" data-item="zenodo">
    Zenodo mit GitHub verknüpft und DOI vergeben
  </label>

  <label>
    <input type="checkbox" data-item="doi-added">
    DOI in <code>README.md</code> und <code>CITATION.cff</code> eingetragen
  </label>

  <label>
    <input type="checkbox" data-item="archiving">
    Langzeitarchivierung (Refubium / Fachrepositorium) angestoßen
  </label>

  <button type="button" class="reset-checklist">
    Auswahl zurücksetzen
  </button>
</div>

<style>
.interactive-checklist {
  margin: 1.25rem 0;
  padding: 1rem 1.2rem;
  border: 1px solid #d9d9d9;
  border-radius: 8px;
  background: #fafafa;
}

.interactive-checklist label {
  display: block;
  padding: 0.4rem 0;
  cursor: pointer;
}

.interactive-checklist input[type="checkbox"] {
  margin-right: 0.55rem;
  transform: scale(1.1);
}

.interactive-checklist label:has(input:checked) {
  color: #666;
  text-decoration: line-through;
}

.checklist-progress {
  margin-top: 0;
  margin-bottom: 0.8rem;
}

.reset-checklist {
  margin-top: 1rem;
  padding: 0.45rem 0.75rem;
  border: 1px solid #aaa;
  border-radius: 5px;
  background: white;
  cursor: pointer;
}

.reset-checklist:hover {
  background: #f0f0f0;
}
</style>

<script>
(function () {
  const checklist = document.getElementById("github-publication-checklist");

  if (!checklist || checklist.dataset.initialized === "true") {
    return;
  }

  checklist.dataset.initialized = "true";

  const storageKey = "github-publication-checklist";
  const checkboxes = checklist.querySelectorAll('input[type="checkbox"]');
  const completedCount = checklist.querySelector(".completed-count");
  const resetButton = checklist.querySelector(".reset-checklist");

  function loadState() {
    const savedState = JSON.parse(
      localStorage.getItem(storageKey) || "{}"
    );

    checkboxes.forEach((checkbox) => {
      checkbox.checked = savedState[checkbox.dataset.item] === true;
    });
  }

  function saveState() {
    const state = {};

    checkboxes.forEach((checkbox) => {
      state[checkbox.dataset.item] = checkbox.checked;
    });

    localStorage.setItem(storageKey, JSON.stringify(state));
  }

  function updateProgress() {
    const checked = checklist.querySelectorAll(
      'input[type="checkbox"]:checked'
    ).length;

    completedCount.textContent = checked;
  }

  checkboxes.forEach((checkbox) => {
    checkbox.addEventListener("change", () => {
      saveState();
      updateProgress();
    });
  });

  resetButton.addEventListener("click", () => {
    checkboxes.forEach((checkbox) => {
      checkbox.checked = false;
    });

    localStorage.removeItem(storageKey);
    updateProgress();
  });

  loadState();
  updateProgress();
})();
</script>
```
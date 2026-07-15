# Resümee

```{admonition} Keypoints: Versionierung, Lizenzierung, Zitierfähigkeit 
:class: keypoint

* Versionierung macht unterschiedliche Veröffentlichungsstände eines Datensatzes eindeutig referenzierbar und dokumentiert Änderungen, sodass sie für andere transparent sind.
    * Sehr etabliert ist das System Semantic Versioning (SemVer). Es unterscheidet zwischen grundlegenden Änderungen (`MAJOR`), abwärtskompatiblen Erweiterungen (`MINOR`) und kleineren Korrekturen (`PATCH`)

* Lizenzen legen fest, unter welchen Bedingungen Forschungsdaten genutzt, bearbeitet und weitergegeben werden dürfen; ohne Lizenzangabe ist eine Nachnutzung grundsätzlich nicht automatisch erlaubt.
    * Für heterogene Datensets kann eine Mehrfachlizenzierung sinnvoll sein: Creative-Commons-Lizenzen für Daten und Dokumentationen, Softwarelizenzen für Code sowie gesonderte Regelungen für urheberrechtlich geschütztes oder nicht schutzfähiges Material.
    * In der Filmwissenschaft können audiovisuelle Primärdaten in der Regel nicht offen publiziert werden, während abgeleitete Forschungsdaten wie Annotationen, Metadaten und Dokumentationen häufig lizenzierbar sind.

* Eine `CITATION.cff` stellt standardisierte, maschinenlesbare Zitationsinformationen bereit; persistente Identifikatoren wie DOIs gewährleisten die dauerhafte Auffindbarkeit und Zitierfähigkeit einer Datenpublikation.
```

```{admonition} Keypoints: Kuratierung und Organisation
:class: keypoint

* Eine nachvollziehbare Ordnerstruktur trennt Forschungsdaten, Metadaten, Dokumentationen, Schemata und projektweite Dateien klar voneinander und erleichtert die Erschließung durch Dritte.
* Dateinamen sollten kurz, aussagekräftig und maschinenlesbar sein; etablierte Konventionen wie `snake_case` vermeiden Leerzeichen, Sonderzeichen und uneindeutige Bezeichnungen.
* Stabile Objekt-IDs ermöglichen die eindeutige Zuordnung zusammengehöriger Dateien und bilden die Grundlage für eine konsistente Organisation relational verknüpfter Datensätze.
* Auch ohne Git sollten unterschiedliche Bearbeitungsstände nach einem festen Versionierungsschema benannt und Änderungen gegebenenfalls in einem `CHANGELOG.md` dokumentiert werden.
* Die 3-2-1-Regel reduziert das Risiko von Datenverlust: drei Kopien auf zwei unterschiedlichen Speichertypen, davon mindestens eine an einem externen Standort.
* Kuratierung, Dateiorganisation und Datensicherung sind prozessbegleitende Aufgaben des FMDs und schaffen die Voraussetzung für eine Publikation nach guter wissenschaftlicher Praxis.
```

```{admonition} Keypoints: Dateninfrastrukuren und Publikation auf Repositorien
:class: keypoint

* Für die Datenpublikation können mehrere Infrastrukturen kombiniert werden: GitHub für Versionskontrolle und kollaborative Bearbeitung, Zenodo für DOI-Vergabe und Archivierung sowie institutionelle oder fachspezifische Repositorien für Langzeitverfügbarkeit und Sichtbarkeit.
* Ein Git-basiertes Repository kann lokal bearbeitet und über versionierte Änderungen mit der Remote-Online-Version synchronisiert werden.
    * Zentrale Dokumentations- und Lizenzdateien sollten klar benannt und an einer gut sichtbaren Stelle im Repository abgelegt werden.
    * Branches und Pull Requests unterstützen kollaborative Arbeitsprozesse, indem Änderungen getrennt vorgenommen, anschließend geprüft und zusammengeführt werden.
    * Ein publikationsreifer Stand wird als Release mit SemVer-Tag veröffentlicht; über die GitHub-Zenodo-Integration kann dafür automatisch eine DOI erzeugt und anschließend in `README.md` und `CITATION.cff` ergänzt werden.
* Die Veröffentlichung auf GitHub und Zenodo ersetzt keine institutionelle oder fachspezifische Langzeitarchivierung, sondern sollte durch geeignete Repositorien ergänzt werden.
```


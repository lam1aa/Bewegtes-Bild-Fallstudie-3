# Commit Guidelines für Bewegtes-Bild-Fallstudie-3

Dieses Dokument definiert die Standards für Commit-Messages, die konkret in unserem Repositorium genutzt werden. Die Verwendung konsistenter Commit-Messages verbessert die Lesbarkeit der Git-Historie und erleichtert das Verständnis von Änderungen.

Für allgemeine Commit-Standards besuchen Sie bitte: [conventionalcommits.org](https://www.conventionalcommits.org/en/v1.0.0/)

## Format

Alle Commit-Messages folgen folgendem Format:

```none
<typ>: <kurze beschreibung>
```
## Verwendete Commit-Typen

`feat`

**Verwendung**: Neue Features, Funktionen oder Verbesserungen

**Beispiele**:

```none
feat: implement search functionality
feat: add support for dark mode
```
***

`fix`

**Verwendung**: Behebung von technischen Fehlern und Bugs

**Beispiele**:

```none
fix: resolve overwritten files
fix: also commit CITATION.cff if changed
```
***

`docs`

**Verwendung**: Inhaltliche Änderungen sowie Änderungen an Dokumentation und Markdown-Dateien, einschließlich Tippfehlern

**Beispiele**:

```none
docs: fix typo in README.md
docs: exchange cross-target link in 'epilog'
```
***

`add`

**Verwendung**: Hinzufügen neuer Dateien, Assets oder Ressourcen

**Beispiele**:

```none
add: new logo image
add: orcid-image link as button
```
***

`update`

**Verwendung**: Kleine allgemeine Änderungen und Neuerungen, die nicht in andere Kategorien passen

**Beispiele**:

```none
update: improve button styling
update: upload new logo image
```

## Branch-Benennung

Für die Benennung von Branches verwenden wir folgendes Format:

* Nur Kleinbuchstaben
* Englische Sprache
* Wörter werden mit Bindestrich (-) voneinander getrennt
* Prägnanter Titel, aus dem hervorgeht, worum es geht

**Beispiel**:

```none
add-summative-assessment-module
```

## Richtlinien 

* Verwendung des Imperativs (z.B. "add" statt "added")
* Verwendung von Kleinbuchstaben mit Außnahme von spezifischen Dateinamen (z.B. README.md)
* Formulierung kurzer und prägnanter Aussagen
* Verwendung von Englisch für Konsistenz 
* Formate und Richtlinien der hier formulierten Standards gelten auch für `pull request`


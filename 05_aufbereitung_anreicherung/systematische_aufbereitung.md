# Systematische Datenaufbereitung 

`````{admonition} Systematisierung der Korpusdaten
:class: story

Die Annotationsdaten wurden erhoben, die [Moviebarcodes](../05_aufbereitung_anreicherung/moviebarcodes.md) aus den Filmdateien extrahiert. Projektintern lagen bereits Dokumentationen und Filmlisten vor, allerdings uneinheitlich und ohne konkrete Systematik. Für eine Datenpublikation ist allerdings die Systematisierung unerlässlich: Daten müssen strukturiert, nachvollziehbar und interoperabel sein. Der erste Schritt ist also die systematische Aufbereitung des gesamten Korpus. Dafür wurde ein projektspezifischer Metadatenstandard entwickelt.

````{admonition} Leitfrage
:class: keypoint
Wie lassen sich unorganisierte [Forschungsdaten](../02_forschungsdaten_fdm/forschungsdaten_fiwi.md) für eine Nachnutzung systematisieren?
````
````{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_rohdaten_systematisierung.png
---
align: center
width: 100%
name: systematisierung
---
Von den Rohdaten zur Systematisierung (KI-generiert)
````
`````

## Das Projekt-Metadatenschema: Beschreibungen und DC/EN-Mapping

````{margin}
```{admonition} Metadatenstandards
:class: hinweis
Mehr Informationen zu Metadatenstandards gibt es im Kapitel [Metadaten & Metadatenstandards](../03_metadaten/toc_03.md)
```
````

Das für das SFB-Projekt entwickelte Metadatenschema orientiert sich an den Basiselementen des [DC-Schemas](../03_metadaten/allgemeine_standards.md) und des [EN 15744](../03_metadaten/metadaten_filmwissenschaft.md). Zentrale Identifikationfelder wie `Titel`, `Identifier`, `Produktionsland`, `Jahr`, `Regie` und `Laufzeit` entsprechen standardnahen Metadatenelementen. Sie dienen einerseits der formalen Einordnung sowie Identifizierbarkeit, andererseits können durch die erfassten Elemente auch weitere Untersuchungen am Korpus ermöglicht werden, wie zum Beispiel Berechnungen von Länderanteilen oder Produktionszeiträumen. 

```{admonition} Wie können die Metadaten genutzt werden?
:class: hinweis
Im Kapitel [Diskriminierungssensible Überprüfung](../05_aufbereitung_anreicherung/diskriminierungssensible_überprüfung.md) führen wir Beispielhaft anhand der Korpusmetadaten punktuell eine Überprüfung mit Fokus auf diskriminierungsensible Aspekte durch.
```

In der Forschungspraxis lässt sich allerdings häufig kein Schema vollständig auf den wissenschaftlichen Kontext übertragen. Dies liegt insbesondere daran, dass Forschungsprojekte eigene Untersuchungsmethoden, Korpusdefinitionen und Analysekateogorien mitbringen, die in den allgemeinen Standards keine Entsprechung finden.

Für das Teilprojekt C05 bedeutet dies konkret: Das Metadatenschema wurde projektspezifisch entwickelt, in weiten Teilen lassen sich die Element jedoch auf das DC/EN-Schema mappen.

Die folgende Tabelle zeigt alle `13 Felder` des Korpusmetadatenschemas mit ihren Entsprechungen in Dublin Core (DC) und EN 15744.
Felder ohne Mapping sind projektspezifische Erweiterungen ohne direkte Entsprechung in einem der beiden Standards.

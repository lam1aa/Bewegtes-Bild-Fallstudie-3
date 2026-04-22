# Metadaten in der Filmwissenschaft

```{image} ../assets/03_metadaten/abb_k03_film_metadaten.png
---
align: center
width: 100%
name: film-metadaten
---
```
<br>

````{margin}
```{admonition} Metadaten am Projektbeispiel
:class: hinweis
Wie ein Filmkorpus und zugehörige Datensätze am konkreten Projektbeispiel durch Metadaten charakterisiert werden können, zeigen wir im Kapitel [Systematische Aufbereitung](../05_aufbereitung_anreicherung/systematische_aufbereitung.md).
```
````

Metadatenstandards in der Filmwissenschaft werden vor allem von Filmarchiven, Kinematheken, Fernsehanstalten und Bibliotheken genutzt, um Filme, Fassungen und Materialien (dazu zählen auch die physischen Trägermedien wie z. B. DVD oder Blu Ray) beschreibbar und auffindbar zu machen. Aber auch Forschungsprojekte greifen auf die Fachstandards zurück, um beispielsweise Filmkorpora durch Metadaten zu charakterisieren.

Gleichzeitig sind Metadateninformationen zu Filmen auch für die Filmrecherche nicht unerheblich. Dabei können die Recherchegründe variieren – von der Suche nach filmbegleitendem Material, Angaben zu beteiligten Personen und Gewerken bis zur Suche nach Aufführungsrechten, historischen Informationen oder Nutzungsrechten. Online-Kataloge und Filmdatenbanken, wie beispielsweise die der <a href="https://www.deutsche-kinemathek.de/de" class="external-link" target="_blank">Deutschen Kinemathek</a> oder dem <a href="https://www.bfi.org.uk/" class="external-link" target="_blank">BFI</a> (British Film Institute), ermöglichen einen mehrdimensionalen Zugriff auf diese Informationen.

```{figure} ../assets/03_metadaten/abb_k03_bfi_katalog.png
---
align: center
width: 100%
name: bfi-katalog
---
Ergebnisansicht mit der Schlagwortsuche "climate change" aus dem Katalog des <a href="https://www.bfi.org.uk/" class="external-link" target="_blank">BFI</a>
```

Dabei spielen Normdaten und Standardisierungen eine wichtige Rolle. Zwei (insbesondere in der EU) sehr bekannte Metadatenstandards für Filme sind das <a href="https://www.fiafnet.org/pages/e-resources/cataloguing-manual.html" class="external-link" target="_blank">FIAF Cataloguing Rules & Moving Image Cataloguing Manual</a> sowie die beiden Metadatenstandards <a href="https://filmstandards.org/fsc/index.php/EN_15744" class="external-link" target="_blank">EN 15744</a> und <a href="https://filmstandards.org/fsc/index.php?title=EN_15907" class="external-link" target="_blank">EN 15907</a>. Ziel der Standardisierung ist es, den Austausch von filmographischen Informationen zu fördern und einen normierten Datenaustausch zwischen Institutionen, aber auch Nutzenden zu ermöglichen.

## EN 15744 & EN 15907

````{margin}
```{admonition} Dublin Core
:class: hinweis
Mehr Informationen zum **Dublin Core** Metadatenstandard gibt es im Kapitel [Allgemeine Metadatenstandards](../03_metadaten/allgemeine_standards.md).
```
````

**EN 15744** und **EN 15907** sind europäische Standards zur Identifikation von Filmwerken (Cinematic Work Standards, kurz: **CWS**). Sie definieren ein Set an Metadatenelementen, um Filme und andere Bewegtbildmedien, ihre Fassungen und Träger (physisch/digital) zu identifizieren und katalogisieren. Der EN 15744-Standard ist ein Minimalstandard für Filmwerke. Er besteht aus einem Datenset mit 15 Elementen in einer flachen Struktur und ist vergleichbar mit dem <a href="https://www.dublincore.org/" class="external-link" target="_blank">Dublin Core</a>.

````{margin}
➡️ Zum Vergrößern bitte draufklicken!
````


```{figure} ../assets/03_metadaten/abb_k03_en_15744.png
---
align: center
width: 100%
name: en-15744
---
Die 15 Elemente des EN 15744 und ihre Beschreibungen, © <a href="https://filmstandards.org/fsc/index.php?title=Main_Page" class="external-link" target="_blank">filmstandards.org</a>
```

Der EN 15907-Standard ist im Gegensatz zum 15744 wesentlich komplexer. Er besteht aus relationalen und hierarchischen Strukturen und ist besonders geeignet, um den Lebenszyklus eines Films abzubilden. Das Schema wird durch fünf primäre Entitäten (Cinematographic Work, Variant, Manifestation, Item, Content) und zwei sekundäre Entitäten (Agent, Event) strukturiert. Detaillierte Informationen zu den einzelnen Beschreibungen der Entitäten und Elemente finden sich auf der <a href="https://filmstandards.org/fsc/index.php?title=EN_15907" class="external-link" target="_blank">Filmstandards-Website</a>.

```{figure} ../assets/03_metadaten/abb_k03_en_15907.png
---
align: center
width: 70%
name: en-15907
---
Datenmodell und Elementstruktur des EN 15907
```
```{admonition} Persistente Identifikatoren
:class: important
Für eine klare Identifizierung filmischer Werke sind [persistente Identifikatoren](../06_publikation_repositorien/versionierung_lizenzierung.md) notwendig. Die EN-Standards definieren das Feld `identifier` folgendermaßen: 
> "An unambiguous reference to the resource within a given context, where possible the International Standard Audio-visual Number (ISAN), otherwise a specific number issued by a government department, or other official body in an individual country, or an archive’s inventory number."
```
```{admonition} Exkurs: Werk – Variante – Manifestation – Exemplar
:class: hinweis
Die vier Begriffe `Werk`, `Variante`, `Manifestation` und `Exemplar` stammen aus dem <a href="https://repository.ifla.org/items/ffb50f46-46ab-4ec4-8970-b00e2b0d2811" class="external-link" target="_blank">FRBR-Modell </a> (Functional Requirements for Bibliographic Records) und wurden für die Filmarchivierung im EN 15907-Standard übernommen. Sie ermöglichen Filmarchiven, Kinematheken und Mediatheken die komplexen und mehrschichtigen Ebenen zwischen dem künstlerischen bzw. schöpferischen Idee (Werk), seinen verschiedenen inhaltlichen Fassungen (Variante), den technischen Ausgabeformaten (Manifestation) und physischen und digitalen Kopien (Exemplar) zu erfassen.

**Beispiel**:

`Werk`: *Metropolis* von Fritz Lang als das künstlerische Konzept <br>
`Variante`: Kurzfassung von Metropolis (1927, 115 Min.) oder restaurierte Langfassung (2010, 148 Min.) <br>
`Manifestation`: 35mm-Filmkopie oder DVD-Ausgabe <br>
`Exemplar`: Deutsche Kinemathek DVD/Blu Ray DVD375, Barcode: <a href="https://deutsche-kinemathek.bsz-bw.de/cgi-bin/koha/opac-detail.pl?biblionumber=81474" class="external-link" target="_blank">00298186</a>
```

Für kleinere filmwissenschaftliche Projekte mit überschaubaren Korpora kann eine Orientierung am Minimalstandard bereits ausreichen. Für archivarische und filmhistorische Arbeiten kann eine Ausrichtung am EN 15907 – je nach Forschungsgegenstand und Frage – sinnvoll sein. 

## FIAF 

Die <a href="https://www.fiafnet.org/" class="external-link" target="_blank">FIAF</a> (International Federation of Film Archives) hat umfassende Katalogisierungsregeln aufgestellt und diese als <a href="https://www.fiafnet.org/pages/e-resources/cataloguing-manual.html" class="external-link" target="_blank">Manual</a> in verschiedenen Sprachen zur Verfügung gestellt. Die Regeln orientieren sich dabei explizit am FBRB-Modell und den EN-Standards zur Erschließung von Filmwerken und sind insbesondere in vielen Filmarchiven die praktische Arbeitsgrundlage. 

````{margin}
➡️ Zum Vergrößern bitte draufklicken!
````

```{figure} ../assets/03_metadaten/abb_k03_fiaf_schema_02.png
---
align: center
width: 100%
name: fiaf-schema
---
Beispiel einer Katalogisierungsstruktur des FIAF-Schemas
```
Für forschungsorientierte Projekte ist das Manual ein guter Referenzrahmen, um filmographische Angaben zu strukturieren und zu definieren.

```{admonition} Filmbezogene Materialien
:class: seealso
Für sogenannte "film related materials" (z. B. Poster, PR Material, Stills) hat die FIAF ebenfalls <a href="https://fiaf.github.io/film-related-materials/" class="external-link" target="_blank">Best Practices</a> zusammengestellt.
```

## Praxisbeispiel: DFFB-Archiv 

Oftmals werden die CWS-Standards in die internen Archiv- oder Bibliotheksinfrastrukturen implementiert. Sie bilden also im “Hintergrund” relationale Strukturen und ordnen Werke, Begriffe, Schlagworte usw. in die systemeigene technische Umgebung ein. 
Sichtbar wird dies in der Art und Weise der Aufteilung der verschiedenen Metadatenelemente, wie das konkrete Anschauungsbeispiel des <a href="https://dffb-archiv.de/dffb/fremde-tage" class="external-link" target="_blank">DFFB-Archiv-Eintrags</a> zum Film *Fremde Tage* (R: Ernst Martin Schlüter, BRD 1985) zeigt.

```{figure} ../assets/03_metadaten/abb_k03_archiv_dffb.png
---
align: center
width: 100%
name: archiv-dffb
---
Archiveintrag und filmographische Angaben zum Film *Fremde Tage* von Ernst Martin Schlüter
```

Die Aufteilung der Elemente erfolgt in der Unterscheidung auf:
* Werk 
* Titelvarianten
* Credits
* Quelle
* Technischen Angaben (Drehformat, Seitenverhältnis, Farbe)
* Verschlagwortung
* Kategorien

Die hier sichtbare Trennung von Werksebene (Titel, Regie), inhaltlichen Angaben, institutionellen Rollen und technischen Manifestationsdaten ist typisch für eine CWS-orientierte Modellierung. 
Während solche Modellierungen jedoch vor allem auf **offenen und zugänglichen Datenaustausch**, **Interoperabilität** sowie auf **Referenzierbarkeit** von Daten zielen, bleiben ihre historischen Entstehungskontexte, normativen Annahmen und Begriffsbestimmungen häufig unsichtbar:
> "Metadata standards are essential in all disciplines. But they are often highly
contested and even controversial because they embody value judgments
either implicitly or explicitly."

Für wen bleiben die Standards anschlussfähig? Und auf welcher Grundlage können kritische Perspektiven mitgedacht werden? Im nächsten Kapitel befassen wir uns daher mit der Frage nach diskriminierungssensiblen Metadaten.

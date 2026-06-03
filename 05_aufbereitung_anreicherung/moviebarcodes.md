# Annotationsdaten anreichern: Moviebarcodes

## Was sind Moviebarcodes?

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_mb_e158p_0.png
:name: moviebarcode planet earth

Moviebarcode aus der Naturdokuserie *Planet Earth: The Future*, Staffel 1/Episode 3: *Living Together*
```

Moviebarcodes sind visuelle Abstraktionen von Bewegtbildmaterial, die Farb- und Helligkeitsverläufe eines Films oder Filmsegments über seine gesamte Laufzeit hinweg darstellen. Sie verdichten die zeitliche Struktur eines audiovisuellen Werks zu einem einzigen, statischen Bild: Die horizontale Achse bildet dabei den zeitlichen Verlauf von links nach rechts ab, während die vertikale Achse die Verteilung von Farb- und Helligkeitswerten im Bildraum repräsentiert. Auf diese Weise machen Moviebarcodes formale Eigenschaften von Filmen sichtbar, ohne auf narrative Inhalte oder konkrete Bildmotive angewiesen zu sein.

## Moviebarcodes in der Filmwissenschaft

In der filmwissenschaftlichen Analyse können Moviebarcodes auf unterschiedliche Weise eingesetzt werden. Auf der makroanalytischen Ebene fungieren sie als visuelle “Fingerabdrücke” von Filmen, die es erlauben, stilistische Merkmale wie dominante Farben, Kontraste oder Helligkeitsverläufe zu erfassen. 
Darüber hinaus eignen sich Moviebarcodes ebenso als Werkzeug für die Analyse zeitlicher Dynamiken innerhalb einzelner Werke. Anhand der visuellen Zeitleiste lassen sich Rhythmusverläufe, Wiederholungsstrukturen sowie graduelle Veränderungen auf der Ebene von Farbe, Licht aber auch in Bezug auf das Verhältnis von Kadrierung und ästhetischer Gestaltung auf einen Blick erfassen. 

Neben der analytischen Auseinandersetzung mit einzelnen Filmen ermöglichen Moviebarcodes ferner auch eine einfache Methode des Vergleichs einer Vielzahl von Filmen auf einem hohen Abstraktionsniveau - etwa nach Genres, Enstehungszeiträumen oder stilistischen bzw. formal-ästhetischen Tendenzen. 

Nicht zuletzt sind Moviebarcodes wichtige wissenschaftliche Argumentationsstützen und können zur Illustration und Darstellung von Hypothesen und Beobachtungen genutzt werden. Dabei können sie qualitative Analysen unterstützen, die die audiovisuelle Inszenierung, also die konkrete zeitliche Anordnung von Bild und Ton, als formale und ästhetische Grundlage von Wahrnehmung, Bedeutungskonstitution und affektivem Erleben im Film verstehen. In diesem Sinne sind Moviebarcodes nicht allein als Werkzeuge zu verstehen, sie sind Teil von Forschungsergebnissen, durch die Affektstrukturen und Bilddramaturgien aus der zeitlichen Organisation der Filme selbst verständlich gemacht werden können. 

## Technische Einordnung

Die Erstellung eines Moviebarcodes erfolgt in mehreren klar definierten Schritten. Zunächst werden aus einem Video in regelmäßigen Abständen Einzelbilder (Frames) extrahiert. Jedes dieser Bilder wird anschließend auf die Breite eines einzigen Pixels reduziert, wodurch die Farb- und Helligkeitswerte bzw. die visuellen Informationen in eine räumliche Dimension verdichtet werden. Die erzeugten Pixelstreifen werden schließlich entsprechend ihrer zeitlichen Position von links nach rechts zu einem Gesamtbild zusammengesetzt, das die temporale Struktur des Films abstrahiert und visuell abbildet. 

Für die Erstellung der Movierbarcodes wurden die frei verfügbaren und quelloffenen Werkzeuge <a href="https://www.ffmpeg.org/" class="external-link" target="_blank">ffmpeg</a> und <a href="https://imagemagick.org/#gsc.tab=0" class="external-link" target="_blank">ImageMagick</a> verwendet. Andere Methoden oder Tools sind grundsätzlich möglich, können aber ggf. zu leicht abweichenden Ergebnissen führen. Der Ansatz wurde gewählt, um die Schritte zur Extrahierung der Farbwerte reproduzierbar, methodisch nachvollziehbar und technisch transparent zu halten. Detaillierte Anleitungen zum Workflow sowie begleitende Tutorials finden sich im Kapitel xxx.

## Rechtliche Einordnung

Um eine reibungslose Veröffentlichung der Moviebarcodes zu gewährleisten, ist es wichtig, eine rechtliche Einordnung vorzunehmen. Denn die Frage, ob Moviebarcodes als eine urheberrechtliche relevante "Bearbeitung" im Sinne eines abgeleiteten Werks ("derivative work") einzustufen sind, wurde im Rahmen des SFB-Projekts unverbindlich durch den <a href="https://nfdi4culture.de/de/dienste/details/nfdi4culture-helpdesk.html" class="external-link" target="_blank">NFDI4Culture Legal Helpdesk</a> juristisch bewertet.

```{admonition} Jursitische Bewertung
:class: important
Diese Einordnung basiert auf der unverbindlichen Einschätzung des NFDI4Culture Legal Helpdesk, ersetzt aber keineswegs eine gesicherte Auskunft oder Rechtsberatung eines Justitiariats oder Kanzlei. Für verbindliche rechtliche Auskünfte wird die Einholung professioneller juristischer Beratung empfohlen.
```

Moviebarcodes stellen nach § 3 und § 23 UrhG keine Bearbeitung des Ausgangswerks dar, da ihre Generierung nicht schöpferischer, sondern analytischer Natur ist. Der Prozess der Farbaggregation – sprich die Berechnung und Kompression von Farbwerten aus einzelnen Frames – ist als ein deskriptiv-quantitativer Prozess zu bewerten, aus dem keine kreativen Entscheidungen in Bezug auf das Ursprungswerk abgeleitet werden können. 

Diese Einschätzung wird durch mehrere charakteristische Merkmale der Moviebarcodes untersützt:
* Es sind keine Szenen, Figuren oder Bildkompositionen erkennbar
* Narrative Strukturen sind nicht rekonstruierbar
* Es besteht kein visueller Wiedererkennungswert zum Originalfilm
* Es liegt keine wirtschaftliche Konkurrenz zum Originalwerk vor

Ergänzend sei darauf verwiesen, dass § 60d UrhG Text- und Data Mining zu wissenschaftlichen Zwecken ausdrücklich erlaubt.

Da Moviebarcodes keinen Werkcharakter im urheberrechtlichen Sinne aufweisen, sind sie auch nicht lizenzierungspflichtig. Dies bedeutet streng genommen, dass es keine explizite Lizenz geben muss. Wie die konkrete Lizenzierung für Moviebarcodes aussehen kann, wird im Kapitel Lizenzierung [TODO: Verlinkung] besprochen.

## Moviebarcodes selbst erstellen: Guides

Nachfolgend haben wir Code-Guides erstellt, die Schritt für Schritt den Prozess der Erzeugung von Moviebarcodes aus einer Filmdatei dokumentieren und selbstständig reproduziert werden können. Die Guides sind hier in der deutschen Version für Windows, MacOS und Linux verfügbar. Die englischen Versionen sind in der 
Dokumentation des <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset/tree/main/documentation/moviebarcodes_documentation" class="external-link" target="_blank">Projektrepositorys </a> hinterlegt. 

1. [Windows](../assets/05_aufbereitung_anreicherung/doc_windows_moviebarcode_guide_v001.md)
2. [Linux](../assets/05_aufbereitung_anreicherung/doc_linux_moviebarcode_guide_v001.md)
3. [MacOS](../assets/05_aufbereitung_anreicherung/doc_mac_moviebarcode_guide_v001.md)

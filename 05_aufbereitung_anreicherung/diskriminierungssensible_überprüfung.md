# Diskriminierungssensible Überprüfung 

```{admonition} Hinweis: Vorwissen und Kontext
:class: hinweis
Die Inhalte dieses Kapitels bauen auf dem Abschnitt [Diskriminierungssensible Metadaten](../03_metadaten/diskriminierungssensible_metadaten.md) des dritten Lernmoduls auf. Dort finden sich die theoretischen Grundlagen, Fallbeispiele und Methoden einer diskriminierungssensiblen Metadatenpraxis.
```

Die folgenden Überprüfungen wurden exemplarisch anhand ausgewählter Leitfragen aus dem im Kapitel Diskriminierungssensible Metadaten vorgestellten {ref}`Fragenkatalog <fragenkatalog-metadaten>` durchgeführt. Sie erheben keinen Anspruch auf Vollständigkeit, sondern dokumentieren mögliche Ansätze, um kritische Perspektiven in die eigene Datenpraxis zu integrieren.

## Vorbereitungen: Datenbereinigung

Da die Produktionen unabhängig von ihrem Umfang ausgewertet wurden, wurden Serien zunächst auf eine Episode pro Serie reduziert. Diese Entscheidung sollte je nach Kontext getroffen werden. Bei Serien, deren Produktionsteam und -land episodisch wechselt, kann ein anderer Umgang sinnvoll sein. Nach der Bereinigung umfasst die Grundlage der Auswertung **87 Produktionen**.

## Geografische Situiertheit: Auswertung nach Produktionsländern

Der Korpus enthält Produktionen aus 29 unterschiedlichen Ländern. Bei der Auswertung fällt ein deutliches Übergewicht nordamerikanischer sowie mittel- und westeuropäischer Produktionen auf: 49 Produktionen sind US-amerikanisch (56,32 %), 26 britisch (29,89 %) und 17 deutsch (19,54 %). Osteuropäische Produktionen sind mit insgesamt 4 (4,6 %) vertreten (2 aus Griechenland, je eine aus Litauen und der Ukraine). Die am stärksten repräsentierten nicht-europäischen und nicht-nordamerikanischen Länder sind Australien, Japan und China mit je 4 Produktionen (4,6 %). Dies entspricht zwei Drittel aller nicht-europäischen und nicht-nordamerikanischen Produktionen. Aus Afrika stammen lediglich 2 Produktionen (Nigeria und Südafrika; 2,3 %). Produktionen aus Mittel- und Südamerika sowie Südostasien sind im Korpus nicht vorhanden. Der Gesamtanteil nicht-europäischer und nicht-nordamerikanischer Produktionen beträgt 18 (20,69 %).

Bei diesen Daten wurden die einzelnen Episoden der gleichen Serie oder Reihe als ein Element zusammengefasst. Unbereinigt zeigt sich diese Tendenz noch deutlicher, so stammen 142 von 226 Elemente aus Großbritannien (62,83 %), 131 aus den USA (57,96 %) und 56 aus Deutschland (24,78 %). 

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_laender_absolut.png
---
align: center
width: 95%
name: laender-absolut
---
Korpusdaten nach Ländern (absolut), Landeskürzel nach ISO 3166
```


```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_laender_anteilig.png
---
align: center
width: 95%
name: laender-anteilig
---
Korpusdaten nach Ländern (anteilig, Treemap-Darstellung)
```

### Berechnung der Länderauswertung

Die Spalte `country` der Korpusmetadaten wurde in ein Textprogramm kopiert. Mithilfe von `Strg + F` (Mac: `Command + F`) lässt sich nach dem jeweiligen Landeskürzel suchen, um die Trefferzahl im Datensatz zu ermitteln (z.B. ergibt DE 17 Treffer). Nach der Erfassung eines Länderkürzels können die gefundenen Treffer durch ein Leerzeichen ersetzt werden.Dadurch wird die Übersicht verbessert und bereits ausgewertete Kürzel werden bei der weiteren manuellen Auswertung nicht erneut berücksichtigt.

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_berechnung_laender_textprogramm.png
---
align: center
width: 100%
name: berechnung-laender-textprogramm
---
Suche nach Länderkürzel im Textprogramm (Beispiel: DE, 17 Treffer)
```

Der prozentuale Anteil ergibt sich aus: absolutes Vorkommen ÷ Gesamtzahl der Produktionen. 

Beispielberechnung:

$\frac{17}{87}=0{,}1954=19{,}54\,\%$

Zur besseren Übersicht empfiehlt es sich, die Ergebnisse in einer Tabelle zu erfassen und auf- oder absteigend zu sortieren. Bei größeren Korpora können zusätzliche Spalten sinnvoll sein, um Länder nach geografischer Lage zu gruppieren. Im vorliegenden Fall war der Korpus klein genug für eine manuelle Organisation.

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_berechnung_laender_tabelle.png
---
align: center
width: 25%
name: berechnung-laender-tabelle
---
Ergebnistabelle: Länder und absolute Vorkommen im Korpus
```

```{admonition} Keypoint: Methodische Einordnung und Schwerpunktsetzung
:class: keypoint
Diese geographische Schwerpunktsetzung ist keine zufällige, sondern eine forschungsstrategische Entscheidung. Denn das Teilprojekt untersucht spezifische Logismen und Traditionen des Anthropozentrismus in westlichen filmischen Auseinandersetzungen zum Klimawandel. Eurozentristische Perspektiven und die strukturelle Dominanz westlicher Klimanarrative und ihrer ästhetischen Strategien sind dabei selbst Gegenstand der Analyse und stellen somit nicht einfach blinde Flecken der Korpuszusammenstellung dar. 
Die Frage, wie marginalisierte Perspektiven (jenseits westlicher Blickregime) filmisch zum Ausdruck kommen und ob bzw. inwiefern sich die Imaginationen des menschlichen Zur-Welt-Seins in der Klimakrise hinsichtlich affektiver sowie formal-ästhetischer Gestaltungsformen in der Zirkulation medialer Bewegtbilder unterscheidet, kann und sollte Ausgangspunkt weiterer Untersuchungen sein (z.B. mit Schwerpunkt auf indigene Formen der Wissens- und Bildproduktion).
```

## Auswertung nach Geschlecht (Regie)

Von 89 regieführenden Personen können 74 als männlich gelesen (83,15 %) und 15 als weiblich gelesen werden (16,85 %). Offene Transpersonen oder nicht-binäre Regisseur:innen bildet der Korpus nicht ab. Aus einer intersektionalen Perspektive ist zudem anzumerken, dass keine der regieführenden Frauen an einer nicht-westlichen Produktion beteiligt war.

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_geschlecht_prozent.png
---
align: center
width: 35%
name: geschlecht-prozent
---
Anteile am Korpus nach Geschlecht (Regie), prozentual
```

### Berechnung der Geschlecht-Auswertung

Zur Auswertung wurde die Metadatentabelle um eine Spalte `Geschlecht` ergänzt, in der das Geschlecht der regieführenden Personen mit einem Kürzel (`m`/`w`) vermerkt wurde. Bei einem weniger binärgeschlechtlichen Korpus sollte die Art der Notation vorab überlegt werden: Werden nicht-binäre Geschlechter kollektiv als "nicht-binär" gelistet? Werden Transpersonen zusätzlich als weiblich/männlich geführt?[^1]

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_geschlecht_tabelle.png
---
align: center
width: 35%
name: geschlecht-tabelle
---
Metadatentabelle mit ergänzter Spalte "Geschlecht"
```

Anders als bei den Ländern wurde der Anteil auf die Gesamtzahl der regieführenden *Personen* (89) bezogen, nicht auf die Produktionen, da einzelne Produktionen mehrere Regisseur:innen haben und manche Personen mehrfach im Korpus vertreten sind.

Beispielberechnung:

$\frac{74}{89}=0{,}8315=83{,}15\,\%$

```{admonition} Hinweis: Queerness in Metadaten
:class: hinweis
Offene Transpersonen, nicht-binäre und queere Personen durch Metadatenangaben zu erkennen, erfordert eine gewisse Vertrautheit mit den Primärdaten, was bei großen Korpora nicht immer gegeben ist. Hilfreiche Ressourcen sind queere Filmdatenbanken, etwa:

* <a href="https://transonscreen.com/" class="external-link" target="_blank">Trans on Screen</a>
* <a href="https://www.imdb.com/de/list/ls093528455/" class="external-link" target="_blank">IMDb-Liste: LGBTQ+ Directors</a>
* <a href="https://www.imdb.com/de/list/ls089816632/" class="external-link" target="_blank">IMDb-Liste: Queer Directors</a>
* <a href="https://queerfilmreviews.com/database/films/" class="external-link" target="_blank">Queer Film Reviews Database</a>

Da alle Datenbanken einen spezifischen Fokus setzen, sollten sie je nach Korpus ausgewählt oder ergänzend genutzt werden. Im vorliegenden Korpus findet sich **keine** der regieführenden Personen in einer dieser Datenbanken wieder.
```

Die Zahlen werfen eine weiterführende Frage auf, die die punktuelle Auswertung der Korpusmetaten übersteigt: Inwieweit bringt die Überrepräsentation männlich gelesener Regie nicht nur eine Eigenheit dieser Zusammenstellung zum Ausdruck, sondern eine strukturelle Tendenz in der filmischen Auseinandersetzung mit dem Klimawandel insgesamt? Und welche Konsequenzen hätte das für die Konstitution der Klimakrise als ästhetische Erfahrung – also ihrer Bildsprache, Narration und affektiven Adressierung – wenn diese überwiegend durch männlich kodierte Blickregime und Erzählpositionen geprägt wäre? 

Diese Fragen lassen sich auf Grundlage der vorliegenden Metadaten zwar nicht abschließend beantworten, sind aber als Impulse für weitere kritische Überlegungen und qualitative Analysen festzuhalten.

## Zeitliche Situiertheit 

Der Korpus hat einen Fokus auf gegenwärtige bzw. zeitgenössische Produktionen: Nur 4 der 87 Produktionen stammen aus dem 20. Jahrhundert, die älteste aus dem Jahr 1979. Die aktuellsten Produktionen sind auf 2023 datiert (3 Produktionen). 61 der 87 Produktionen (70,11 %) sind nach 2010 erschienen. **Diese zeitliche Ausrichtung lässt sich der Aktualität und zunehmenden medialen Relevanz des Themas rund um die Klimakrise zuschreiben**. Zur Auswertung kann die Spalte `year` in den Korpusmetadaten auf- oder absteigend sortiert werden; wie präzise die Zeiträume gruppiert werden, sollte von der 
Zeitspanne des Korpus abhängig gemacht werden.

## Visualisierung

Nach der Auswertung können die Daten in Grafiken oder Diagrammen aufbereitet werden. Dazu eignen sich Excel (PivotCharts oder Diagramme) sowie andere Programme wie <a href="https://www.canva.com/" class="external-link" target="_blank">Canva</a>. Für die vorliegenden Darstellungen wurde Canva benutzt.

In beiden Programmen wird zunächst eine einfache Tabelle mit zwei Spalten angelegt: eine Spalte für die Kategorien (z.B. Länderkürzel nach ISO 3166) und eine für die zugehörigen Werte (absolute Vorkommen). Diese Tabelle bildet die Grundlage für das Diagramm.



[^1]: Die hier verwendete Kategorie Geschlecht dient ausschließlich der exemplarischen Auswertung der Korpusmetadaten und stellt ausdrücklich keine gegebene Klassifikation dar. "Geschlecht" wird in den Gender Studies vielmehr als sozial und kulturell hervorgebrachte sowie historisch wandelbare Kategorie verstanden (vgl. hierzu: Simone de Beauvoir 1949; Judith Butler 1990). Die im Projekt verwendete binäre Codierung (m/w) geht aus der Verfügbarkeit der erhobenen Metadaten hervor und erhebt keinen normativen Anspruch. Je nach Forschungsfrage und Korpus kann eine differenziertere Erfassung erforderlich und methodisch angemessener sein.
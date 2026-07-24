# Resümee

```{admonition} Keypoints: Moviebarcodes
:class: keypoint

* Moviebarcodes verdichten Farb- und Helligkeitsverläufe eines Films oder Filmsegments zu einer statischen Visualisierung, die den zeitlichen Ablauf und die Farbdramaturgie erfasst.
* In der filmwissenschaftlichen Analyse können Moviebarcodes stilistische Merkmale, Rhythmusverläufe, Wiederholungen und graduelle Veränderungen sichtbar machen sowie den Vergleich mehrerer Werke ermöglichen.
* Ihre technische Erstellung basiert auf der regelmäßigen Extraktion von Frames, der Reduktion jedes Einzelbilds auf einen Pixelstreifen und der zeitlichen Zusammensetzung zu einem Gesamtbild.
```

```{admonition} Keypoints: Systematische Aufbereitung von Forschungsdaten
:class: keypoint

* Die systematische Aufbereitung eines Datensatzes erfordert ein konsistentes Metadatenschema, das projektspezifische Anforderungen mit etablierten allgemeinen sowie fachspezifischen Standards wie beispielsweise Dublin Core und EN 15744 verbindet.
* Eindeutige interne und externe Identifier gewährleisten die stabile Zuordnung, Referenzierbarkeit und relationale Verknüpfung von audiovisuellen Ressourcen und weiteren Forschungsdaten (z.B Annotationsdaten, Moviebarcodes).
* Kontrollierte Vokabulare, ISO-Standards und verbindliche Formatregeln reduzieren Inkonsistenzen und erhöhen Maschinenlesbarkeit, Interoperabilität und Auswertbarkeit der Daten.
* Die `object_id` fungiert als zentraler Primärschlüssel, über den die verschiedenen Bestandteile des Datensets miteinander verknüpft werden.
* Ein maschinenlesbares Metadatenschema im `yaml`-Format dokumentiert Felder, Datentypen, Mappings, Vokabulare und Validierungsregeln und kann als anpassbare Vorlage für andere Projekte nachgenutzt werden.
```

```{admonition} Keypoints: Formate und Konvertierung
:class: keypoint

* Für die Publikation und Langzeitarchivierung sollten Forschungsdaten möglichst in offenen, nicht-proprietären, maschinenlesbaren und interoperablen Formaten bereitgestellt werden.
* Unterschiedliche Formate erfüllen unterschiedliche Funktionen: `xlsx` eignet sich als Arbeitsformat, `csv` für tabellarischen Datenaustausch, `json` für strukturierte und maschinenlesbare Daten sowie `html` für eine browserbasierte, nutzerfreundliche Durchsuchbarkeit.
* Bei Formatkonvertierungen müssen Zeichencodierung, Trennzeichen, leere Felder, Spaltennamen und Datentypen kontrolliert werden, um Struktur- und Informationsverluste zu vermeiden.
* Die parallele Veröffentlichung des ursprünglichen Arbeitsformats und offener Exportformate erhöht Nachvollziehbarkeit, Zugänglichkeit und langfristige Nachnutzbarkeit.
* Automatisierte Workflows mit (z. B. `html`-Skript und Python) ermöglichen reproduzierbare Exporte und anpassbare Darstellungsformen für eigene Forschungsdatensätze.
```

```{admonition} Keypoints:  Datenbereinigung und Dokumentation
:class: keypoint

* Datenbereinigung umfasst die Vereinheitlichung von Strukturen, Schreibweisen, Feldnamen, Trennzeichen, Identifikatoren und kontrollierten Vokabularen, damit Datensätze konsistent und maschinenlesbar vorliegen.
* Ein maschinenlesbares `yaml`-Schema kann als Regelwerk dienen, um Pflichtfelder, Muster und zulässige Werte automatisiert gegen eine `csv`-Datei zu prüfen.
    * Ein Python-basiertes Validierungsverfahren identifiziert Abweichungen und dokumentiert sie in einem nachvollziehbaren Validation Report.
* Offene Dokumentationsformate im Markdown-Format wie z. B. `README`-Dateien erläutern Herkunft, Struktur, Methoden, Formate, Lizenzen und Zitationshinweise eines Datensatzes.
```

```{admonition} Keypoints: Diskriminierungssensible Überprüfung 
:class: keypoint

* Eine diskriminierungssensible Überprüfung kann strukturelle Schwerpunkte und Ausschlüsse eines Korpus sichtbar machen, etwa hinsichtlich geografischer Herkunft, Geschlecht, zeitlicher Situiertheit und verwendeter Datenquellen.
* Quantitative Auswertungen von Metadaten können Verhältnisse und Ungleichgewichte als Tendenzen sichtbar machen, müssen jedoch im jeweiligen Forschungsdesign und Entstehungskontext des Korpus interpretiert werden.
* Kategorien wie `country` oder `director` sowie externe Standards und Datenbanken sind nicht neutral, sondern beruhen auf politischen, institutionellen und produktionsästhetischen Hierarchien und historischen Machtgefügen.
* Für die Überprüfung sollten sowohl eigene Metadaten als auch nachgenutzte Begriffe, Normdaten, Vokabulare und externe Quellen auf diskriminierende Sprache, Narrative und Ausschlüsse untersucht werden.
* Quantitative (Meta-)Datenanalysen können Ansatzpunkte für weiterführende qualitative Untersuchungen liefern, erlauben für sich genommen jedoch keine analytisch fundierten Aussagen über konkrete ästhetische, narrative oder ideologische Darstellungsweisen der Werke selbst.
```


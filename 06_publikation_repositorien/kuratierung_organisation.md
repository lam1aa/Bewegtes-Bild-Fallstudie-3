# Kuratierung & Organisation

```{admonition} Story
:class: story
Das filmwissenschaftliche Teilprojekt der FU Berlin hat sich nun alle wichtigen Grundlagen zur [Versionierung, Lizenzierung und Zitierfähigkeit](./versionierung_lizenzierung.md) angeschaut und die wichtigen Durchführungsschritte dazu eingeleitet. 
Doch bevor das Datenset und alle notwendigen Dateien tatsächlich in das Repository auf GitHub hochgeladen werden können, fehlt noch ein häufig vernachlässigter Bestandteil der Arbeit mit Forschungsdaten: Das Aufräumen und Organisieren der Daten. Im Projektalltag sind Daten und Dateien häufig lokal oder auf verschiedenen Clouddiensten gleichzeitig verstreut, unterschiedlich benannt und in inkonsistenten Ordnerstrukturen abgelegt. Vor der Veröffentlichung müssen sie also kuratiert, vereinheitlicht und publikationsreif strukturiert werden. Die wichtigsten Schritte hierzu werden in den nachfolgenden Abschnitten behandelt.
```

## Ordnerstrukturen

Eine durchdachte Ordnerstruktur bildet die Basis eines nachnutzbaren Datensets. Sie erleichtert dabei nicht nur den eigenen Arbeitsprozess, sondern sorgt dafür, dass externe Nutzer:innen die publizierten Daten erschließen können. Grundsätzlich gilt: Eine Ordnerstruktur ist dann gut, wenn sie einer außenstehenden Person deutlich macht, wo welche Daten zu finden sind und wie sie zusammenhängen.

### Richtlinien für Ordnerstrukturen


Die folgenden Empfehlungen haben sich nach dem <a href="https://www.konsortswd.de/ueber-uns/" class="external-link" target="_blank">Rat für Sozial- und Wirtschaftsdaten</a> sowie dem <a href="https://www.forschungsdaten-bildung.de/" class="external-link" target="_blank">Verbund Forschungsdaten Bildung</a> als Best Practice etabliert:

* Die Struktur ist **hierarchisch** gegliedert und umfasst **maximal drei Unterordner-Ebenen**
* Die Benennung ist **klar, konsistent und selbsterklärend**
* Eine {ref}`README-Datei <dokumentation>` im Wurzelverzeichnis dokumentiert die Struktur und ihre Logik
* In Projekten mit mehreren Beteiligten werden **Verantwortlichkeiten** festgelegt: Wer darf neue Ordner anlegen? Wer verwaltet den Zugriff?

Weitere Dokumentationsdateien – zum Beispiel zu einer bestimmten Methode eines konkretes Datentyps – können den jeweiligen zugehörigen Ordnern beigelegt werden.

### Beispiel: Repository-Ablage des Projektdatensatzes


Für die Publikation auf GitHub hat das Projekt eine Ordnerstruktur entwickelt, die die unterschiedlichen Datentypen klar voneinander trennt. Das folgende Baumdiagramm zeigt die Ablagestruktur und kann als Orientierung für das eigene Projekt dienen. Die Ablage kann ebenso direkt in dem Projektrepository <a href="https://github.com/SFB1512-C05-climate-film/intervening-world-projections-dataset" class="external-link" target="_blank">"Intervening World Projections: Audiovisuality of Climate Change"</a> eingesehen werden.

```text
intervening-world-projections-dataset/ # Rootverzeichnis
│
├── assets/                  # Visualisierungen und weitere Ressourcen
├── data/                    # Forschungsdaten
│   ├── annotations/         # Annotationsdaten (azp, json)
│   │   ├── f001a.azp
│   │   ├── f001a.json
│   │   └── ...
│   ├── moviebarcodes/       # Visualisierungen (png)
│   │   ├── f001a_barcode.png
│   │   └── ...
│   └── metadata/            # Korpusmetadaten (xlsx, csv, html, json)
│
├── documentation/           # Dokumentationen, Tutorials und Guidelines
├── schema/                  # corpus-metadata-schema.yml
│
├── .gitignore               # Von Git ignorierte Dateien
├── CITATION.cff             # Zitationshinweis
├── LICENSE.md               # Lizenzierung des Datensets
└── README.md                # Zentrale Dokumentationsdatei des Repositoriums
```

In dieser Struktur werden Forschungsdaten (`data/`), Dokumentationsdateien (`documentation/`), das projekteigene 
{ref}`YAML-Schema <yaml-schema>`, sowie projektweite Dateien (LICENSE, CITATION) voneinander getrennt.  Innerhalb von `data/` sind die drei Datentypen – Annotationen, Moviebarcodes und Metadaten – in eigenen Unterordnern organisiert.

Desweiteren ist es ratsam, Ordner (hier: `assets/`) für Bilder oder Visualisierungen anzulegen, die für Erklärungs- und Veranschaulichungszwecke genutzt werden aber nicht Teil des Datensets sind. 

## Dateibenennung

Neben der Ordnerstruktur ist ein konsistentes **Dateibenennungssystem** entscheidend dafür, dass Dateien auffindbar, maschinell verarbeitbar und für Dritte verständlich sind. In Projekten, an denen mehrere Personen beteiligt sind, entstehen ohne klare Regeln schnell Benennungschaos und Versionskonflikte.











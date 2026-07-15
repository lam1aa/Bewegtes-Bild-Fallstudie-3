---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---


# 🏆Selbsttest: Wissen und Praxis

````{admonition} Wie nutze ich den Selbsttest?
:class: hinweis, dropdown
Dieser Selbsttest verzichtet bewusst auf reine Wissensabfragen. Stattdessen werden Ihnen Situationen und Fallbeispiele präsentiert, die Sie mithilfe der im Kapitel erlernten Konzepte durchdenken und einordnen sollen. Es geht darum, Prinzipien auf neue Konstellationen zu übertragen – nicht darum, Textpassagen wiederzuerkennen.

Die Aufgaben sind in drei Schwierigkeitsstufen gegliedert: **Einsteiger:in**, **Fortgeschritten** und **Vertiefung**.

**So funktioniert es:**
- Lesen Sie jede Situation sorgfältig und überlegen Sie, welches Prinzip hier zum Tragen kommt
- Wählen Sie die Antwort(en), die Sie für richtig halten
- Nutzen Sie das Feedback, um Ihre Argumentation zu überprüfen - auch bei richtigen Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse.

**Geschätzte Zeit**: XX Minuten

Viel Erfolg!
````

## Aufgabe 1

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice1 = [{
    "question": """Eine Doktorandin lädt am Ende ihres Projekts lediglich die reine CSV-Tabelle ihrer Filmkorpusdaten auf einen privaten Cloud-Speicher hoch und teilt den Link mit zwei Kolleg:innen. Erfüllt dies bereits eine Datenpublikation im wissenschaftlichen Sinne?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Ja, sobald Daten irgendwo online verfügbar sind, gilt dies als Publikation",
            "correct": False,
            "feedback": """× Nicht ausreichend: Reine Online-Verfügbarkeit ohne Referenzierbarkeit, Metadaten oder Dokumentation erfüllt nicht die Anforderungen einer wissenschaftlichen Datenpublikation."""
        },
        {
            "answer": "Nein, da weder eine referenzierbare Beschreibung (Metadaten, Dokumentation) noch eine allgemeine Zugänglichkeit für die Fachcommunity gegeben ist",
            "correct": True,
            "feedback": """✓ Richtig: Datenpublikation setzt mehr voraus als bloße technische Verfügbarkeit - es braucht referenzierbare Beschreibungen und Zugänglichkeit für ein breiteres Publikum, nicht nur für ausgewählte Personen."""
        },
        {
            "answer": "Nein, da CSV-Dateien grundsätzlich kein zulässiges Format für Forschungsdaten sind",
            "correct": False,
            "feedback": """× Falsch: Das Dateiformat CSV ist nicht das Problem - problematisch ist das Fehlen von Referenzierbarkeit, Metadaten und breiter Zugänglichkeit."""
        },
        {
            "answer": "Ja, weil die Weitergabe an Kolleg:innen bereits einer Form von Peer-Review entspricht",
            "correct": False,
            "feedback": """× Falsch: Informeller Austausch mit Kolleg:innen ist kein Peer-Review-Verfahren und ersetzt keine strukturierte, referenzierbare Publikation."""
        }
    ]
}]

display_quiz(single_choice1, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 2

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice2 = [{
    "question": """Ein Team hat 200 Stunden restaurierte DDR-Amateurfilme digitalisiert und mit Annotationen versehen. Bevor über den Publikationsweg entschieden wird, sollten mehrere Fragen geklärt werden. Welche der folgenden Überlegungen sind dabei tatsächlich zielführend?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Wer die Zielgruppe der Veröffentlichung ist - z. B. eine Fachcommunity, Archive oder die Lehre",
            "correct": True,
            "feedback": """✓ Richtig: Die Zielgruppe beeinflusst maßgeblich, welcher Publikationsweg (z. B. Fachrepositorium vs. Lehrmaterial) passend ist."""
        },
        {
            "answer": "Ob an den Filmen Bild- oder Persönlichkeitsrechte von noch lebenden Personen bestehen könnten",
            "correct": True,
            "feedback": """✓ Richtig: Rechtliche Fragen zu Urheberrecht und Persönlichkeitsrechten sind bei historischem Filmmaterial mit abgebildeten Personen zentral für die Wahl des Publikationsweges und etwaige Zugriffsbeschränkungen."""
        },
        {
            "answer": "Wie viele Mitarbeitende im Laufe des Projekts insgesamt beteiligt waren",
            "correct": False,
            "feedback": """× Nicht zielführend: Die Anzahl der Projektmitarbeitenden hat keinen direkten Einfluss auf die Wahl des passenden Publikationsweges."""
        },
        {
            "answer": "Welche Weiterverwendung der Daten realistischerweise zu erwarten ist (z. B. Vergleichsstudien, Lehrmaterial, Tool-Entwicklung)",
            "correct": True,
            "feedback": """✓ Richtig: Das erwartete Nachnutzungsszenario ist eine der zentralen Leitfragen, um einen passenden Publikationsweg zu identifizieren."""
        }
    ]
}]

display_quiz(multiple_choice2, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 3

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice3 = [{
    "question": """Ein Nachwuchsforscher möchte seinen Datensatz zu 25 Kurzfilmen so veröffentlichen, dass er dauerhaft eindeutig zitierbar bleibt, auch wenn sich die URL der Institutsseite in Zukunft ändert. Welche Eigenschaft eines Publikationsortes ist dafür entscheidend?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Die Vergabe eines persistenten Identifikators wie einer DOI",
            "correct": True,
            "feedback": """✓ Richtig: Ein persistenter Identifikator wie eine DOI bleibt auch bei Änderungen der zugrunde liegenden URL stabil und ermöglicht dauerhafte Zitierbarkeit - genau deshalb wird DOI-Vergabe als zentrales Kriterium bei der Wahl von Repositorien genannt."""
        },
        {
            "answer": "Eine möglichst bunte und ansprechende Gestaltung der Institutsseite",
            "correct": False,
            "feedback": """× Falsch: Das visuelle Design hat keinen Einfluss auf dauerhafte Zitierbarkeit oder Stabilität der Referenzierung."""
        },
        {
            "answer": "Die Speicherung der Daten auf möglichst vielen verschiedenen Servern gleichzeitig",
            "correct": False,
            "feedback": """× Falsch: Redundante Speicherung allein löst nicht das Problem wechselnder URLs - entscheidend ist ein stabiler, institutionell verwalteter Identifikator."""
        },
        {
            "answer": "Die Verwendung eines möglichst kurzen Dateinamens",
            "correct": False,
            "feedback": """× Falsch: Die Länge des Dateinamens hat nichts mit dauerhafter Referenzierbarkeit zu tun."""
        }
    ]
}]

display_quiz(single_choice3, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 4

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz1 = DragDropQuiz()

quiz1.create_matching_quiz(
    title="Ordnen Sie jeder Projektsituation den am besten geeigneten Publikationsweg zu:",
    descriptions=[
        "Ein Team hat Code und Analyseskripte entwickelt, die regelmäßig weiterversioniert werden, und möchte eine zitierbare Momentaufnahme jeder größeren Version archivieren",
        "Ein Forschungsprojekt verfügt über ein großes, sich ständig veränderndes Netzwerk aus Filmfestivals, Verleihfirmen und Filmen, das von Dritten flexibel und individuell abgefragt werden soll",
        "Ein Team möchte die Methodik und Struktur seines Datensatzes selbst als eigenständige, peer-reviewte wissenschaftliche Leistung sichtbar machen, unabhängig von einer konkreten Forschungsfrage",
        "Ein groß angelegtes, langfristig gefördertes Projekt möchte umfangreiche biografische Daten für ein breites Publikum interaktiv erkundbar machen"
    ],
    options=[
        "GitHub kombiniert mit Zenodo-Archivierung",
        "API-Schnittstelle",
        "Data Paper in einem Fachjournal",
        "Eigens entwickelte interaktive Website"
    ],
    correct_mapping={
        "Ein Team hat Code und Analyseskripte entwickelt, die regelmäßig weiterversioniert werden, und möchte eine zitierbare Momentaufnahme jeder größeren Version archivieren": "GitHub kombiniert mit Zenodo-Archivierung",
        "Ein Forschungsprojekt verfügt über ein großes, sich ständig veränderndes Netzwerk aus Filmfestivals, Verleihfirmen und Filmen, das von Dritten flexibel und individuell abgefragt werden soll": "API-Schnittstelle",
        "Ein Team möchte die Methodik und Struktur seines Datensatzes selbst als eigenständige, peer-reviewte wissenschaftliche Leistung sichtbar machen, unabhängig von einer konkreten Forschungsfrage": "Data Paper in einem Fachjournal",
        "Ein groß angelegtes, langfristig gefördertes Projekt möchte umfangreiche biografische Daten für ein breites Publikum interaktiv erkundbar machen": "Eigens entwickelte interaktive Website"
    }
)
```

## Aufgabe 5

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice5 = [{
    "question": """Ein kleines, zeitlich befristetes Studierendenprojekt (drei Monate, keine Programmierkenntnisse im Team) hat 10 studentische Kurzfilme analysiert und möchte die Annotationsdaten so publizieren, dass sie von anderen nachgenutzt werden können. Welche Einschätzungen sind in dieser Situation plausibel?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Eine eigene API-Schnittstelle wäre unverhältnismäßig, da weder die Datenmenge noch die Komplexität eine dynamische Abfragbarkeit erfordern und die technischen Voraussetzungen fehlen",
            "correct": True,
            "feedback": """✓ Richtig: APIs eignen sich für komplexe, relationale, dynamische Datenstrukturen und erfordern fortgeschrittene Programmierkenntnisse - beides liegt hier nicht vor, weshalb dieser Weg unangemessen wäre."""
        },
        {
            "answer": "Eine Veröffentlichung in einem disziplinären oder generischen Repositorium wäre angesichts der begrenzten Ressourcen und der überschaubaren Datenmenge ein passender erster Schritt",
            "correct": True,
            "feedback": """✓ Richtig: Repositorien gelten als niedrigschwellig in den erforderlichen Kompetenzen und eignen sich daher gut für kleinere Projekte mit begrenzten Ressourcen."""
        },
        {
            "answer": "Der Aufbau einer eigenen interaktiven Explorer-Website wäre die naheliegendste Wahl, da dies die Sichtbarkeit des Projekts am stärksten erhöht",
            "correct": False,
            "feedback": """× Nicht plausibel: Interaktive Websites erfordern einen deutlich höheren technischen und zeitlichen Aufwand, der für ein dreimonatiges Projekt ohne Programmierkenntnisse nicht leistbar ist - Sichtbarkeit allein rechtfertigt nicht den Aufwand."""
        },
        {
            "answer": "Da das Projekt zeitlich befristet ist, sollte auf eine Publikation der Daten grundsätzlich verzichtet werden",
            "correct": False,
            "feedback": """× Nicht plausibel: Die zeitliche Befristung des Projekts ist kein Grund, auf eine Publikation zu verzichten - im Gegenteil, gerade kleinere Datensätze können wertvoll für Vergleichsstudien oder Lehre sein."""
        }
    ]
}]

display_quiz(multiple_choice5, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 6

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice6 = [{
    "question": """Ein Projekt hat sowohl einen Datensatz mit Annotationen als auch eine ausführliche Beschreibung der Erhebungsmethodik, der Datenqualität und potenzieller Nachnutzungsszenarien verfasst. Es möchte diese Beschreibung selbst als eigenständige, begutachtete wissenschaftliche Publikation sichtbar machen, getrennt von einer inhaltlichen Forschungsfrage. Welches Format passt hierfür am besten?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Ein Data Paper in einem fachspezifischen Data Journal",
            "correct": True,
            "feedback": """✓ Richtig: Ein Data Paper ist speziell dafür konzipiert, Datenerhebung, -qualität und -struktur unabhängig von einer inhaltlichen Fragestellung zu dokumentieren, und durchläuft dabei - wie ein regulärer Artikel - ein Peer-Review-Verfahren."""
        },
        {
            "answer": "Eine reine Ablage der Rohdaten in einem generischen Repositorium ohne Begleittext",
            "correct": False,
            "feedback": """× Nicht passend: Eine reine Datenablage ohne begleitende Dokumentation entspricht nicht dem Wunsch, die Methodik selbst als eigenständige begutachtete Publikation sichtbar zu machen - dafür braucht es das strukturierte, peer-reviewte Format eines Data Papers."""
        },
        {
            "answer": "Eine unstrukturierte Projektwebsite ohne Begutachtungsverfahren",
            "correct": False,
            "feedback": """× Nicht passend: Ohne Peer-Review-Verfahren fehlt die wissenschaftliche Anerkennung, die für eine eigenständige Sichtbarkeit als begutachtete Publikation notwendig ist."""
        },
        {
            "answer": "Eine private Weitergabe der Dokumentation an interessierte Kolleg:innen per E-Mail",
            "correct": False,
            "feedback": """× Nicht passend: Dies entspricht keiner öffentlichen, referenzierbaren und begutachteten Publikationsform."""
        }
    ]
}]

display_quiz(single_choice6, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 7

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice8 = [{
    "question": """Ein Projekt zu Filmfestival-Netzwerken hat sowohl (a) eine seit Jahren wachsende, sich ständig verändernde relationale Datenbank aus Festivals, Verleihfirmen und Filmen als auch (b) eine für eine bestimmte Publikation genutzte, abgeschlossene Korpusliste von 150 Filmen. Welche Aussagen zur separaten Behandlung dieser beiden Datenbestände sind schlüssig?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Für (a) ist eine API-basierte Bereitstellung sinnvoller, da Dritte flexibel und aktuell auf die sich verändernden Beziehungsdaten zugreifen können sollen, statt eine veraltete Momentaufnahme herunterzuladen",
            "correct": True,
            "feedback": """✓ Richtig: Dynamische, relationale und sich verändernde Datenstrukturen sind der klassische Anwendungsfall für APIs, da so stets der aktuelle Stand abgefragt werden kann, statt eine statische Kopie zu verbreiten."""
        },
        {
            "answer": "Für (b) eignet sich eine Ablage in einem Repositorium mit DOI besser, da diese Liste als abgeschlossenes, referenzierbares Datenprodukt zu einem bestimmten Zeitpunkt zitierfähig gemacht werden soll",
            "correct": True,
            "feedback": """✓ Richtig: Eine abgeschlossene, unveränderliche Datenversion profitiert von einer stabilen, referenzierbaren und DOI-versehenen Ablage - genau der Stärke eines Repositoriums."""
        },
        {
            "answer": "Beide Datenbestände sollten zwingend über denselben Publikationsweg bereitgestellt werden, um Konsistenz zu gewährleisten",
            "correct": False,
            "feedback": """× Nicht schlüssig: Konsistenz im Sinne einheitlicher Dokumentation ist sinnvoll, doch die technische Beschaffenheit der Daten (dynamisch vs. statisch) rechtfertigt hier unterschiedliche, jeweils passendere Publikationswege."""
        },
        {
            "answer": "Da es sich in beiden Fällen um filmbezogene Daten handelt, ist eine Unterscheidung des Publikationsweges nicht notwendig",
            "correct": False,
            "feedback": """× Nicht schlüssig: Nicht der Inhalt (Filme), sondern die Beschaffenheit der Daten (dynamisch/relational vs. statisch/abgeschlossen) bestimmt die Eignung eines Publikationsweges."""
        }
    ]
}]

display_quiz(multiple_choice8, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 8

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice9 = [{
    "question": """Ein Projekt veröffentlicht seine Annotationsdaten in einem GitHub-Repositorium und beschränkt sich darauf, ausschließlich die Rohdaten (Timecode-Listen) hochzuladen, ohne weitere Angaben. Ein zweites Projekt veröffentlicht vergleichbare Annotationsdaten, ergänzt diese jedoch um das verwendete Analysevokabular, ein Annotationstemplate sowie Korpus-Metadaten. Was unterscheidet die beiden Ansätze am grundlegendsten hinsichtlich der Nachnutzbarkeit?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Das zweite Projekt ermöglicht durch die zusätzlichen Materialien nicht nur die Nutzung der bestehenden Daten, sondern auch die eigenständige Reproduktion und Fortführung der Datenerhebung durch Dritte",
            "correct": True,
            "feedback": """✓ Richtig: Erst durch die Bereitstellung von Vokabular, Template und Metadaten wird ein Repositorium zu mehr als einer reinen Datenablage - es ermöglicht Dritten, die Methodik nachzuvollziehen und selbst anzuwenden, wie es das AdA-Projekt vorbildhaft zeigt."""
        },
        {
            "answer": "Es gibt keinen wesentlichen Unterschied, da beide Projekte ihre Daten öffentlich auf GitHub bereitstellen",
            "correct": False,
            "feedback": """× Falsch: Öffentliche Verfügbarkeit allein sagt nichts über die tatsächliche Nachnutzbarkeit aus - entscheidend ist, ob Kontext, Methodik und Struktur mitgeliefert werden."""
        },
        {
            "answer": "Das erste Projekt ist vorzuziehen, da reine Rohdaten ohne zusätzliche Dateien schneller heruntergeladen werden können",
            "correct": False,
            "feedback": """× Falsch: Downloadgeschwindigkeit ist kein relevantes Kriterium für wissenschaftliche Nachnutzbarkeit - im Gegenteil, fehlender Kontext erschwert die sinnvolle Weiterverwendung erheblich."""
        },
        {
            "answer": "Der Unterschied betrifft ausschließlich die Dateigröße, nicht die inhaltliche Qualität der Publikation",
            "correct": False,
            "feedback": """× Falsch: Es geht nicht um Dateigröße, sondern um die methodische Nachvollziehbarkeit und Reproduzierbarkeit, die durch Vokabular, Templates und Metadaten erst ermöglicht wird."""
        }
    ]
}]

display_quiz(single_choice9, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 9

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false1 = [{
    "question": """Ein Team veröffentlicht seinen Code auf GitHub und geht davon aus, dass dieser dadurch bereits automatisch eine zitierfähige DOI besitzt""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! GitHub selbst vergibt keine DOIs. Für eine zitierfähige, dauerhafte Archivierung muss das Repository zusätzlich über einen DOI-fähigen Dienst wie Zenodo archiviert werden."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: GitHub bietet Versionierung und Sichtbarkeit, aber keine automatische DOI-Vergabe - hierfür ist eine zusätzliche Archivierung z. B. über Zenodo notwendig."""
        }
    ]
}]

display_quiz(true_false1, colors=colors.jupyterquiz, max_width=900)
```

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false2 = [{
    "question": """Ein Projektteam argumentiert: "Unser Forschungsdatenmanagement ist bereits vollständig FAIR-konform umgesetzt, daher ist die Wahl des konkreten Publikationsweges nur noch eine rein technische Formsache ohne inhaltliche Abwägung." Ist diese Einschätzung zutreffend?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Nein",
            "correct": True,
            "feedback": """✓ Korrekt! FAIR-Konformität betrifft vor allem Auffindbarkeit, Zugänglichkeit, Interoperabilität und Nachnutzbarkeit der Daten selbst - sie ersetzt nicht die kontextabhängige Abwägung von Datentyp, Zielgruppe, Nachnutzungsszenario und Rechtslage, die den konkret geeigneten Publikationsweg (Repositorium, Data Paper, API, GLAM-Website) bestimmt."""
        },
        {
            "answer": "Ja",
            "correct": False,
            "feedback": """× Nicht korrekt: Selbst bei vollständiger FAIR-Konformität bleibt die Wahl zwischen unterschiedlichen Publikationswegen eine inhaltliche Entscheidung, die von Faktoren wie Zielgruppe, Datendynamik und verfügbaren Ressourcen abhängt."""
        }
    ]
}]

display_quiz(true_false2, colors=colors.jupyterquiz, max_width=900)
```

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false3 = [{
    "question": """Ein Team geht davon aus, dass bei der Publikation von digitalisiertem historischem Filmmaterial keine urheberrechtlichen Probleme auftreten können, da die Filme bereits mehrere Jahrzehnte alt sind""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Das Alter eines Films allein garantiert nicht den Wegfall urheberrechtlicher Ansprüche - Schutzfristen, Rechte an Restaurierungen/Digitalisaten sowie Persönlichkeitsrechte abgebildeter Personen können weiterhin relevant sein. Genau deshalb wird empfohlen, rechtliche Aspekte anhand eines strukturierten Entscheidungsprozesses projektspezifisch zu prüfen, statt pauschale Annahmen zu treffen."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: Das Alter des Filmmaterials ist kein verlässlicher Indikator für die urheberrechtliche Unbedenklichkeit - Rechte an Digitalisaten, Restaurierungen oder Persönlichkeitsrechte können unabhängig vom Produktionsjahr fortbestehen."""
        }
    ]
}]

display_quiz(true_false3, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 10

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz2 = DragDropQuiz()

quiz2.create_matching_quiz(
    title="Ordnen Sie jede Konsequenz der jeweils zugrunde liegenden Fehleinschätzung zu:",
    descriptions=[
        "Ein Projekt veröffentlicht Code auf GitHub, kann seine Analysepipeline aber in einer späteren Publikation nicht mehr eindeutig zitieren, weil sich Repository-Inhalte und URLs seither mehrfach geändert haben",
        "Ein Team entwickelt für einen kleinen, statischen Datensatz von 5 Kurzfilmen aufwendig eine eigene API und bindet damit unnötig Projektressourcen, obwohl niemand dynamische Abfragen benötigt",
        "Ein Projekt veröffentlicht einen Datensatz in einem Repositorium, erhält aber kaum Nachnutzung, weil weder Erhebungsmethodik noch Vokabular oder Templates dokumentiert wurden",
        "Ein Team geht unreflektiert davon aus, dass digitalisierte historische Filmausschnitte in jedem Fall gefahrlos veröffentlicht werden dürfen und übersieht so mögliche Rechtsverletzungen"
    ],
    options=[
        "Fehlende DOI-Archivierung trotz Nutzung von GitHub",
        "Fehleinschätzung der tatsächlich benötigten Datendynamik",
        "Fehlende Kontext- und Methodendokumentation",
        "Unterschätzung fortbestehender Rechteansprüche"
    ],
    correct_mapping={
        "Ein Projekt veröffentlicht Code auf GitHub, kann seine Analysepipeline aber in einer späteren Publikation nicht mehr eindeutig zitieren, weil sich Repository-Inhalte und URLs seither mehrfach geändert haben": "Fehlende DOI-Archivierung trotz Nutzung von GitHub",
        "Ein Team entwickelt für einen kleinen, statischen Datensatz von 5 Kurzfilmen aufwendig eine eigene API und bindet damit unnötig Projektressourcen, obwohl niemand dynamische Abfragen benötigt": "Fehleinschätzung der tatsächlich benötigten Datendynamik",
        "Ein Projekt veröffentlicht einen Datensatz in einem Repositorium, erhält aber kaum Nachnutzung, weil weder Erhebungsmethodik noch Vokabular oder Templates dokumentiert wurden": "Fehlende Kontext- und Methodendokumentation",
        "Ein Team geht unreflektiert davon aus, dass digitalisierte historische Filmausschnitte in jedem Fall gefahrlos veröffentlicht werden dürfen und übersieht so mögliche Rechtsverletzungen": "Unterschätzung fortbestehender Rechteansprüche"
    }
)
```

## Aufgabe 11

**Szenario:** Sie beraten ein filmwissenschaftliches Projekt, das drei sehr unterschiedliche Datenprodukte erzeugt hat:

- eine Sammlung von 40 handkodierten Sequenzprotokollen zu Naturdokumentationen (abgeschlossen, statisch)
- eine kontinuierlich wachsende, relationale Datenbank zu Ko-Produktionsnetzwerken zwischen Sendern und Produktionsfirmen
- eine ausführliche methodische Reflexion zur Entwicklung der eigenen Kodierungssystematik, die als eigenständiger wissenschaftlicher Beitrag sichtbar werden soll

Beschreiben Sie für jedes der drei Datenprodukte, welchen Publikationsweg Sie empfehlen würden und begründen Sie Ihre Entscheidung anhand der jeweiligen Beschaffenheit der Daten - nicht anhand des Themas (Naturdokumentationen).

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_4-12')
```

````{admonition} Musterlösung
:class: solution, dropdown

**(a) Sequenzprotokolle (abgeschlossen, statisch):**
Ein Repositorium (z. B. media/rep/ oder Zenodo) mit DOI-Vergabe ist hier passend, da es sich um ein abgeschlossenes, unveränderliches Datenprodukt handelt, das dauerhaft referenzierbar gemacht werden soll. Eine API wäre unverhältnismäßig, da keine dynamische Abfragbarkeit benötigt wird.

**(b) Ko-Produktionsnetzwerk (dynamisch, relational, wachsend):**
Eine API-Schnittstelle eignet sich hier deutlich besser, da die Daten sich kontinuierlich verändern und Dritte idealerweise stets auf den aktuellen Stand zugreifen sollen, statt eine veraltete statische Kopie zu erhalten. Dies setzt allerdings entsprechende Programmierkenntnisse im Projekt voraus.

**(c) Methodische Reflexion zur Kodierungssystematik (eigenständiger wissenschaftlicher Beitrag):**
Ein Data Paper in einem einschlägigen Fachjournal (z. B. NECSUS oder Journal of Open Humanities Data) ist hier die passende Wahl, da es genau dafür konzipiert ist, Methodik, Erhebungslogik und Struktur eines Datenprodukts - unabhängig von einer inhaltlichen Forschungsfrage - als eigenständige, peer-reviewte Leistung sichtbar zu machen.

**Zentrale Erkenntnis:** Die Entscheidung für einen Publikationsweg richtet sich nicht nach dem Forschungsthema, sondern nach der technischen und funktionalen Beschaffenheit der jeweiligen Daten (statisch/dynamisch, relational/einfach) sowie dem Ziel der Veröffentlichung (Datenzugänglichkeit vs. methodische Sichtbarkeit).
````

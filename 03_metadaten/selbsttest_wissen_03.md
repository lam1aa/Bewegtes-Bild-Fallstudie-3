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
Diese Übungsaufgaben dienen Ihrer Selbsteinschätzung und helfen Ihnen, das im Kapitel Gelernte zu reflektieren.

Sie können die Fragen in beliebiger Reihenfolge bearbeiten und die Beantwortung auch mehrfach versuchen.

**So funktioniert es:**
- Wählen Sie bei jeder Frage die Antwort(en) aus, die Sie für richtig halten
- Lesen Sie das Feedback zu den einzelnen Antwortoptionen sorgfältig durch
- Die Erklärungen helfen Ihnen, Ihr Verständnis zu vertiefen – auch bei korrekten Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse. Nutzen Sie dieses Assessment, um Wissenslücken zu identifizieren und gegebenenfalls die entsprechenden Abschnitte des Kapitels nochmals zu bearbeiten.

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

multiple_choice1 = [{
    "question": """Ein Filmarchiv digitalisiert eine Sammlung von Super-8-Amateurfilmen. Zu jeder Datei werden u.a. Dateigröße, Erstellungsdatum der Digitalisierung und Zugriffsrechte gespeichert, außerdem wird die Abfolge der einzelnen Filmsequenzen dokumentiert. Welche Aussagen zu den hier vorliegenden Metadatentypen sind korrekt?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Dateigröße und Zugriffsrechte sind Beispiele für administrative Metadaten",
            "correct": True,
            "feedback": """✓ Richtig: Administrative Metadaten helfen bei Verwaltung und langfristiger Sicherung der Daten, u.a. mit technischen und rechtlichen Angaben wie Dateigröße oder Zugriffsrechten."""
        },
        {
            "answer": "Die Dokumentation der Sequenzabfolge ist ein Beispiel für strukturelle Metadaten",
            "correct": True,
            "feedback": """✓ Richtig: Strukturelle Metadaten beschreiben die Anordnung und Hierarchie eines Objekts, wie z. B. die sequentielle Abfolge eines Films."""
        },
        {
            "answer": "Alle hier genannten Angaben sind eindeutig nur einer einzigen Metadatenkategorie zuzuordnen und überschneiden sich nie",
            "correct": False,
            "feedback": """× Falsch: Der Text weist explizit darauf hin, dass sich Metadaten-Kategorien nicht immer klar trennen lassen, z. B. bei Überlappungen zwischen Prozess- und administrativen Metadaten."""
        },
        {
            "answer": "Das Erstellungsdatum der Digitalisierung könnte je nach Kontext sowohl administrativen als auch Prozessmetadaten zugeordnet werden",
            "correct": True,
            "feedback": """✓ Richtig: Gerade technische Angaben wie Erstellungsdatum oder Migration können sowohl administrative als auch prozessbezogene Aspekte betreffen - eine trennscharfe Zuordnung ist nicht immer möglich."""
        }
    ]
}]

display_quiz(multiple_choice1, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 2

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Ordnen Sie die folgenden Projektsituationen dem jeweils passenden Metadatenschema bzw. -standard zu:",
    descriptions=[
        "Ein kleines interdisziplinäres Projekt möchte digitale Objekte unterschiedlichster Art (Texte, Bilder, Webseiten) mit möglichst geringem Einarbeitungsaufwand beschreiben",
        "Ein Forschungsdatensatz soll publiziert, mit einer DOI versehen und zitierfähig gemacht werden",
        "Ein filmhistorisches Archivprojekt möchte den gesamten Lebenszyklus eines Films inkl. Fassungen und Trägermedien in einer komplexen, relationalen Struktur abbilden"
    ],
    options=[
        "Dublin Core",
        "DataCite",
        "EN 15907"
    ],
    correct_mapping={
        "Ein kleines interdisziplinäres Projekt möchte digitale Objekte unterschiedlichster Art (Texte, Bilder, Webseiten) mit möglichst geringem Einarbeitungsaufwand beschreiben": "Dublin Core",
        "Ein Forschungsdatensatz soll publiziert, mit einer DOI versehen und zitierfähig gemacht werden": "DataCite",
        "Ein filmhistorisches Archivprojekt möchte den gesamten Lebenszyklus eines Films inkl. Fassungen und Trägermedien in einer komplexen, relationalen Struktur abbilden": "EN 15907"
    }
)
```

## Aufgabe 3

Bewerten Sie folgende Aussagen zu Metadatenstandards und ihrer Anwendung:

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false1 = [{
    "question": """Der EN 15744-Standard ist grundsätzlich für alle filmwissenschaftlichen Projekte zu komplex und daher ungeeignet""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! EN 15744 ist im Gegenteil ein Minimalstandard mit nur 15 Elementen in flacher Struktur, vergleichbar mit Dublin Core - für kleinere Projekte mit überschaubaren Korpora oft völlig ausreichend."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: EN 15744 ist gerade der einfachere, nicht der komplexe Standard - EN 15907 bildet die komplexere, relationale Variante."""
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
    "question": """Die Wahl eines geeigneten Metadatenschemas hängt u.a. davon ab, ob die Daten primär publiziert und zitierfähig gemacht werden sollen oder primär inhaltlich beschrieben werden sollen""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Richtig",
            "correct": True,
            "feedback": """✓ Korrekt! Der Fragenkatalog zur Schema-Auswahl verweist explizit auf den Aspekt Publikation und Zitation als Entscheidungskriterium - hierfür eignet sich z. B. DataCite besonders gut, während generische Schemata wie Dublin Core eher für inhaltliche Minimalbeschreibungen genutzt werden."""
        },
        {
            "answer": "Falsch",
            "correct": False,
            "feedback": """× Nicht korrekt: Genau dieser Unterschied ist zentrales Auswahlkriterium, wie der praxisnahe Fragenkatalog zeigt."""
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
    "question": """Metadatenstandards und Klassifizierungssysteme sind grundsätzlich neutral und frei von wertenden Vorannahmen, da sie rein technischer Natur sind""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Nach Drucker tragen alle Klassifizierungssysteme den ideologischen Abdruck ihrer Produktion in sich - sie sind historisch situiert und stellen spezifische Sichtweisen von Welt- und Wissensordnungen her, z. B. sichtbar am Feld creator, das kollektive Produktionsweisen ausblenden kann."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: Klassifizierungssysteme sind weder wertneutral noch objektiv, da sie immer auf Auswahlentscheidungen beruhen."""
        }
    ]
}]

display_quiz(true_false3, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 4

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice4 = [{
    "question": """Ein Projektteam findet in einer nachgenutzten historischen Filmdatenbank eine Synopse mit stark diskriminierender, veralteter Sprache. Das Team möchte den historischen Charakter der Quelle erhalten, aber keine diskriminierenden Inhalte unkommentiert weiterverbreiten. Welche Vorgehensweise entspricht am besten den im Kapitel vorgestellten diskriminierungssensiblen Praktiken?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Die problematischen Begriffe kommentarlos genau wie im Original übernehmen, da Objektivität in der Archivarbeit oberste Priorität hat",
            "correct": False,
            "feedback": """× Falsch: Genau dieses Vorgehen wird am Beispiel des DNB-Katalogeintrags kritisiert - die unkommentierte Übernahme führt zur Fortschreibung diskriminierender Implikationen."""
        },
        {
            "answer": "Die Originalsynopse vollständig löschen und durch eine neue, moderne Inhaltsangabe ersetzen, ohne auf die Quelle hinzuweisen",
            "correct": False,
            "feedback": """× Falsch: Dies würde den historischen Entstehungskontext verschleiern, den das Sammeln und Erforschen von Ressourcen gerade bewahren soll."""
        },
        {
            "answer": """Die Quelle durch einen Disclaimer kontextualisieren, problematische Begriffe ggf. kennzeichnen und auf den historischen bzw. propagandistischen Charakter des Werks hinweisen, wie es die Murnau-Stiftung bei J*d Süß vorgemacht hat""",
            "correct": True,
            "feedback": """✓ Richtig: Diese Kombination aus Kontextualisierung, Disclaimer und expliziter Einordnung des Werks als problematisch entspricht genau der im Kapitel beschriebenen Best Practice."""
        },
        {
            "answer": "Nachgenutzte Metadaten müssen grundsätzlich nicht auf diskriminierende Inhalte geprüft werden, da die Verantwortung allein bei der Ursprungsquelle liegt",
            "correct": False,
            "feedback": """× Falsch: Der Fragenkatalog fordert explizit die Prüfung nachgenutzter Daten auf problematische Titel oder Beschreibungen und Strategien zur Vermeidung ihrer Reproduktion."""
        }
    ]
}]

display_quiz(single_choice4, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 5

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz2 = DragDropQuiz()

quiz2.create_matching_quiz(
    title="Ordnen Sie die folgenden Maßnahmen der jeweils passenden diskriminierungssensiblen Praktik zu:",
    descriptions=[
        "Ein problematischer Begriff wird mit einem Sternchen versehen, um ihn zu markieren, ohne ihn vollständig auszuschreiben",
        "Zu einem historischen Filmtitel wird zusätzlich eine heute bevorzugte, alternative Bezeichnung angegeben",
        "Ein einleitender Hinweistext klärt Nutzer:innen über diskriminierende Inhalte einer Quelle auf, bevor sie darauf zugreifen",
        "Ein Projekt verwendet statt veralteter Begriffe ein aktualisiertes, inklusives kontrolliertes Vokabular aus einem Fachglossar"
    ],
    options=[
        "Verfremdungsvariante",
        "Mehrfachbenennung",
        "Disclaimer",
        "Alternatives kontrolliertes Vokabular"
    ],
    correct_mapping={
        "Ein problematischer Begriff wird mit einem Sternchen versehen, um ihn zu markieren, ohne ihn vollständig auszuschreiben": "Verfremdungsvariante",
        "Zu einem historischen Filmtitel wird zusätzlich eine heute bevorzugte, alternative Bezeichnung angegeben": "Mehrfachbenennung",
        "Ein einleitender Hinweistext klärt Nutzer:innen über diskriminierende Inhalte einer Quelle auf, bevor sie darauf zugreifen": "Disclaimer",
        "Ein Projekt verwendet statt veralteter Begriffe ein aktualisiertes, inklusives kontrolliertes Vokabular aus einem Fachglossar": "Alternatives kontrolliertes Vokabular"
    }
)
```

## Aufgabe 6

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice6 = [{
    "question": """Welche der folgenden Aussagen zum Vergleich von Dublin Core und den filmwissenschaftlichen CWS-Standards (EN 15744/EN 15907) sind korrekt?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Dublin Core ist disziplinübergreifend einsetzbar, während EN 15744/EN 15907 speziell auf die Bedürfnisse der Filmarchivierung zugeschnitten sind",
            "correct": True,
            "feedback": """✓ Richtig: Dublin Core ist ein generischer, fächerübergreifender Standard, während die CWS-Standards fachspezifisch für Filmwerke entwickelt wurden."""
        },
        {
            "answer": "Generische Standards wie Dublin Core sind grundsätzlich allen fachspezifischen Standards überlegen, da sie mehr Elemente enthalten",
            "correct": False,
            "feedback": """× Falsch: Dublin Core enthält mit 15 Elementen sogar genauso viele Elemente wie EN 15744, deckt aber komplexere fachspezifische Anforderungen wie den Lebenszyklus eines Films (EN 15907) nicht ab."""
        },
        {
            "answer": "Fachspezifische Standards werden häufig entwickelt, weil generische Schemata die Erfordernisse des jeweiligen Fachs nicht ausreichend abdecken",
            "correct": True,
            "feedback": """✓ Richtig: Genau dies wird als Grund für die Existenz und Anpassung fachspezifischer Metadatenschemata genannt."""
        },
        {
            "answer": "EN 15907 nutzt Konzepte aus dem FRBR-Modell (Werk, Variante, Manifestation, Exemplar), um verschiedene Ebenen eines Films zu unterscheiden",
            "correct": True,
            "feedback": """✓ Richtig: Diese vier Begriffe aus dem FRBR-Modell wurden für die Filmarchivierung im EN 15907-Standard übernommen."""
        }
    ]
}]

display_quiz(multiple_choice6, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 7

**Szenario:** Sie bereiten die Publikation eines Datensatzes zu einem Korpus von 30 ostdeutschen Dokumentarfilmen (1985–1995) vor. Der Datensatz enthält Filmtitel, Regieangaben, Schlagworte sowie nachgenutzte Metadaten aus einem historischen Bibliothekskatalog, in dem einige Schlagworte und Beschreibungstexte aus heutiger Sicht diskriminierende oder stark ideologisch geprägte Sprache enthalten.

Beschreiben Sie:
1. Welches Metadatenschema bzw. welche Kombination von Standards Sie für die Publikation wählen würden und warum
2. Wie Sie mit den diskriminierenden bzw. ideologisch geprägten Inhalten in den nachgenutzten Metadaten umgehen würden

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_3-7')
```

````{admonition} Musterlösung
:class: solution, dropdown

**1. Wahl des Metadatenschemas:**
- Für die reine Publikation und Zitierfähigkeit des Datensatzes (DOI-Registrierung) eignet sich **DataCite**, da es eng mit persistenten Identifikatoren verknüpft ist und international in Forschungsdateninfrastrukturen etabliert ist
- Für die inhaltliche, filmspezifische Beschreibung der einzelnen Filme (Titel, Fassungen, Beteiligte) bietet sich zusätzlich eine Orientierung an **EN 15744** an, da es sich um einen überschaubaren Korpus handelt, für den ein Minimalstandard ausreicht - bei Bedarf differenzierterer Fassungs- oder Trägerinformationen käme auch EN 15907 in Frage
- Eine Kombination beider Standardtypen (generisch für Publikation/Zitation, fachspezifisch für inhaltliche Beschreibung) ist dabei üblich und sinnvoll

**2. Umgang mit diskriminierenden nachgenutzten Inhalten:**
- Zunächst systematische Prüfung des Datensatzes anhand des Fragenkatalogs (Korpus, Inhalte, Metadaten & Begriffe, Datenquellen, historische Kontexte)
- Trennung von Originalbeschreibung (historisches Zitat/Fremdmetadaten) und eigener Projektbeschreibung, um eine unreflektierte Vermischung zu vermeiden
- Einsatz eines Disclaimers, der auf die ideologische Prägung der historischen Quelle (DDR-Kontext) hinweist und den Entstehungshintergrund transparent macht
- Ggf. Mehrfachbenennung: historischer Schlagwortbegriff parallel zu einer heute bevorzugten, neutraleren Bezeichnung
- Bei stark diskriminierender Sprache Prüfung alternativer, inklusiver kontrollierter Vokabulare, ohne die historische Nachvollziehbarkeit der Originalquelle zu verlieren
- Dokumentation der getroffenen Entscheidungen (z. B. in einer README), damit Nachnutzende den Umgang mit den sensiblen Metadaten nachvollziehen können
````

## Aufgabe 8

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice8 = [{
    "question": """Ein Forschungsprojekt katalogisiert restaurierte Fassungen eines Stummfilms, die in unterschiedlichen Längen und mit unterschiedlichen Musikbegleitungen kursieren, jeweils auf DVD, Blu-ray und als digitale Streamingdatei. Warum würde sich für dieses konkrete Vorhaben eine Modellierung nach EN 15907 eher anbieten als eine reine Dublin-Core-Beschreibung?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Weil Dublin Core grundsätzlich keine Angaben zu Titel oder Urheberschaft zulässt, EN 15907 dies aber ermöglicht",
            "correct": False,
            "feedback": """× Falsch: Dublin Core enthält mit dc:title und dc:creator durchaus vergleichbare Basisfelder. Der entscheidende Unterschied liegt nicht in Basisangaben, sondern in der Modellierungstiefe."""
        },
        {
            "answer": "Weil EN 15907 durch die FRBR-Ebenen Werk, Variante, Manifestation und Exemplar gezielt die Beziehungen zwischen unterschiedlichen Fassungen, Formaten und Trägern eines Films abbilden kann, was bei Dublin Cores flacher Struktur nicht vorgesehen ist",
            "correct": True,
            "feedback": """✓ Richtig: Genau für diesen Fall - mehrere Fassungen und Trägermedien eines Werks - wurde das FRBR-Modell in EN 15907 integriert. Dublin Core kennt zwar das Element dc:relation, bildet aber keine hierarchische Werk-Varianten-Struktur ab."""
        },
        {
            "answer": "Weil EN 15907 international weniger verbreitet ist und daher spezialisierten Archivprojekten vorbehalten bleibt",
            "correct": False,
            "feedback": """× Falsch: Die Verbreitung ist kein inhaltliches Argument für die Eignung - entscheidend ist die strukturelle Passung zum komplexen Beziehungsgeflecht von Fassungen und Manifestationen."""
        },
        {
            "answer": "Weil bei Verwendung von Dublin Core keine Lizenzangaben zu den unterschiedlichen Trägermedien gemacht werden könnten",
            "correct": False,
            "feedback": """× Falsch: Dublin Core besitzt mit dc:rights durchaus ein Lizenzfeld - das eigentliche Problem ist die fehlende relationale Tiefe für Werk-Varianten-Beziehungen, nicht die Lizenzierung."""
        }
    ]
}]

display_quiz(multiple_choice8, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 9

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice9 = [{
    "question": """Die University of Michigan Library stellt fest, dass beschreibende Metadaten "grundsätzlich nicht neutral" sind, reagiert aber dennoch aktiv mit Maßnahmen zur Kontextualisierung, statt problematische historische Bestände unverändert zu lassen. Was ist die treffendste Interpretation dieser Haltung im Sinne des Kapitels?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Da Neutralität ohnehin unerreichbar ist, ist jede Form der Kontextualisierung letztlich beliebig und wissenschaftlich nicht besser begründbar als der Verzicht darauf",
            "correct": False,
            "feedback": """× Falsch: Aus der Erkenntnis, dass Neutralität nicht erreichbar ist, folgt im Kapitel gerade nicht Beliebigkeit, sondern die Notwendigkeit einer bewussten, reflektierten und dokumentierten Umgangsweise mit dieser Nicht-Neutralität."""
        },
        {
            "answer": "Die Anerkennung fehlender Neutralität begründet eine aktive Verantwortung, mit vorhandenen diskriminierenden Strukturen transparent umzugehen, anstatt sie unreflektiert fortzuschreiben oder sie durch Schweigen zu verdecken",
            "correct": True,
            "feedback": """✓ Richtig: Das Statement zeigt exemplarisch, wie aus der Diagnose (nicht neutral) eine konkrete Praxis (Identifizierung, Kontextualisierung, Überarbeitung) abgeleitet wird - ein zentraler Gedanke des gesamten Abschnitts zu diskriminierungssensiblen Metadaten."""
        },
        {
            "answer": "Die Haltung fordert implizit, alle historisch belasteten Titel und Beschreibungen vollständig aus Katalogen zu entfernen, um Diskriminierung zu vermeiden",
            "correct": False,
            "feedback": """× Falsch: Das Kapitel plädiert gerade nicht für Löschung, sondern für Kontextualisierung bei gleichzeitigem Erhalt der historischen Merkmale der Ressourcen - vgl. die Diskussion zum Erhalt von Entstehungsmerkmalen trotz problematischer Titel."""
        },
        {
            "answer": "Die Haltung bezieht sich ausschließlich auf technische Metadatenfelder wie Dateiformat oder Speicherort, nicht auf inhaltliche Beschreibungstexte",
            "correct": False,
            "feedback": """× Falsch: Das Statement bezieht sich explizit auf "beschreibende Metadaten", also inhaltliche/deskriptive Felder wie Synopsen oder Schlagworte, nicht auf rein technische Angaben."""
        }
    ]
}]

display_quiz(single_choice9, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 10

Bewerten Sie folgende, bewusst nuancierte Aussagen:

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false4 = [{
    "question": """Die Existenz international standardisierter Metadatenschemata wie EN 15907 bedeutet, dass die damit erschlossenen Filmdaten frei von historischen oder ideologischen Vorannahmen sind, da es sich um rein technische Katalogisierungsstandards handelt""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Auch technisch wirkende, stark standardisierte Schemata sind laut Drucker nie wertneutral, da bereits die Auswahl der zu beschreibenden Elemente und Kategorien normative Vorannahmen enthält - das Kapitel betont explizit, dass Metadatenstandards oft hoch umstritten sind, weil sie implizite oder explizite Werturteile enthalten, selbst wenn sie technisch-standardisiert wirken."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: Der technische bzw. standardisierte Charakter eines Schemas schützt nicht vor eingebetteten Werturteilen - im Gegenteil, gerade weil solche Standards oft unhinterfragt im Hintergrund von Archivsystemen wirken, bleiben ihre normativen Annahmen häufig unsichtbar."""
        }
    ]
}]

display_quiz(true_false4, colors=colors.jupyterquiz, max_width=900)
```

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false5 = [{
    "question": """Ein Projekt, das konsequent Mehrfachbenennung (historischer Titel + bevorzugte Bezeichnung) für alle problematischen Werktitel einsetzt, hat damit automatisch auch die Frage nach diskriminierenden Inhalten in nachgenutzten Schlagwortsystemen oder Thesauri gelöst""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Mehrfachbenennung adressiert primär die Titelebene. Der Fragenkatalog unterscheidet explizit mehrere Ebenen (Korpus, Inhalte, Metadaten & Begriffe, Datenquellen, historische Kontexte, Rollen) - problematische Schlagwortsysteme oder Thesauri erfordern eine gesonderte Prüfung auf veraltete Begriffe und ggf. den Einsatz alternativer kontrollierter Vokabulare, unabhängig von der Titelbehandlung."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: Die verschiedenen diskriminierungssensiblen Praktiken (Disclaimer, Verfremdung, Mehrfachbenennung, alternative Vokabulare) adressieren unterschiedliche Problemstellen und schließen sich nicht gegenseitig ein - Titelbehandlung und Vokabularprüfung sind getrennte Aufgaben."""
        }
    ]
}]

display_quiz(true_false5, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 11

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz3 = DragDropQuiz()

quiz3.create_matching_quiz(
    title="Ordnen Sie die folgende Projektsituation dem Bereich des Fragenkatalogs zu, der jeweils am ehesten übersehen werden könnte, wenn man sich nur auf die inhaltliche Prüfung von Synopsen konzentriert:",
    descriptions=[
        "Ein per API von TMDb übernommener Datensatz enthält problematische Genre-Tags, die von der Plattform algorithmisch vergeben wurden",
        "Die im Projekt verwendeten Regie- und Produktionsangaben verschweigen systematisch die Mitwirkung von Kollektiven zugunsten einer einzelnen benannten Person",
        "Der ausgewählte Filmkorpus besteht fast ausschließlich aus westeuropäischen Produktionen, ohne dass dies irgendwo dokumentiert wird",
        "Nutzer:innenkommentare aus einer nachgenutzten Streaming-Plattform werden ungefiltert in die Projektdatenbank übernommen"
    ],
    options=[
        "Bereich D: Datenquellen",
        "Bereich F: Rollen, Gewerke",
        "Bereich A: Korpus",
        "Bereich D: Nutzer:innendaten"
    ],
    correct_mapping={
        "Ein per API von TMDb übernommener Datensatz enthält problematische Genre-Tags, die von der Plattform algorithmisch vergeben wurden": "Bereich D: Datenquellen",
        "Die im Projekt verwendeten Regie- und Produktionsangaben verschweigen systematisch die Mitwirkung von Kollektiven zugunsten einer einzelnen benannten Person": "Bereich F: Rollen, Gewerke",
        "Der ausgewählte Filmkorpus besteht fast ausschließlich aus westeuropäischen Produktionen, ohne dass dies irgendwo dokumentiert wird": "Bereich A: Korpus",
        "Nutzer:innenkommentare aus einer nachgenutzten Streaming-Plattform werden ungefiltert in die Projektdatenbank übernommen": "Bereich D: Nutzer:innendaten"
    }
)
```

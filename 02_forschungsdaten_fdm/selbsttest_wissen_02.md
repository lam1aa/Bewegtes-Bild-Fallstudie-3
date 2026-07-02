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
:class: hinweis

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
    "question": """Ein Forschungsteam extrahiert Einzelbilder (Screenshots) aus einem digitalisierten Spielfilm, um damit Farbkompositionen zu analysieren. Welche Aussagen zur Einordnung dieser Screenshots als Forschungsdaten sind korrekt?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Die Screenshots lassen sich eindeutig und ausschließlich als Primärdaten einordnen",
            "correct": False,
            "feedback": """× Falsch: Gerade bei filmwissenschaftlichen Daten ist eine eindeutige Zuordnung oft nicht möglich. Screenshots stellen eine zeitlich selektive, bereits bearbeitete Auswahl aus dem Originalmaterial dar, was für eine Einordnung als Sekundärdaten spricht."""
        },
        {
            "answer": "Die Einordnung als Primär- oder Sekundärdaten ist bei stark heterogenem filmischem Material nicht immer eindeutig möglich",
            "correct": True,
            "feedback": """✓ Richtig: Aufgrund der Heterogenität und Vermischung von Datentypen im Bewegtbildbereich ist eine trennscharfe Kategorisierung häufig nicht möglich, wie am Beispiel von Screenshots oder restaurierten Filmfassungen deutlich wird."""
        },
        {
            "answer": "Auch wenn eine eindeutige Kategorisierung schwierig ist, sollte im Forschungsalltag dennoch eine kategoriale Einordnung angestrebt werden",
            "correct": True,
            "feedback": """✓ Richtig: Für eine gute Dokumentation und Organisation ist es sinnvoll, sowohl nachgenutzte als auch neu erhobene Daten möglichst kategorial zu definieren, auch wenn Grenzfälle bestehen bleiben."""
        },
        {
            "answer": "Da Screenshots digital erzeugt werden, handelt es sich automatisch um born digital materials",
            "correct": False,
            "feedback": """× Falsch: Born digital bezieht sich auf im Ursprung digital entstandene Objekte. Ein aus einem analogen Film extrahiertes und digitalisiertes Bild ist hingegen ein Beispiel für digitale Re-Mediatisierung (datafication) eines analogen Ausgangsmaterials."""
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
    title="Ordnen Sie die folgenden Methoden der Datenerhebung dem jeweils passenden technischen Anforderungsniveau zu:",
    descriptions=[
        "Erstellung von Annotationen mit Advene, ELAN oder VIAN",
        "Abfrage von Filmdaten über eine API-Schnittstelle wie TMDb",
        "Automatisierte Extraktion von Daten aus Webseiten mittels Python-Skripten"
    ],
    options=[
        "Niveau: Basis",
        "Niveau: Fortgeschritten",
        "Niveau: Expert:in"
    ],
    correct_mapping={
        "Erstellung von Annotationen mit Advene, ELAN oder VIAN": "Niveau: Basis",
        "Abfrage von Filmdaten über eine API-Schnittstelle wie TMDb": "Niveau: Fortgeschritten",
        "Automatisierte Extraktion von Daten aus Webseiten mittels Python-Skripten": "Niveau: Expert:in"
    }
)
```

## Aufgabe 3

Bewerten Sie folgende Aussagen zu Forschungsdatenmanagement und FAIR-Prinzipien:

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false1 = [{
    "question": """Der Forschungsdatenlebenszyklus muss in jedem filmwissenschaftlichen Projekt exakt linear und vollständig durchlaufen werden""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Sophie Einwächter weist darauf hin, dass sich Forschungsprozesse nicht linear verhalten und der Zyklus projektspezifisch angepasst werden muss - manche Projekte enden sogar mit der planmäßigen Löschung der Daten."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: Forschungsprozesse sind keine strikte, lineare Aneinanderreihung kategorisierbarer Aktivitäten."""
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
    "question": """Das A in FAIR bedeutet, dass Forschungsdaten grundsätzlich für jede Person ohne jegliche Einschränkung frei zugänglich sein müssen, unabhängig von Datenschutz oder Urheberrecht""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Accessible bedeutet, dass Daten so offen und zugänglich wie möglich gemacht werden sollen (z. B. über offene Protokolle, APIs, Repositorien) - dies schließt jedoch begründete Zugriffsbeschränkungen etwa aus rechtlichen oder datenschutzrechtlichen Gründen nicht aus."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: FAIR fordert maximale, aber keine bedingungslose Offenheit - rechtliche Rahmenbedingungen bleiben immer zu prüfen, gerade bei Filmmaterial und personenbezogenen Daten."""
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
    "question": """Ein Datenmanagementplan (DMP) sollte als einmalig zu erstellendes, danach unverändertes Dokument verstanden werden""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Ein DMP ist ein living document und muss im Projektverlauf angepasst werden, da sowohl Forschung als auch FDM dynamisch und selten linear verlaufen."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: Gerade bei Langzeitprojekten muss der DMP wiederholt aktualisiert werden."""
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
    "question": """Warum betont Sarah-Mai Dang, dass die Nutzung von Daten aus Plattformen wie IMDb kritisch reflektiert werden sollte?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Weil IMDb technisch fehlerhafte Daten liefert, die sich nicht für digitale Analysen eignen",
            "correct": False,
            "feedback": """× Falsch: Das Problem liegt nicht primär in technischer Fehlerhaftigkeit, sondern in inhaltlichen Verzerrungen der Datenauswahl und -bewertung."""
        },
        {
            "answer": "Weil die Auswahl, Gewichtung und Bewertung der Inhalte kommerziellen, soziopolitischen und algorithmischen Logiken unterliegt, die bestimmte Filme und Personengruppen marginalisieren können",
            "correct": True,
            "feedback": """✓ Richtig: Als kommerziell von Amazon betriebene Plattform ist IMDb nicht neutral - Ranking- und Sichtbarkeitsmechanismen sind von diskriminierenden Inklusions- und Exklusionsmechanismen geprägt."""
        },
        {
            "answer": "Weil IMDb ausschließlich fiktionale Angaben zu Filmen bereitstellt",
            "correct": False,
            "feedback": """× Falsch: IMDb liefert reale filmografische Daten, deren Auswahl und Gewichtung jedoch kritisch zu hinterfragen ist."""
        },
        {
            "answer": "Weil eine Nachnutzung von IMDb-Daten grundsätzlich rechtlich verboten ist",
            "correct": False,
            "feedback": """× Falsch: Es gibt z. B. IMDb Non-Commercial Datasets zur eingeschränkten Nachnutzung; relevant ist vor allem die kritische Einordnung der Daten, nicht ein generelles Verbot."""
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
    title="Ordnen Sie die folgenden Forschungsszenarien der jeweils passenden Art der Nachnutzung zu:",
    descriptions=[
        "Vorhandene Annotationsdaten zu Kamerabewegungen werden genutzt, um eine neue Fragestellung zu Bewegungsmustern zu untersuchen",
        "Zwei bestehende Filmkorpora werden gegenübergestellt, um Lücken in der Repräsentation weiblicher Regisseurinnen aufzudecken",
        "Metadaten aus mehreren offenen Filmdatenbanken werden zusammengeführt, um ein neues, angereichertes Datenregister zu erstellen",
        "Ein bestehendes OER-Tutorial zu Annotationstools wird als Übungsmaterial in einem Seminar eingesetzt"
    ],
    options=[
        "Analytische Nachnutzung",
        "Vergleichende Nachnutzung",
        "Kuratierende Nachnutzung",
        "Didaktische Nachnutzung"
    ],
    correct_mapping={
        "Vorhandene Annotationsdaten zu Kamerabewegungen werden genutzt, um eine neue Fragestellung zu Bewegungsmustern zu untersuchen": "Analytische Nachnutzung",
        "Zwei bestehende Filmkorpora werden gegenübergestellt, um Lücken in der Repräsentation weiblicher Regisseurinnen aufzudecken": "Vergleichende Nachnutzung",
        "Metadaten aus mehreren offenen Filmdatenbanken werden zusammengeführt, um ein neues, angereichertes Datenregister zu erstellen": "Kuratierende Nachnutzung",
        "Ein bestehendes OER-Tutorial zu Annotationstools wird als Übungsmaterial in einem Seminar eingesetzt": "Didaktische Nachnutzung"
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
    "question": """Welche der folgenden Aussagen zu Best Practices im filmwissenschaftlichen Forschungsdatenmanagement sind korrekt?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Softwarespezifische Annotationsformate wie .eaf oder .azp sind langfristig unproblematisch und benötigen keine besondere Beachtung bei der Archivierung",
            "correct": False,
            "feedback": """× Falsch: Gerade bei softwarespezifischen Formaten sollte an mögliche Formatmigrationen gedacht werden, um die langfristige Nutzbarkeit zu sichern."""
        },
        {
            "answer": "Eine ausführliche Dokumentation von Auswahl-, Bearbeitungs- und Analyseschritten fördert die Nachnutzbarkeit filmwissenschaftlicher Forschungsdaten",
            "correct": True,
            "feedback": """✓ Richtig: Metadaten und Dokumentationen (z. B. README-Dateien oder Protokolle) zu Entstehung, Auswahl und Bearbeitungsschritten sind zentral für die Nachnutzbarkeit."""
        },
        {
            "answer": "Die Heterogenität filmwissenschaftlicher Daten (Video, Transkripte, Annotationen, Metadaten etc.) erfordert eine klare Strukturierung bereits im Vorfeld des Projekts",
            "correct": True,
            "feedback": """✓ Richtig: Die Vielfalt der Datentypen macht eine frühzeitige, klare Strukturierung notwendig."""
        },
        {
            "answer": "In der Filmwissenschaft existieren bereits seit Langem einheitliche, disziplinweit verbindliche Standards für das Forschungsdatenmanagement",
            "correct": False,
            "feedback": """× Falsch: Laut Dang mangelt es bislang an spezifischen Standardisierungen; Initiativen wie NFDI4Culture arbeiten erst in jüngerer Zeit an entsprechenden Empfehlungen."""
        }
    ]
}]

display_quiz(multiple_choice6, colors=colors.jupyterquiz, max_width=900)
```
## Aufgabe 7

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice7 = [{
    "question": "Welche Vorgaben bezüglich der Bereitstellung und langfristigen Sicherung von Forschungsdaten sind zentrale Bestandteile der DFG-Leitlinien?",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Daten sollen in nutzbarer Form zeitnah bereitgestellt und für mindestens zehn Jahre in institutionellen oder überregionalen Infrastrukturen archiviert werden",
            "correct": True,
            "feedback": "✓ Richtig: Die DFG fordert explizit eine Aufbewahrungsfrist von mindestens 10 Jahren in geeigneten Repositorien sowie eine zeitnahe, nutzbare Bereitstellung der Daten[cite: 7]."
        },
        {
            "answer": "Daten müssen zwingend für immer (unbefristet) ausschließlich auf den lokalen Servern der Forschenden gesichert werden",
            "correct": False,
            "feedback": "× Falsch: Die Daten sollten in institutionellen (z. B. lokales Repositorium) oder fachbezogenen überregionalen Infrastrukturen archiviert werden, nicht zwingend auf lokalen Rechnern[cite: 7]."
        },
        {
            "answer": "Forschungsdaten müssen nur dann gesichert werden, wenn sie fehlerfrei sind; eine Bereitstellungspflicht gibt es nicht, sobald Verwertungsrechte an Verlage übertragen wurden",
            "correct": False,
            "feedback": "× Falsch: Die DFG empfiehlt eine zeitnahe Bereitstellung zur Transparenz und Qualitätssicherung. Der Zugang soll auch bei übertragenen Verwertungsrechten sichergestellt werden[cite: 7]."
        },
        {
            "answer": "Eine Archivierung für exakt 3 Jahre nach Projektende ist gemäß den DFG-Leitlinien für geisteswissenschaftliche Projekte ausreichend",
            "correct": False,
            "feedback": "× Falsch: Die DFG empfiehlt disziplinübergreifend eine Archivierung von mindestens 10 Jahren[cite: 7]."
        }
    ]
}]

display_quiz(single_choice7, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 8

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice8 = [{
    "question": """Ein Projekt nutzt Annotationsdaten eines abgeschlossenen Drittprojekts nach (per offener Lizenz), reichert diese mit eigenen Moviebarcodes an und möchte den kombinierten Datensatz nach FAIR-Prinzipien publizieren. Die Annotationen enthalten Zeitstempel zu Interviewpassagen mit noch lebenden Zeitzeug:innen. Welche der folgenden Einschätzungen sind zutreffend?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Da die ursprünglichen Annotationsdaten bereits offen lizenziert sind, entfällt die Pflicht zur Quellenangabe für das nachnutzende Projekt",
            "correct": False,
            "feedback": """× Falsch: Eine offene Lizenz befreit nicht von der Pflicht zur transparenten Zitation. Nachgenutzte Daten sollten wie wissenschaftliche Publikationen mit vollständiger Quellenangabe behandelt werden - unabhängig vom Lizenzstatus."""
        },
        {
            "answer": "Die Kombination aus offener Lizenz des Drittdatensatzes und personenbezogenen Zeitstempeln zu Interviewpassagen erfordert eine gesonderte Prüfung, ob und wie die Daten FAIR-konform, aber dennoch datenschutzkonform veröffentlicht werden können",
            "correct": True,
            "feedback": """✓ Richtig: FAIR fordert Zugänglichkeit so offen wie möglich, so geschlossen wie nötig - personenbezogene Daten zu lebenden Personen erfordern eine Abwägung zwischen Offenheit und Schutzpflichten, unabhängig von der Lizenz der nachgenutzten Basisdaten."""
        },
        {
            "answer": "Die eigens erstellten Moviebarcodes müssen nicht separat dokumentiert werden, da sie lediglich eine visuelle Ergänzung bereits vorhandener Annotationsdaten darstellen",
            "correct": False,
            "feedback": """× Falsch: Auch neu erzeugte Sekundärdaten wie Moviebarcodes benötigen eigene Prozessdokumentation (Entstehung, verwendete Software/Methodik), um dem Interoperabilitäts- und Nachnutzbarkeitsanspruch der FAIR-Prinzipien zu genügen."""
        },
        {
            "answer": "Eine vollständige FAIR-konforme Publikation ist in diesem Fall grundsätzlich ausgeschlossen, sobald personenbezogene Daten enthalten sind",
            "correct": False,
            "feedback": """× Falsch: FAIR schließt personenbezogene Daten nicht kategorisch aus - vielmehr erlaubt das Accessible-Prinzip auch kontrollierte oder eingeschränkte Zugänge (z. B. nach Antrag), sofern Auffindbarkeit und Dokumentation trotzdem gegeben sind."""
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
    "question": """Sophie Einwächter kritisiert, dass sich der klassische Forschungsdatenlebenszyklus vorrangig am Management quantitativer Daten orientiert. Was ist die treffendste Begründung dafür, warum dieses Modell für viele filmwissenschaftliche Projekte angepasst werden muss?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Weil filmwissenschaftliche Forschungsdaten grundsätzlich nicht digitalisierbar sind und sich daher keinem Lebenszyklus zuordnen lassen",
            "correct": False,
            "feedback": """× Falsch: Filmwissenschaftliche Daten werden im Kapitel gerade als digitalisierbar und managebar beschrieben (z. B. Annotationen, Digitalisate) - das Problem liegt nicht in der Digitalisierbarkeit."""
        },
        {
            "answer": "Weil filmwissenschaftliche Forschungsprozesse oft nicht-linear verlaufen, mit iterativen Rückkopplungen zwischen Erhebung, Analyse und erneuter Datengenerierung, was dem phasenhaften, sequentiellen Charakter des klassischen Zyklus widerspricht",
            "correct": True,
            "feedback": """✓ Richtig: Der Text betont explizit, dass Forschungsprozesse keine Aneinanderreihung von kategorisierbaren Aktivitäten sind - die Nicht-Linearität qualitativ-hermeneutischer Analyseprozesse steht im Kontrast zum sequentiellen Zyklus-Modell, das eher für standardisierte quantitative Erhebungen passt."""
        },
        {
            "answer": "Weil der Lebenszyklus keine Archivierungsphase vorsieht, filmwissenschaftliche Projekte diese aber zwingend benötigen",
            "correct": False,
            "feedback": """× Falsch: Der klassische Zyklus umfasst durchaus eine Archivierungsphase - das eigentliche Problem ist die unterstellte Linearität und feste Abfolge der Phasen, nicht deren Vollständigkeit."""
        },
        {
            "answer": "Weil ausschließlich personenbezogene Daten eine Anpassung des Zyklus erfordern, alle anderen Datentypen aber problemlos dem Modell folgen können",
            "correct": False,
            "feedback": """× Falsch: Einwächter nennt den Umgang mit personenbezogenen Daten als ein Beispiel unter mehreren, nicht als alleinigen Grund - auch reine Löschprojekte oder nicht-lineare Analyseprozesse erfordern Anpassungen."""
        }
    ]
}]

display_quiz(single_choice9, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 10

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false4 = [{
    "question": """Ein Projekt, das seine Forschungsdaten konsequent nach den FAIR-Prinzipien aufbereitet, erfüllt damit automatisch auch alle drei Kernpunkte der DFG-Leitlinien zum Umgang mit Forschungsdaten""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! FAIR deckt zentrale Aspekte wie Auffindbarkeit, Zugänglichkeit und Nachnutzbarkeit ab, ersetzt aber nicht die DFG-Kernpunkte zur Projektplanung (frühzeitige Konzeption bereits vor Datenentstehung) - FAIR setzt eher am fertigen Datenprodukt an, während die DFG-Leitlinien den gesamten Planungsprozess von Anfang an mitdenken."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: FAIR und die DFG-Leitlinien überschneiden sich zwar in wesentlichen Punkten (Bereitstellung, langfristige Sicherung), doch die DFG-Leitlinien beginnen explizit bereits bei der Projektplanungsphase - ein Aspekt, den die FAIR-Prinzipien selbst nicht direkt adressieren."""
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
    "question": """Wenn ein Datensatz vollständig in einem offen zugänglichen Repositorium ohne jegliche Zugriffsbeschränkung liegt, ist das A (Accessible) der FAIR-Prinzipien in jedem Fall optimal erfüllt""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Falsch",
            "correct": True,
            "feedback": """✓ Korrekt! Accessible bedeutet so offen und zugänglich wie möglich - bei sensiblen oder personenbezogenen Inhalten (z. B. Interviews mit Zeitzeug:innen) kann eine unbeschränkte Offenheit sogar rechtlich und ethisch problematisch sein. Kontrollierter Zugang bei klarer Dokumentation der Zugriffsbedingungen erfüllt das Prinzip ebenso, unbeschränkte Offenheit allein ist kein Selbstzweck."""
        },
        {
            "answer": "Richtig",
            "correct": False,
            "feedback": """× Nicht korrekt: Maximale technische Offenheit ohne Berücksichtigung von Datenschutz oder Urheberrecht kann FAIR sogar widersprechen, da so offen wie möglich immer im Kontext rechtlicher und ethischer Grenzen zu verstehen ist."""
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
    title="Ordnen Sie die folgende Projektsituation dem FAIR-Prinzip zu, das dabei am stärksten verletzt wird:",
    descriptions=[
        "Annotationsdaten liegen ausschließlich in einem proprietären, softwarespezifischen Format vor, das nur mit einer inzwischen eingestellten Anwendung geöffnet werden kann",
        "Ein Forschungsdatensatz ist zwar über eine private Institutsseite ohne Suchfunktion und ohne DOI abrufbar, aber niemand außerhalb des Projekts weiß von seiner Existenz",
        "Ein Datensatz liegt offen zugänglich in einem Repositorium, enthält aber keinerlei Dokumentation zu Erhebungsmethode, Lizenz oder Entstehungskontext",
        "Der Zugriff auf sensible Videointerviews wird grundsätzlich verweigert, obwohl die begleitenden Metadaten vollständig offen einsehbar und mit klaren Beantragungswegen versehen sind"
    ],
    options=[
        "Interoperable (I) verletzt",
        "Findable (F) verletzt",
        "Reusable (R) verletzt",
        "Kein FAIR-Prinzip klar verletzt"
    ],
    correct_mapping={
        "Annotationsdaten liegen ausschließlich in einem proprietären, softwarespezifischen Format vor, das nur mit einer inzwischen eingestellten Anwendung geöffnet werden kann": "Interoperable (I) verletzt",
        "Ein Forschungsdatensatz ist zwar über eine private Institutsseite ohne Suchfunktion und ohne DOI abrufbar, aber niemand außerhalb des Projekts weiß von seiner Existenz": "Findable (F) verletzt",
        "Ein Datensatz liegt offen zugänglich in einem Repositorium, enthält aber keinerlei Dokumentation zu Erhebungsmethode, Lizenz oder Entstehungskontext": "Reusable (R) verletzt",
        "Der Zugriff auf sensible Videointerviews wird grundsätzlich verweigert, obwohl die begleitenden Metadaten vollständig offen einsehbar und mit klaren Beantragungswegen versehen sind": "Kein FAIR-Prinzip klar verletzt"
    }
)
```

## Aufgabe 12

**Szenario:** Sie beginnen ein neues filmwissenschaftliches Forschungsprojekt zur Darstellung von Klimawandel in Naturdokumentationen. Sie planen, ca. 40 Dokumentarfilme zu analysieren, dafür Annotationen mit ELAN zu erstellen und zusätzlich Metadaten aus einer offenen Filmdatenbank per API nachzunutzen.

Beschreiben Sie:
1. Welche zentralen Bereiche Sie in Ihrem Datenmanagementplan berücksichtigen müssten
2. Welche rechtlichen und ethischen Aspekte bei der Nachnutzung der API-Daten zu beachten sind
3. Wie Sie die spätere Nachnutzbarkeit Ihrer eigenen Annotationsdaten sicherstellen würden

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_2-12')
```

````{admonition} Musterlösung
:class: solution, dropdown

**1. Zentrale Bereiche des Datenmanagementplans:**
- **Art und Datentypen der Daten**: Primärdaten (Filme), Sekundärdaten (ELAN-Annotationen, nachgenutzte Metadaten)
- **Datengewinnung**: Einsatz von ELAN, verwendete API und deren Nutzungsbedingungen
- **Speicherung & Speicherlösungen**: Backup-Strategie für Annotationsdateien, Speicherort während der Projektlaufzeit
- **Datenorganisation**: Einheitliche Benennungskonventionen und Ordnerstruktur für Annotationsdateien
- **Rechtliche Aspekte**: Umgang mit urheberrechtlich geschütztem Filmmaterial und Lizenzbedingungen der API-Daten
- **Archivierung & Veröffentlichung**: Repositorium (z. B. media/rep/), persistenter Identifier (DOI)

**2. Rechtliche und ethische Aspekte bei API-Nachnutzung:**
- Prüfung der Lizenzbedingungen und Nutzungsrechte der jeweiligen API (kommerziell vs. nicht-kommerziell)
- Transparente Zitation der Datenquelle inkl. Herkunft, Kontext und ggf. DOI
- Kritische Reflexion möglicher Verzerrungen (Bias) in den nachgenutzten Metadaten, z. B. hinsichtlich Repräsentation oder Bewertungslogiken der Plattform
- Beachtung von Datenschutzbestimmungen, falls personenbezogene Daten enthalten sind

**3. Sicherstellung der Nachnutzbarkeit eigener Annotationsdaten:**
- Ausführliche Dokumentation der Annotationsmethodik (verwendete Kategorien, Analysesystematik)
- Nutzung offener/interoperabler Formate bzw. Bewusstsein für Formatmigration bei .eaf-Dateien
- Bereitstellung einer README-Datei mit Angaben zu Entstehung, Software-Version und Bearbeitungsschritten
- Anwendung der FAIR-Prinzipien: auffindbar (Metadaten/DOI), zugänglich (Repositorium), interoperabel (offene Formate), nachnutzbar (Lizenz, Dokumentation)
````

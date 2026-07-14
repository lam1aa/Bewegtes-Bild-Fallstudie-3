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
Diese Übungsaufgaben dienen Ihrer Selbsteinschätzung und helfen Ihnen, das im Kapitel Gelernte auf neue Fälle anzuwenden - nicht, Formulierungen aus dem Kapitel wiederzuerkennen.

Sie können die Fragen in beliebiger Reihenfolge bearbeiten und die Beantwortung auch mehrfach versuchen.

**So funktioniert es:**
- Wählen Sie bei jeder Frage die Antwort(en) aus, die Sie für richtig halten
- Lesen Sie das Feedback zu den einzelnen Antwortoptionen sorgfältig durch
- Die Erklärungen helfen Ihnen, Ihr Verständnis zu vertiefen – auch bei korrekten Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse.

**Geschätzte Zeit**: XX Minuten

Viel Erfolg!
````

## Aufgabe 1

Ein neues, kleines Forschungsprojekt zur Stummfilmgeschichte plant die Publikation seines Datensets. Es gibt nur eine einzige verantwortliche Person, es sind keine größeren Aktualisierungen nach der Publikation zu erwarten, aber der Datensatz soll fachspezifisch für die Medienwissenschaft auffindbar sein und dauerhaft (mind. zehn Jahre) verfügbar bleiben.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice1 = [{
    "question": """Welche Einschätzungen zur Wahl der Publikationsinfrastruktur(en) sind sinnvoll?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Da keine kollaborative Weiterentwicklung geplant ist, lohnt sich eine Kombination aus GitHub und Zenodo grundsätzlich nicht mehr",
            "correct": False,
            "feedback": """× Falsch: GitHub+Zenodo eignet sich nicht nur für aktiv weiterentwickelte Projekte, sondern bietet unabhängig davon eine versionierte, DOI-fähige Publikation - ein sinnvoller erster Schritt, auch ohne geplante Weiterentwicklung."""
        },
        {
            "answer": "Für die geforderte Langzeitverfügbarkeit und fachspezifische Sichtbarkeit sollte zusätzlich ein Fachrepositorium wie FID Media in Betracht gezogen werden",
            "correct": True,
            "feedback": """✓ Richtig: Fachrepositorien wie FID Media sind speziell auf die fachspezifische Auffindbarkeit in der Medienwissenschaft ausgelegt und ergänzen die technische Publikation auf GitHub/Zenodo sinnvoll."""
        },
        {
            "answer": "Ein institutionelles Repositorium (z. B. der eigenen Hochschule) kann ergänzend zur dauerhaften Archivierung genutzt werden, auch wenn GitHub/Zenodo bereits verwendet wird",
            "correct": True,
            "feedback": """✓ Richtig: Institutionelle Repositorien dienen primär der Langzeitarchivierung und schließen eine parallele technische Publikation auf GitHub/Zenodo nicht aus - beide Wege ergänzen sich."""
        },
        {
            "answer": "Ohne kollaborative Weiterentwicklung ist ein Repositorien-Finder wie re3data überflüssig, da ohnehin nur eine einzige Plattform infrage kommt",
            "correct": False,
            "feedback": """× Falsch: Repositorien-Finder helfen unabhängig von der Teamgröße dabei, passende, fachspezifische oder institutionelle Repositorien überhaupt erst zu identifizieren."""
        }
    ]
}]

display_quiz(multiple_choice1, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 2

In einem Repository entdecken Sie folgende Commit-Historie:

```text
feat: add corpus metadata CSV
fix: correct country code for Geostorm
feat: add corpus metadata CSV
fix: correct country code for Geostorm
update: minor formatting
```

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice2 = [{
    "question": """Was lässt sich aus dieser (fiktiven, stark vereinfachten) Commit-Historie über gute Versionskontrolle ableiten?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Da Commits ohnehin nur intern sichtbar sind, spielt die Formulierung der Commit Message für die Nachnutzbarkeit keine Rolle",
            "correct": False,
            "feedback": """× Falsch: Commit Messages sind auf GitHub öffentlich sichtbar und Teil der Versionsgeschichte - sie helfen auch externen Nutzenden, Änderungen am Datensatz nachzuvollziehen."""
        },
        {
            "answer": "Jeder einzelne Commit sollte grundsätzlich eine möglichst große Menge an Änderungen bündeln, um die Anzahl der Commits gering zu halten",
            "correct": False,
            "feedback": """× Falsch: Zu große, unübersichtliche Commits erschweren die Nachvollziehbarkeit einzelner Änderungen - kleinteiligere, klar benannte Commits sind grundsätzlich besser nachvollziehbar."""
        },
        {
            "answer": "Klar formulierte Commit Messages nach einem einheitlichen Schema (z. B. feat/fix/update) erleichtern es, die Art einer Änderung auch ohne Blick in den Diff einzuordnen",
            "correct": True,
            "feedback": """✓ Richtig: Ein einheitliches Präfix-Schema wie bei Conventional Commits macht auf einen Blick erkennbar, ob es sich um eine neue Funktion, eine Korrektur oder eine Aktualisierung handelt."""
        },
        {
            "answer": "Ein Git-Commit dokumentiert neben der inhaltlichen Änderung auch automatisch, wer sie zu welchem Zeitpunkt vorgenommen hat",
            "correct": True,
            "feedback": """✓ Richtig: Jeder Commit erhält eine eindeutige ID, die Änderung, Zeitpunkt und Urheber:in der Änderung dokumentiert - unabhängig vom Wortlaut der Commit Message."""
        }
    ]
}]

display_quiz(single_choice2, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 3

**Szenario:** Ein Datensatz liegt aktuell in Version `2.3.1` vor. Es treten nun vier verschiedene Änderungen auf.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Ordnen Sie jede Änderung der resultierenden neuen Versionsnummer zu:",
    descriptions=[
        "Ein Tippfehler in einer Beschreibung wird korrigiert, sonst ändert sich nichts",
        "Ein neues optionales Metadatenfeld wird ergänzt, alle bisherigen Anwendungen funktionieren unverändert weiter",
        "Das komplette Metadatenschema wird umstrukturiert, bestehende Skripte anderer Nutzender funktionieren dadurch nicht mehr",
        "Der Datensatz wird zur breiten Testung veröffentlicht, ist aber noch nicht vollständig stabil"
    ],
    options=[
        "2.3.2 (PATCH)",
        "2.4.0 (MINOR)",
        "3.0.0 (MAJOR)",
        "3.0.0-beta.1 (Pre-Release)"
    ],
    correct_mapping={
        "Ein Tippfehler in einer Beschreibung wird korrigiert, sonst ändert sich nichts": "2.3.2 (PATCH)",
        "Ein neues optionales Metadatenfeld wird ergänzt, alle bisherigen Anwendungen funktionieren unverändert weiter": "2.4.0 (MINOR)",
        "Das komplette Metadatenschema wird umstrukturiert, bestehende Skripte anderer Nutzender funktionieren dadurch nicht mehr": "3.0.0 (MAJOR)",
        "Der Datensatz wird zur breiten Testung veröffentlicht, ist aber noch nicht vollständig stabil": "3.0.0-beta.1 (Pre-Release)"
    }
)
```

## Aufgabe 4

Ein neues filmwissenschaftliches Korpus enthält:  
(a) ein selbst entwickeltes Metadatenschema, das möglichst breit - auch kommerziell - weiterverwendet werden soll,  
(b) handschriftliche Analyseannotationen der Forschenden, die als eigenständige wissenschaftliche Leistung gelten sollen und bei Weiterverbreitung unter denselben Bedingungen zugänglich bleiben sollen,   
(c) Screenshots aus urheberrechtlich geschützten Spielfilmen.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice4 = [{
    "question": """Welche Lizenzierungsentscheidungen passen zu diesen drei Ressourcen?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Für das Metadatenschema (a) eignet sich CC0, da ein möglichst uneingeschränkter Rechteverzicht einer breiten, auch kommerziellen Nachnutzung am ehesten entspricht",
            "correct": True,
            "feedback": """✓ Richtig: CC0 verzichtet vollständig auf Rechte und ermöglicht so die größtmögliche Offenheit für jede Art der Weiterverwendung, auch kommerziell."""
        },
        {
            "answer": "Für die Annotationen (b) eignet sich CC BY-SA, da dieses Modul die Weitergabe nur unter derselben Lizenz erlaubt und zugleich Namensnennung sichert",
            "correct": True,
            "feedback": """✓ Richtig: Das SA-Modul (Share Alike) verpflichtet Nachnutzende, Bearbeitungen unter derselben Lizenz weiterzugeben, während BY die Namensnennung als wissenschaftliche Leistung sicherstellt."""
        },
        {
            "answer": "Die Screenshots (c) können ohne weitere Prüfung unter einer offenen CC-Lizenz publiziert werden, da Screenshots per se keine urheberrechtlich relevanten Bestandteile des Originalfilms mehr enthalten",
            "correct": False,
            "feedback": """× Falsch: Screenshots aus geschütztem Filmmaterial bleiben Primärdaten und unterliegen weiterhin dem Urheberrecht des Ursprungswerks - eine offene Lizenzierung ist ohne eingeholte Rechte oder Public-Domain-Status nicht ohne Weiteres möglich."""
        },
        {
            "answer": "Da alle drei Ressourcen Teil desselben Datensets sind, muss projektweit einheitlich nur eine einzige Lizenz vergeben werden",
            "correct": False,
            "feedback": """× Falsch: Je nach Art der Ressource (Primär- vs. Sekundärdaten, Software vs. kreative Inhalte) sind unterschiedliche Lizenzmodelle notwendig - eine Mehrfachlizenzierung innerhalb eines Datensets ist üblich und sinnvoll."""
        }
    ]
}]

display_quiz(multiple_choice4, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 5

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

true_false5 = [{
    "question": """Ein Projekt veröffentlicht seinen Datensatz zunächst unter CC BY 4.0. Ein Jahr später möchte es aus strategischen Gründen zu CC BY-NC wechseln, um zukünftig kommerzielle Nachnutzung auszuschließen. Bereits veröffentlichte Kopien und Weiterverwendungen der ursprünglichen Version dürfen weiterhin gemäß CC BY 4.0 genutzt werden.""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Richtig",
            "correct": True,
            "feedback": """✓ Korrekt! CC-Lizenzen sind unwiderruflich: Einmal unter einer bestimmten Lizenz veröffentlichte Stände bleiben unter dieser Lizenz nutzbar. Ein Lizenzwechsel wirkt nur für neue Versionen, nicht rückwirkend."""
        },
        {
            "answer": "Falsch",
            "correct": False,
            "feedback": """× Nicht korrekt"""
        }
    ]
}]

display_quiz(true_false5, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 6

Ein Kollege legt für ein neues Korpusprojekt folgende Ordnerstruktur an:

```text
projekt/
├── data/
│   ├── typ_a/
│   │   ├── unterordner_1/
│   │   │   ├── unterordner_1a/
│   │   │   │   └── datei.csv
├── endgueltig/
│   └── Beispieldatei_FINAL_wirklich_neu.csv
└── sonstiges/
```

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice6 = [{
    "question": """Welche Probleme lassen sich anhand dieser Struktur im Hinblick auf gute Praxis bei Ordnerstrukturen und Dateibenennung identifizieren?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Die Verschachtelung von `data/typ_a/unterordner_1/unterordner_1a/` überschreitet die empfohlene maximale Tiefe von drei Unterordner-Ebenen",
            "correct": True,
            "feedback": """✓ Richtig: Vier Ebenen unterhalb des Root-Verzeichnisses überschreiten die empfohlene Obergrenze von maximal drei Unterordner-Ebenen und erschweren die Übersichtlichkeit."""
        },
        {
            "answer": "Der Dateiname `Beispieldatei_FINAL_wirklich_neu.csv` signalisiert keinen klar nachvollziehbaren Versionsstand und ist damit ungeeignet",
            "correct": True,
            "feedback": """✓ Richtig: Bezeichnungen wie 'FINAL', 'wirklich', 'neu' lassen keine sinnvolle Sortierung zu und sind für Außenstehende nicht interpretierbar - ein klares Versionsschema (z. B. v1-0, v1-1) wäre vorzuziehen."""
        },
        {
            "answer": "Ordnernamen wie `sonstiges` sind unproblematisch, da eine Ordnerstruktur ohnehin nur der eigenen Übersicht dient und nicht für Dritte verständlich sein muss",
            "correct": False,
            "feedback": """× Falsch: Eine gute Ordnerstruktur muss auch externen Nutzenden erschließen, wo welche Daten liegen - generische, nicht-selbsterklärende Namen wie 'sonstiges' widersprechen diesem Prinzip."""
        },
        {
            "answer": "Da keine Leerzeichen oder Sonderzeichen im Dateinamen vorkommen, ist der Dateiname `Beispieldatei_FINAL_wirklich_neu.csv` insgesamt unproblematisch",
            "correct": False,
            "feedback": """× Falsch: Maschinenlesbarkeit (keine Leerzeichen/Sonderzeichen) ist nur eines von mehreren Kriterien - der Name muss zusätzlich selbsterklärend sein und einen nachvollziehbaren Versionsstand signalisieren, was hier nicht der Fall ist."""
        }
    ]
}]

display_quiz(multiple_choice6, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 7

**Szenario:** Ein Team arbeitet ausschließlich über einen Cloud-Speicher ohne Git-Versionskontrolle an einem wachsenden Korpus. Bisher werden Dateien einfach überschrieben, sobald jemand Änderungen vornimmt.

Entwickeln Sie eine Strategie zur Absicherung und Versionierung der Daten:
1. Welches einfache, nicht-Git-basierte Versionierungsschema würden Sie vorschlagen und warum?
2. Welche Backup-Strategie würden Sie empfehlen, um Datenverlust zu vermeiden?
3. Welche organisatorischen Maßnahmen (jenseits der Technik) sind notwendig, damit die Strategie im Projektalltag funktioniert?

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_K6-7')
```

````{admonition} Musterlösung
:class: solution, dropdown

**1. Versionierungsschema ohne Git:**
- Ein aus SemVer abgeleitetes, vereinfachtes Schema im Dateinamen (z. B. `korpus_v1-0.csv` → `korpus_v1-1.csv` für kleinere, `korpus_v2-0.csv` für größere Änderungen) macht Änderungen auch ohne Versionskontrolle sichtbar.
- Ergänzend sollte ein `CHANGELOG.md` oder eine Versionstabelle mit Datum, Bearbeiter:in und Art der Änderung gepflegt werden, um den Änderungsverlauf nachvollziehbar zu dokumentieren.

**2. Backup-Strategie:**
- Anwendung der 3-2-1-Regel: mindestens drei Kopien der Daten, auf mindestens zwei unterschiedlichen Speichermedien, davon eine an einem externen Standort.
- Automatische statt manuelle Backups bevorzugen, um menschliche Fehler oder Vergessen zu vermeiden.
- Regelmäßige Kontrolle, ob aus dem Backup tatsächlich erfolgreich wiederhergestellt werden kann.

**3. Organisatorische Maßnahmen:**
- Eine verantwortliche Person für Backups und Versionierung festlegen, um Unklarheiten zu vermeiden.
- Klare, für alle zugängliche Regeln zur Dateibenennung und zum Umgang mit Versionsständen dokumentieren (z. B. in einer projektinternen README).
- Aufbewahrungsdauer und Löschregeln für Backups im Vorfeld festlegen, idealerweise bereits im Datenmanagementplan verankert.
````

## Aufgabe 8

Ein Datensatz wurde auf Zenodo veröffentlicht und hat eine DOI erhalten. Die zugehörige `CITATION.cff` enthält jedoch nur Titel und Autor:innen, aber keine DOI und keine Versionsangabe.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice8 = [{
    "question": """Welche Einschätzung zu diesem Fall ist zutreffend?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Da die DOI ohnehin automatisch auf Zenodo sichtbar ist, muss sie nicht zusätzlich in der `CITATION.cff` eingetragen werden",
            "correct": False,
            "feedback": """× Falsch: Damit maschinenlesbare, konsistente Zitationsangaben direkt aus dem Repository heraus nutzbar sind, sollte die DOI explizit in der `CITATION.cff` ergänzt werden, statt sich allein auf die Sichtbarkeit auf Zenodo zu verlassen."""
        },
        {
            "answer": "Die fehlende DOI- und Versionsangabe sollte ergänzt werden, damit die `CITATION.cff` ihre Funktion als vollständige, maschinenlesbare Zitationsquelle erfüllen kann",
            "correct": True,
            "feedback": """✓ Richtig: Eine `CITATION.cff` soll eindeutig und vollständig dokumentieren, wie ein Datensatz zu zitieren ist - dazu gehören auch persistente Identifikatoren wie die DOI und eine klare Versionsangabe."""
        },
        {
            "answer": "Ein persistenter Identifikator wie eine DOI ist bei Forschungsdaten grundsätzlich optional und nur für klassische Textpublikationen relevant",
            "correct": False,
            "feedback": """× Falsch: PIDs wie die DOI sind auch für Forschungsdaten zentral, um sie dauerhaft auffindbar und eindeutig zitierbar zu machen - unabhängig vom Publikationstyp."""
        },
        {
            "answer": "Fehler in der `CITATION.cff` lassen sich vor der Publikation nicht systematisch überprüfen, sondern nur durch manuelles Gegenlesen",
            "correct": False,
            "feedback": """× Falsch: Tools wie ein CITATION.cff-Generator/Validator ermöglichen eine systematische Prüfung auf Vollständigkeit und Korrektheit, statt sich allein auf manuelles Gegenlesen zu verlassen."""
        }
    ]
}]

display_quiz(single_choice8, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 9

Ein Projektmitglied speichert alle Forschungsdaten ausschließlich auf einem einzigen externen USB-Stick, der sicher im Büroschrank verschlossen wird.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice9 = [{
    "question": """Wie ist diese Backup-Strategie im Sinne der 3-2-1-Regel und der Anforderungen an Langzeitverfügbarkeit einzuschätzen?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Die Strategie ist ausreichend, da der USB-Stick physisch sicher verschlossen und damit vor Diebstahl geschützt ist",
            "correct": False,
            "feedback": """× Falsch: Physische Sicherheit vor Diebstahl schützt nicht vor anderen Risiken wie Hardwaredefekten, Datenverlust durch Abnutzung oder einem einzigen Störfall (z. B. Brand, Wasserschaden) am Aufbewahrungsort."""
        },
        {
            "answer": "Die Strategie verstößt gegen die 3-2-1-Regel, da nur eine einzige Kopie auf einem einzigen Speichertyp an einem einzigen Ort vorliegt",
            "correct": True,
            "feedback": """✓ Richtig: Die 3-2-1-Regel fordert mindestens drei Kopien auf mindestens zwei verschiedenen Speichertypen, davon eine an einem externen Standort - eine einzelne USB-Stick-Kopie erfüllt keines dieser Kriterien vollständig."""
        },
        {
            "answer": "USB-Sticks sind grundsätzlich ungeeignet, um die für gute wissenschaftliche Praxis geforderte Aufbewahrungsdauer von mindestens zehn Jahren zuverlässig zu garantieren",
            "correct": True,
            "feedback": """✓ Richtig: Tragbare Speichermedien wie USB-Sticks können die geforderte Mindestaufbewahrungsdauer von zehn Jahren nicht zuverlässig garantieren und sind daher nicht für die alleinige Langzeitsicherung geeignet."""
        },
        {
            "answer": "Ein Backup auf einem USB-Stick ersetzt vollständig die Notwendigkeit einer späteren Langzeitarchivierung in einem Repositorium",
            "correct": False,
            "feedback": """× Falsch: Ein Backup sichert den Arbeitsstand während des Projekts, ersetzt aber keine langfristige, strukturierte Archivierung in einem dafür vorgesehenen Repositorium."""
        }
    ]
}]

display_quiz(single_choice9, colors=colors.jupyterquiz, max_width=900)
```

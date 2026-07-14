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

Sie entwerfen ein Metadatenschema für ein neues Korpus zu studentischen Kurzfilmen. Ein Kollege schlägt vor, ein Feld `festival_teilnahme` hinzuzufügen, das angibt, ob ein Film auf einem Festival gezeigt wurde, und ein weiteres Feld `sprache_farbe`, das gleichzeitig Originalsprache und Angabe zu Farb-/Schwarzweißfilm kombiniert.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice1 = [{
    "question": """Welche Einschätzungen zu diesem Schemaentwurf sind aus Sicht guter Metadatenmodellierung zutreffend?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "`sprache_farbe` verstößt gegen das Prinzip klarer Datenmodellierung, da zwei unabhängige Informationen in einem Feld vermischt werden",
            "correct": True,
            "feedback": """✓ Richtig: Ein Feld sollte jeweils eine klar abgrenzbare Information enthalten, damit gezielt gefiltert und maschinell ausgewertet werden kann. Zwei unabhängige Dimensionen (Sprache, Farbe) gehören in getrennte Felder."""
        },
        {
            "answer": "`festival_teilnahme` sollte nur zugelassen werden, wenn dafür ein kontrolliertes Vokabular oder ein klarer Wertetyp (z. B. Boolean) definiert wird, statt Freitext zuzulassen",
            "correct": True,
            "feedback": """✓ Richtig: Ohne kontrolliertes Vokabular oder festen Datentyp drohen inkonsistente Werte (z. B. 'ja', 'Ja', 'teilgenommen', 'X'), die die maschinelle Auswertbarkeit einschränken."""
        },
        {
            "answer": "Da beide Felder projektspezifisch sind, ist ein Mapping auf Dublin Core oder EN 15744 grundsätzlich unmöglich und auch nicht notwendig",
            "correct": False,
            "feedback": """× Falsch: Projektspezifische Felder ohne direkte Standard-Entsprechung sind möglich und legitim, sollten aber trotzdem dokumentiert werden - ein fehlendes Mapping ist kein Freibrief für inkonsistente Feldgestaltung."""
        },
        {
            "answer": "Beide Felder sollten in snake_case benannt werden, um Kompatibilität mit anderen Datensystemen sicherzustellen",
            "correct": True,
            "feedback": """✓ Richtig: Einheitliche, maschinenlesbare Benennungskonventionen wie snake_case sind unabhängig vom Inhalt eines Feldes ein Grundprinzip konsistenter Datenmodellierung."""
        }
    ]
}]

display_quiz(multiple_choice1, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 2

Ein neues Forschungsprojekt möchte eigene Identifier für audiovisuelle Ressourcen vergeben und diskutiert vier Varianten.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice2 = [{
    "question": """Welche der folgenden Identifier-Varianten verstoßen gegen zentrale Anforderungen an gute Identifier (Eindeutigkeit, Persistenz, Maschinenlesbarkeit, Referenzierbarkeit)?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Ein Identifier nach dem Muster Titel_Jahr, z. B. 'Nomadland_2020'",
            "correct": True,
            "feedback": """✓ Richtig: Titel können sich ändern, in mehreren Sprachen vorliegen oder Sonderzeichen enthalten, was die dauerhafte Eindeutigkeit und Maschinenlesbarkeit gefährdet - genau das Problem, das im Kapitel am Beispiel 'avatar_2009' diskutiert wird."""
        },
        {
            "answer": "Ein fortlaufender numerischer Code ohne jede inhaltliche Struktur, z. B. '000452'",
            "correct": False,
            "feedback": """× Nicht zwingend problematisch: Ein rein numerischer, fortlaufender Code kann durchaus eindeutig, persistent und maschinenlesbar sein - er ist lediglich weniger informativ als ein strukturierter Identifier mit Präfix/Suffix-Logik."""
        },
        {
            "answer": "Ein Identifier, der bei jeder inhaltlichen Überarbeitung der Metadaten neu vergeben wird",
            "correct": True,
            "feedback": """✓ Richtig: Dies verletzt das Prinzip der Persistenz. Ein Identifier muss dauerhaft stabil bleiben, auch wenn sich Titel oder andere Metadaten ändern, da er sonst seine Funktion als verlässlicher Verweis verliert."""
        },
        {
            "answer": "Ein Identifier mit Leerzeichen und Umlauten, z. B. 'Film Nr. 5 – Überarbeitet'",
            "correct": True,
            "feedback": """✓ Richtig: Leerzeichen, Umlaute und Sonderzeichen beeinträchtigen die Maschinenlesbarkeit und können bei automatisierter Verarbeitung zu Fehlern führen."""
        }
    ]
}]

display_quiz(multiple_choice2, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 3

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Ordnen Sie jedes Nutzungsszenario dem Dateiformat zu, das dafür am besten geeignet ist:",
    descriptions=[
        "Ein technisch weniger versierter Nutzer möchte im Browser gezielt nach einzelnen Filmtiteln suchen und filtern, ohne Software zu installieren",
        "Eine App soll die Metadaten automatisch abrufen und dabei auch verschachtelte Zusatzinformationen (z. B. mehrere Schlagwort-Kategorien pro Film) verarbeiten",
        "Das Projektteam möchte weiterhin bequem mit mehreren Tabellenblättern, Kommentaren und Formeln arbeiten, bevor die Daten veröffentlicht werden",
        "Die Daten sollen so einfach wie möglich mit praktisch jeder Software, auch in 15 Jahren noch, gelesen werden können"
    ],
    options=[
        "HTML",
        "JSON",
        "XLSX",
        "CSV"
    ],
    correct_mapping={
        "Ein technisch weniger versierter Nutzer möchte im Browser gezielt nach einzelnen Filmtiteln suchen und filtern, ohne Software zu installieren": "HTML",
        "Eine App soll die Metadaten automatisch abrufen und dabei auch verschachtelte Zusatzinformationen (z. B. mehrere Schlagwort-Kategorien pro Film) verarbeiten": "JSON",
        "Das Projektteam möchte weiterhin bequem mit mehreren Tabellenblättern, Kommentaren und Formeln arbeiten, bevor die Daten veröffentlicht werden": "XLSX",
        "Die Daten sollen so einfach wie möglich mit praktisch jeder Software, auch in 15 Jahren noch, gelesen werden können": "CSV"
    }
)
```

## Aufgabe 4

Sie konvertieren einen neuen Datensatz von CSV nach JSON. Die CSV-Datei enthält ein Feld `bewertung` mit Werten wie `7.5`, ein Feld `mehrfachregie` mit `TRUE`/`FALSE` und ein Feld `anmerkung`, das für viele Zeilen leer ist.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice4 = [{
    "question": """Welche Vorgehensweise bei der Konvertierung entspricht den im Kapitel vorgestellten Prinzipien einer sinnvollen, verlustarmen Typkonvertierung?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "`bewertung` wird als Dezimalzahl (float) gespeichert, `mehrfachregie` als JSON-Boolean, leere `anmerkung`-Felder werden als leere Zeichenkette beibehalten",
            "correct": True,
            "feedback": """✓ Richtig: Numerische Werte sollten als Zahlen gespeichert werden, um sie maschinell weiterverarbeiten zu können; TRUE/FALSE gehört als echter Boolean kodiert; leere Felder bleiben als leere Strings erhalten, um die tabellarische Struktur (gleiche Anzahl an Feldern pro Objekt) zu wahren."""
        },
        {
            "answer": "Alle Werte werden unabhängig von ihrem Typ als Text (String) belassen, um Konvertierungsfehler von vornherein auszuschließen",
            "correct": False,
            "feedback": """× Nicht optimal: Dies vermeidet zwar Konvertierungsfehler, verringert aber die Interoperabilität und maschinelle Auswertbarkeit erheblich, da z. B. numerische Sortierungen oder Boolean-Logik dann nicht mehr direkt möglich sind."""
        },
        {
            "answer": "Leere `anmerkung`-Felder werden konsequent zu `null`, um in JSON klar zwischen 'kein Wert' und 'leerer Text' zu unterscheiden",
            "correct": False,
            "feedback": """× Nicht die im Kapitel vorgestellte Praxis: Dort werden leere Felder bewusst als leere Strings statt `null` beibehalten, um die tabellarische Struktur konsistent zu halten - eine bewusste Designentscheidung, kein Zufall."""
        },
        {
            "answer": "`mehrfachregie` wird als String '1' oder '0' statt als Boolean gespeichert, da JSON keine Booleans unterstützt",
            "correct": False,
            "feedback": """× Falsch: JSON unterstützt echte Booleans (`true`/`false`) als eigenen Datentyp - genau diese Umwandlung von CSV-Text zu JSON-Boolean ist ein zentraler Schritt bei einer sauberen Konvertierung."""
        }
    ]
}]

display_quiz(single_choice4, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 5

Der folgende Ausschnitt eines Validation Reports wurde nach Prüfung eines neuen Korpus erzeugt:

```text
ZEILE 42: Pflichtfeld 'director' ist leer.
ZEILE 58: Wert 'DEU' in 'country' ist nicht erlaubt. Erlaubt sind: ['DE', 'AT', 'CH', ...]
ZEILE 71: Wert '2021 ' in 'year' passt nicht zum erwarteten Muster: "^[0-9]{4}$"
```

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Ordnen Sie jeder Fehlermeldung die zugrunde liegende Ursache zu:",
    descriptions=[
        "ZEILE 42: Pflichtfeld 'director' ist leer",
        "ZEILE 58: Wert 'DEU' in 'country' ist nicht erlaubt",
        "ZEILE 71: Wert '2021 ' in 'year' passt nicht zum erwarteten Muster"
    ],
    options=[
        "Verstoß gegen ein kontrolliertes Vokabular / ISO-Standard",
        "Verletzung einer Pflichtfeld-Regel (required)",
        "Verstoß gegen ein Formatmuster (Pattern), z. B. durch ein unsichtbares Leerzeichen"
    ],
    correct_mapping={
        "ZEILE 42: Pflichtfeld 'director' ist leer": "Verletzung einer Pflichtfeld-Regel (required)",
        "ZEILE 58: Wert 'DEU' in 'country' ist nicht erlaubt": "Verstoß gegen ein kontrolliertes Vokabular / ISO-Standard",
        "ZEILE 71: Wert '2021 ' in 'year' passt nicht zum erwarteten Muster": "Verstoß gegen ein Formatmuster (Pattern), z. B. durch ein unsichtbares Leerzeichen"
    }
)
```

## Aufgabe 6

Ein anderes Forschungsteam erstellt aus urheberrechtlich geschütztem Filmmaterial ein neues visuelles Analysetool: Für jeden Film wird ein Diagramm erzeugt, das die durchschnittliche Schnittfrequenz (Anzahl der Schnitte pro Minute) über die Laufzeit darstellt - ganz ohne Farbinformationen oder Standbilder.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice6 = [{
    "question": """Wenden Sie die im Kapitel zu Moviebarcodes vorgestellte rechtliche Argumentation auf dieses neue Analysetool an: Welche Einschätzung ist am ehesten zutreffend?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Da hier andere Werte (Schnittfrequenz statt Farbe) verwendet werden, greift die Argumentation der Moviebarcodes nicht und das Tool ist automatisch schutzfähig",
            "correct": False,
            "feedback": """× Falsch: Die Art der gemessenen Werte ist nicht entscheidend. Entscheidend ist, ob der Erzeugungsprozess deskriptiv-quantitativ und analytisch ist oder ob er schöpferische, gestalterische Entscheidungen zum Ausgangswerk trifft."""
        },
        {
            "answer": "Wie bei Moviebarcodes handelt es sich um einen deskriptiv-quantitativen, analytischen Aggregationsprozess ohne erkennbare Szenen oder Wiedererkennungswert - die Argumentation lässt sich grundsätzlich übertragen",
            "correct": True,
            "feedback": """✓ Richtig: Die zentralen Kriterien aus dem Kapitel (kein Werkcharakter, keine erkennbaren Szenen/Figuren, kein visueller Wiedererkennungswert, analytischer statt schöpferischer Prozess) lassen sich strukturell auch auf diese Schnittfrequenz-Visualisierung anwenden."""
        },
        {
            "answer": "Jede Form der Datenverarbeitung von Filmmaterial ist durch § 60d UrhG automatisch von jeglicher rechtlicher Prüfung befreit",
            "correct": False,
            "feedback": """× Falsch: § 60d UrhG erlaubt Text- und Data Mining zu wissenschaftlichen Zwecken, ersetzt aber keine grundsätzliche Einordnung, ob überhaupt ein schutzfähiges (abgeleitetes) Werk entsteht - beides sind unterschiedliche rechtliche Ebenen."""
        },
        {
            "answer": "Ohne erneute Einholung einer rechtlichen Einschätzung (z. B. durch einen Helpdesk oder eine Kanzlei) sollte die Argumentation nicht ungeprüft auf ein neues, andersartiges Analysetool übertragen werden",
            "correct": True,
            "feedback": """✓ Richtig: Das Kapitel betont ausdrücklich, dass die vorliegende Einschätzung unverbindlich ist und keine Rechtsberatung ersetzt - dies gilt umso mehr bei der Übertragung auf ein neues, nicht identisches Verfahren."""
        }
    ]
}]

display_quiz(single_choice6, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 7

**Szenario:** Sie übernehmen ein filmwissenschaftliches Korpus mit 300 Produktionen aus 40 Ländern und sollen es analog zur diskriminierungssensiblen Überprüfung aus Kapitel 5 auswerten. Sie stellen fest, dass 85 % der Produktionen aus Nordamerika und Westeuropa stammen und 90 % der Regie männlich gelesenen Personen zugeordnet werden.

Reflektieren Sie:
1. Ist diese Verteilung allein schon ein Beleg für diskriminierende Inhalte der Filme selbst?
2. Welche methodischen Schritte würden Sie unternehmen, um diese Zahlen einzuordnen (z. B. Bezugsgröße der Prozentrechnung, Umgang mit Serien)?
3. Welche Grenzen hat eine rein quantitative Metadatenauswertung in Bezug auf Diskriminierungssensibilität?

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_K5-7')
```

````{admonition} Musterlösung
:class: solution, dropdown

**1. Kein direkter Beleg für diskriminierende Inhalte:**
- Eine geografische oder geschlechtsbezogene Schieflage in den Metadaten sagt zunächst nur etwas über die Zusammensetzung des Korpus aus, nicht über die diskursive oder ästhetische Qualität der einzelnen Werke.
- Ob und wie Filme diskriminierende Perspektiven reproduzieren oder unterlaufen, lässt sich nur durch qualitative Analyse der einzelnen Werke beantworten.

**2. Methodische Schritte zur Einordnung:**
- Serien vor der Auswertung auf eine Episode reduzieren (oder Begründung finden, warum nicht), um Verzerrung durch viele Einzelepisoden zu vermeiden.
- Bezugsgröße klar wählen und dokumentieren: Prozentanteile auf Produktionen vs. auf Personen (z. B. Regie) beziehen, je nachdem was inhaltlich sinnvoller ist.
- Prüfen, ob die Korpuszusammenstellung eine bewusste forschungsstrategische Entscheidung ist oder einen blinden Fleck darstellt.
- Ergebnisse tabellarisch/visuell aufbereiten für bessere Übersicht.

**3. Grenzen der quantitativen Auswertung:**
- Quantitative Auswertungen erlauben Aussagen über Struktur/Organisation des Korpus, nicht über dessen Diskursivität.
- Kategorien wie Geschlecht sind oft binär und unvollständig erfasst.
- Externe Datenquellen (z. B. IMDb) können selbst diskriminierende Begriffe oder Verzerrungen enthalten.
- Notwendig sind ergänzende qualitative Analysen der ästhetischen, affektiven und narrativen Strategien der Werke.
````

## Aufgabe 8

Ein neues Teilprojekt möchte sein Korpus ebenfalls öffentlich publizieren. Es enthält:  
(a) die Rohvideodateien,  
(b) eine Tabelle mit Titel, Jahr, Land und Regie,  
(c) automatisch erzeugte Farbverlaufsbilder je Film,  
(d) handschriftliche Notizen der Forschenden mit Zitaten aus den Filmen.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice8 = [{
    "question": """Übertragen Sie die im Kapitel angewendete Publikationslogik (Primär- vs. Sekundärdaten, Urheberrecht) auf dieses neue Korpus. Welche Einschätzungen sind plausibel?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Die Rohvideodateien (a) sollten analog zum besprochenen Projekt eher nicht direkt mitpubliziert werden, da hierfür in der Regel keine Rechte für eine freie Weiterverbreitung vorliegen",
            "correct": True,
            "feedback": """✓ Richtig: Wie im Kapitel gezeigt, werden Primärdaten wie Film-/Videomaterial aus urheberrechtlichen Gründen typischerweise nicht mitpubliziert, da eigene Bearbeitungsrechte fehlen."""
        },
        {
            "answer": "Die Farbverlaufsbilder (c) sind, ähnlich wie Moviebarcodes, eher unproblematisch zu publizieren, da sie stark abstrahierte, analytisch erzeugte Ableitungen ohne Werkcharakter darstellen",
            "correct": True,
            "feedback": """✓ Richtig: Analog zur Argumentation bei Moviebarcodes handelt es sich um eine deskriptiv-quantitative Aggregation, die in der Regel keinen eigenen urheberrechtlichen Schutz des Originalwerks berührt."""
        },
        {
            "answer": "Die handschriftlichen Notizen mit wörtlichen Filmzitaten (d) können ohne weitere Prüfung genauso unproblematisch veröffentlicht werden wie die Tabelle mit Titel, Jahr und Land (b)",
            "correct": False,
            "feedback": """× Falsch: Wörtliche Zitate aus den Filmen sind urheberrechtlich anders zu bewerten als rein strukturelle Metadaten (Titel, Jahr, Land) und benötigen eine gesonderte Prüfung, z. B. hinsichtlich Zitatrecht oder Umfang."""
        },
        {
            "answer": "Für die Metadatentabelle (b) sollte trotz vermeintlicher Unproblematik weiterhin auf diskriminierungssensible Aspekte (z. B. Länderkodierung, Kategorisierung von Regie) geachtet werden",
            "correct": True,
            "feedback": """✓ Richtig: Auch scheinbar neutrale, strukturelle Metadaten wie Länder- oder Personenangaben sollten mit Blick auf diskriminierungssensible Kriterien geprüft werden, unabhängig von ihrer rechtlichen Unbedenklichkeit."""
        }
    ]
}]

display_quiz(multiple_choice8, colors=colors.jupyterquiz, max_width=900)
```

## Aufgabe 9

Ihr Datensatz ist inzwischen auf 20 Metadatenfelder, drei verschiedene Datentypen und mehrere verschachtelte Ordner angewachsen. Eine studentische Hilfskraft schlägt vor, einfach alle Informationen in einer einzigen, sehr langen README-Datei zu bündeln.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

single_choice9 = [{
    "question": """Welche Einschätzung zu diesem Vorschlag entspricht am ehesten den im Kapitel vermittelten Prinzipien guter Datendokumentation?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Der Vorschlag ist sinnvoll, da eine einzige zentrale Datei Nutzenden die Suche nach Informationen erleichtert, unabhängig von deren Länge",
            "correct": False,
            "feedback": """× Nicht ideal: Eine übermäßig lange README erschwert erfahrungsgemäß die Orientierung. Das Kapitel empfiehlt stattdessen, bei komplexeren Datensätzen mehrere, klar abgegrenzte Dokumentationsdateien anzulegen."""
        },
        {
            "answer": "Besser wäre eine kompakte README mit Überblick, Lizenz- und Zitationsinformationen, ergänzt durch separate, spezialisierte Dokumente (z. B. Codebook, Guides) für Detailinformationen zu einzelnen Datentypen",
            "correct": True,
            "feedback": """✓ Richtig: Dies entspricht dem im Kapitel vorgestellten Prinzip mehrschichtiger Dokumentation, bei dem die README als zentraler Einstiegspunkt dient und komplexere Inhalte in separate Dateien ausgelagert werden."""
        },
        {
            "answer": "Auf eine README kann in diesem Fall ganz verzichtet werden, da die Ordnerstruktur selbst ausreichend selbsterklärend ist",
            "correct": False,
            "feedback": """× Falsch: Auch eine gut organisierte Ordnerstruktur ersetzt keine explizite Dokumentation von Kontext, Methoden, Lizenz und Zitierhinweisen."""
        },
        {
            "answer": "Die Entscheidung für eine oder mehrere Dokumentationsdateien ist rein stilistisch und hat keinen Einfluss auf die Nachnutzbarkeit der Daten",
            "correct": False,
            "feedback": """× Falsch: Die Struktur der Dokumentation wirkt sich direkt auf Verständlichkeit und Nachnutzbarkeit aus - schlecht organisierte Dokumentation erschwert Nutzenden den Zugang zu den Daten erheblich."""
        }
    ]
}]

display_quiz(single_choice9, colors=colors.jupyterquiz, max_width=900)
```

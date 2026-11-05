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
```{code-cell} ipython3
:tags: [remove-cell]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors
```

# 🏆Selbsttest: Wissen und Praxis

Dieser Selbsttest bezieht sich auf das Kapitel **Automatisierte Annotation von Filmen**.

````{admonition} Wie nutze ich den Selbsttest?
:class: hinweis, dropdown
Diese Übungsaufgaben dienen Ihrer Selbsteinschätzung und helfen Ihnen, das im Kapitel Gelernte zu reflektieren.

Sie können die Fragen in beliebiger Reihenfolge bearbeiten und die Beantwortung auch mehrfach versuchen.

**So funktioniert es:**
- Wählen Sie bei jeder Frage die Antwort(en) aus, die Sie für richtig halten
- Lesen Sie das Feedback zu den einzelnen Antwortoptionen sorgfältig durch
- Die Erklärungen helfen Ihnen, Ihr Verständnis zu vertiefen – auch bei korrekten Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse. Nutzen Sie dieses Assessment, um Wissenslücken zu identifizieren und gegebenenfalls die entsprechenden Abschnitte des Kapitels nochmals zu bearbeiten.

**Geschätzte Zeit**: 20 Minuten

Viel Erfolg!
````

## Aufgabe 1

Ein Modell ist sehr bekannt, wurde aber mit Farbfotos trainiert. Ihr Material ist ein Schwarz-Weiß-Film. Was prüfen Sie zuerst?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice1 = [{
    "question": """Ein Modell ist sehr bekannt, wurde aber mit Farbfotos trainiert. Ihr Material ist ein Schwarz-Weiß-Film. Was prüfen Sie zuerst?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Ob es auf Ihrem Material brauchbare Ergebnisse liefert.",
            "correct": True,
            "feedback": """✓ Richtig: Bekanntheit und Zitierhäufigkeit sind kein Beleg für die Eignung im eigenen Kontext. Entscheidend ist die Prüfung am konkreten Material."""
        },
        {
            "answer": "Ob es häufig zitiert wird.",
            "correct": False,
            "feedback": """× Nicht korrekt: Zitierhäufigkeit kann ein Hinweis sein, ersetzt aber keine Prüfung der Ergebnisse."""
        },
        {
            "answer": "Ob es eine GPU benötigt.",
            "correct": False,
            "feedback": """× Nicht korrekt: GPU-Bedarf ist eine technische Frage, keine Aussage über die inhaltliche Eignung."""
        },
        {
            "answer": "Ob der Modellname kurz ist.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Modellname ist kein Qualitätskriterium."""
        }
    ]
}]

display_quiz(multiple_choice1, colors=colors.jupyterquiz)
```

## Aufgabe 2

Bringen Sie die Schritte des Workflows in die richtige Reihenfolge.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Bringen Sie die Schritte des Workflows in die richtige Reihenfolge.",
    descriptions=[
        "1",
        "2",
        "3",
        "4",
        "5",
        "6"
    ],
    options=[
        "Parameter und Schwellenwerte festlegen",
        "Technische Vorbereitung und Import der Bibliotheken",
        "Modell anwenden",
        "Ergebnisse tabellarisch aufbereiten",
        "CSV- und EAF-Dateien exportieren",
        "Ergebnisse in VIAN sichten"
    ],
    correct_mapping={
        "1": "Parameter und Schwellenwerte festlegen",
        "2": "Technische Vorbereitung und Import der Bibliotheken",
        "3": "Modell anwenden",
        "4": "Ergebnisse tabellarisch aufbereiten",
        "5": "CSV- und EAF-Dateien exportieren",
        "6": "Ergebnisse in VIAN sichten"
    }
)
```

````{admonition} Erläuterung
:class: solution, dropdown

- **Parameter/Schwellenwerte:** Zuerst werden die Rahmenbedingungen festgelegt; sie bestimmen die gesamte Analyse.
- **Technische Vorbereitung:** Danach werden Bibliotheken installiert und importiert, Material und Modell vorbereitet.
- **Modell anwenden:** Das Modell wird auf das Videomaterial angewendet.
- **Tabellarische Aufbereitung:** Die Rohausgabe wird in ein weiterverarbeitbares Tabellenformat gebracht.
- **Export:** CSV für Tabellen und EAF für die Sichtung in VIAN.
- **Sichtung:** Die Qualität wird nach dem Export geprüft; bei Bedarf werden Schwellenwerte angepasst und der Prozess wiederholt.
- **Typischer Fehler:** Die Sichtung vor den Export zu setzen. Ohne EAF-Datei kann VIAN die Annotationen nicht importieren.
````

## Aufgabe 3

Sie möchten die automatisch erstellten Annotationen in VIAN sichten. Welche Datei importieren Sie?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice3 = [{
    "question": """Sie möchten die automatisch erstellten Annotationen in VIAN sichten. Welche Datei importieren Sie?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Die CSV-Datei mit den Einstellungen",
            "correct": False,
            "feedback": """× Nicht korrekt: CSV eignet sich für Tabellen und weitere Berechnungen, aber nicht für den Annotationsimport in VIAN."""
        },
        {
            "answer": "Die EAF-Datei",
            "correct": True,
            "feedback": """✓ Richtig: EAF steht für ELAN Annotation Format und wird von VIAN importiert; die Annotationen erscheinen dort als Spuren."""
        },
        {
            "answer": "Das ZIP-Archiv",
            "correct": False,
            "feedback": """× Nicht korrekt: Das ZIP-Archiv bündelt Dateien, ist aber kein Annotationsformat."""
        },
        {
            "answer": "Die MP4-Videodatei",
            "correct": False,
            "feedback": """× Nicht korrekt: Die Videodatei wird in VIAN geöffnet, enthält aber nicht die Annotationen."""
        }
    ]
}]

display_quiz(multiple_choice3, colors=colors.jupyterquiz)
```

## Aufgabe 4

Sie erhöhen bei der Einstellungserkennung den `THRESHOLD` von 0,5 auf 0,8. Was erwarten Sie?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice4 = [{
    "question": """Sie erhöhen bei der Einstellungserkennung den <code>THRESHOLD</code> von 0,5 auf 0,8. Was erwarten Sie?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Mehr Treffer, aber auch mehr falsch-positive Ergebnisse.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das beschreibt einen niedrigeren Schwellenwert."""
        },
        {
            "answer": "Weniger Treffer, weniger falsch-positive Ergebnisse, aber mögliche übersehene Übergänge.",
            "correct": True,
            "feedback": """✓ Richtig: Ein höherer Schwellenwert ist konservativer: weniger Treffer, aber tendenziell sicherere Treffer. Gleichzeitig können echte Übergänge übersehen werden."""
        },
        {
            "answer": "Keine Veränderung, weil der Schwellenwert nur die Laufzeit beeinflusst.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Schwellenwert verändert die Anzahl und Auswahl der Annotationen."""
        },
        {
            "answer": "Eine schnellere Analyse, weil weniger Frames geprüft werden.",
            "correct": False,
            "feedback": """× Nicht korrekt: Die für die Analyse benötigte Zeit hängt primär von der Anzahl der analysierten Frames und dem Modell ab, nicht vom Schwellenwert."""
        }
    ]
}]

display_quiz(multiple_choice4, colors=colors.jupyterquiz)
```

## Aufgabe 5

Ein Modell liefert für mögliche Einstellungsübergänge die Werte 0,18; 0,42; 0,51; 0,79. Wie viele Übergänge werden bei `THRESHOLD = 0.5` erfasst?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

numeric5 = [{
    "question": """Ein Modell liefert für mögliche Einstellungsübergänge die Werte 0,18; 0,42; 0,51; 0,79. Wie viele Übergänge werden bei <code>THRESHOLD = 0.5</code> erfasst?""",
    "type": "numeric",
    "answers": [
        {
            "value": 2,
            "correct": True,
            "feedback": """✓ Richtig: 0,51 und 0,79 liegen über 0,5; 0,42 und 0,18 darunter."""
        },
        {
            "value": 3,
            "correct": False,
            "feedback": """× Nicht korrekt: 0,42 wird mitgezählt, weil es „fast“ 0,5 erreicht. Der Schwellenwert ist eine harte Grenze."""
        },
        {
            "value": 4,
            "correct": False,
            "feedback": """× Nicht korrekt: Alle vier werden gezählt. Das ignoriert die Funktion des Schwellenwerts."""
        },
        {
            "type": "default",
            "feedback": """× Nicht korrekt: Ein niedrigerer Wert würde hier mehr Übergänge erfassen, aber auch die Wahrscheinlichkeit falsch-positiver Treffer erhöhen."""
        }
    ]
}]

display_quiz(numeric5, colors=colors.jupyterquiz)
```

## Aufgabe 6

Rita ist im Trailer „Der geteilte Himmel“ von hinten zu sehen und wird nicht erkannt. Wie ordnen Sie das ein?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice6 = [{
    "question": """Rita ist im Trailer „Der geteilte Himmel“ von hinten zu sehen und wird nicht erkannt. Wie ordnen Sie das ein?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Das Modell ist defekt.",
            "correct": False,
            "feedback": """× Nicht korrekt: Ein einzelner Nichterkennungsfall belegt keinen Defekt. Das Verfahren benötigt sichtbare Gesichtsmerkmale."""
        },
        {
            "answer": "Ohne sichtbares Gesicht kann die Gesichtserkennung nicht arbeiten; das ist eine Beschränkung des Verfahrens.",
            "correct": True,
            "feedback": """✓ Richtig: Wenn das Gesicht nicht im Bild ist, können Detection und Recognition keine verlässlichen Merkmale extrahieren. Das ist eine materialbedingte Beschränkung, die dokumentiert werden sollte."""
        },
        {
            "answer": "Der Schwellenwert ist zu hoch.",
            "correct": False,
            "feedback": """× Nicht korrekt: Ein niedrigerer Schwellenwert kann oft helfen, ist aber nicht automatisch die Lösung und erzeugt ggf. falsch-positive Treffer."""
        },
        {
            "answer": "Rita ist keine Hauptfigur und wird deshalb übersprungen.",
            "correct": False,
            "feedback": """× Nicht korrekt: Die Figurenerkennung unterscheidet nicht nach Haupt- und Nebenfiguren; sie arbeitet mit Referenzbildern und Ähnlichkeitswerten."""
        }
    ]
}]

display_quiz(multiple_choice6, colors=colors.jupyterquiz)
```

## Aufgabe 7

Bringen Sie die vier Schritte der Gesichtserkennung in die richtige Reihenfolge.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Bringen Sie die vier Schritte der Gesichtserkennung in die richtige Reihenfolge.",
    descriptions=[
        "1",
        "2",
        "3",
        "4"
    ],
    options=[
        "Detection",
        "Alignment",
        "Representation",
        "Recognition"
    ],
    correct_mapping={
        "1": "Detection",
        "2": "Alignment",
        "3": "Representation",
        "4": "Recognition"
    }
)
```

````{admonition} Erläuterung
:class: solution, dropdown

- **Detection:** Zuerst wird ein Gesicht im Bild gefunden und mit einem Rahmen markiert; zusätzlich entsteht ein Konfidenzwert.
- **Alignment:** Das erkannte Gesicht wird begradigt und zugeschnitten, um die Vergleichbarkeit zu erhöhen.
- **Representation:** Aus dem Gesicht wird ein Embedding, also eine Vektorrepräsentation, erstellt.
- **Recognition:** Die Embeddings werden verglichen; ein Schwellenwert entscheidet, ob zwei Gesichter derselben Person zugeordnet werden.
- **Typischer Fehler:** Representation vor Alignment zu setzen. Ohne Normalisierung ist der Vergleich weniger stabil.
````

## Aufgabe 8

Welche Anforderung an Referenzbilder ist korrekt?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice8 = [{
    "question": """Welche Anforderung an Referenzbilder ist korrekt?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Mehrere Bilder einer Figur aus verschiedenen Perspektiven können die Erkennung verbessern.",
            "correct": True,
            "feedback": """✓ Richtig: Mehrere Aufnahmen erhöhen die Wahrscheinlichkeit einer korrekten Zuordnung; aus ihnen wird ein durchschnittliches Embedding gebildet."""
        },
        {
            "answer": "Ein Bild mit möglichst vielen Gesichtern ist ideal.",
            "correct": False,
            "feedback": """× Nicht korrekt: Jedes Referenzbild sollte genau ein Gesicht enthalten, sonst ist unklar, welches Gesicht zur Figur gehört."""
        },
        {
            "answer": "Der Dateiname ist beliebig.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Figurenname wird aus dem Dateinamen ermittelt; die Konvention muss eingehalten werden."""
        },
        {
            "answer": "Referenzbilder werden automatisch aus dem Film extrahiert.",
            "correct": False,
            "feedback": """× Nicht korrekt: Die Referenzbilder werden händisch ausgewählt und vorbereitet."""
        }
    ]
}]

display_quiz(multiple_choice8, colors=colors.jupyterquiz)
```

## Aufgabe 9

Sie senken den Schwellenwert. Es gibt mehr Treffer, darunter aber auch falsche Figurenzuordnungen. Wie beurteilen Sie das?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice9 = [{
    "question": """Sie senken den Schwellenwert. Es gibt mehr Treffer, darunter aber auch falsche Figurenzuordnungen. Wie beurteilen Sie das?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Mehr Treffer sind immer besser.",
            "correct": False,
            "feedback": """× Nicht korrekt: Mehr Treffer bedeuten nicht automatisch mehr Erkenntnis; falsch-positive Treffer können Muster verfälschen."""
        },
        {
            "answer": "Falsch-positive Treffer können die Analyse verzerren; der Nutzen ist vom Forschungsziel abhängig.",
            "correct": True,
            "feedback": """✓ Richtig: Es handelt sich um eine zu treffende Entscheidung. Für eine explorative Suche können mehr Treffer sinnvoll sein; für eine quantitative Auswertung sind präzise Zuordnungen wichtiger. Die Ergebnisse müssen geprüft werden."""
        },
        {
            "answer": "Schwellenwerte ändern die Ergebnisse nicht.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Schwellenwert bestimmt, welche Werte als Treffer gelten."""
        },
        {
            "answer": "Das Modell wird durch den niedrigeren Schwellenwert trainiert.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Schwellenwert ist ein Analyseparameter, kein Trainingssignal."""
        }
    ]
}]

display_quiz(multiple_choice9, colors=colors.jupyterquiz)
```

## Aufgabe 10

Sie möchten eigene Trailer für die Einstellungserkennung nutzen. Was müssen Sie im Jupyter Notebook mindestens anpassen?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice10 = [{
    "question": """Sie möchten eigene Trailer für die Einstellungserkennung nutzen. Was müssen Sie im Jupyter Notebook mindestens anpassen?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "<code>DOWNLOAD_TESTFILES = False</code> setzen und die Dateien in <code>VIDEO_PATH</code> ablegen.",
            "correct": True,
            "feedback": """✓ Richtig: Damit das Notebook keine Testdateien herunterlädt und Ihre eigenen Videos verarbeitet, müssen Sie den Download deaktivieren und die Dateien im vorgesehenen Videoordner ablegen."""
        },
        {
            "answer": "Nur <code>THRESHOLD</code> ändern.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Schwellenwert allein ändert nichts an der Datenquelle."""
        },
        {
            "answer": "Nur <code>EXPORT_PATH</code> ändern.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Exportpfad bestimmt nur, wohin Ergebnisse gespeichert werden."""
        },
        {
            "answer": "Nichts; das Notebook erkennt eigene Dateien automatisch.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das Notebook lädt standardmäßig Testdateien herunter; eigene Dateien müssen aktiv eingebunden werden."""
        }
    ]
}]

display_quiz(multiple_choice10, colors=colors.jupyterquiz)
```

## Aufgabe 11 – Selbstreflexion: Schwellenwerte wählen und Qualität beurteilen

Sie möchten für eine Videodatei eine Einstellungs- und Figurenerkennung mit den Jupyter Notebooks durchführen.

1. Was müssen Sie bei der Festlegung der Schwellenwerte für die Einstellungserkennung beachten?
2. Wie gehen Sie mit den Ergebnissen der Einstellungserkennung um?
3. Reflektieren Sie kurz, warum Age-/Gender-Schätzungen der Figurenerkennung nicht ungeprüft verwendet werden sollten.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_Annotation')
```

````{admonition} Musterlösung
:class: solution, dropdown

> **Vorgehen:** Für eine erste explorative Sichtung kann ein niedrigerer Schwellenwert sinnvoll sein, um mögliche Übergänge nicht zu übersehen. Für eine quantitative Auswertung, bei der falsch-positive Treffer die Kennwerte verzerren, ist ein höherer Schwellenwert sinnvoll. Der Wert muss zum Material, zur Fragestellung und zur geplanten Auswertung passen. Die Annotationsergebnisse sollten immer am Material auf ihre Korrektheit überprüft werden. Hierfür können die Ergebnisse z. B. mithilfe einer `EAF-Datei` in das Annotationstool VIAN importiert werden.
>
> **Age-/Gender-Reflexion:** Diese Schätzwerte beruhen auf äußeren Merkmalen und den Kategorien der Trainingsdaten. Sie sind oft fehlerhaft, reproduzieren Stereotype und bilden Geschlechtsidentität nicht angemessen ab. Sie werden in der OER daher nicht gespeichert und nicht für die Analyse verwendet.
````

### Bewertungsraster

| Kriterium | 0 Punkte | 1 Punkt | 2 Punkte |
|---|---|---|---|
| Durchführung | nicht durchgeführt | teilweise | zwei Werte systematisch verglichen |
| Dokumentation | fehlt | knapp | Tabelle mit nachvollziehbaren Beobachtungen |
| Begründung | fehlt | allgemein | forschungszielbezogen und materialbezogen |
| Qualitätsurteil | fehlt | ansatzweise | Fehlertypen und Grenzen benannt |
| Ethik-Reflexion | fehlt | ansatzweise | Age-/Gender-Problematik konkret erklärt |

````{admonition} Hinweise zur Selbstkorrektur
:class: hinweis, dropdown

- Wenn Sie nur „mehr Treffer = besser“ schreiben, fehlt die Unterscheidung zwischen Sensitivität und Präzision.
- Wenn Sie keine Fehler in VIAN finden, prüfen Sie gezielt Übergänge mit starken Bewegungen, ähnlichen Bildern und Lichtwechseln.
- Wenn die Downloadlinks in den Kapiteln noch fehlen, nutzen Sie die beschriebenen Beispiele aus `annotation/einstellung_datensichtung.md` und `annotation/figuren_datensichtung.md` als Fallvignetten.
````

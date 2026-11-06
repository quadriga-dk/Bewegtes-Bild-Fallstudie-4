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

````{admonition} Wie nutze ich den Selbsttest?
:class: hinweis, dropdown
Diese Übungsaufgaben dienen Ihrer Selbsteinschätzung und helfen Ihnen, das in den Kapiteln Gelernte zu reflektieren.

Sie können die Fragen in beliebiger Reihenfolge bearbeiten und die Beantwortung auch mehrfach versuchen.

**So funktioniert es:**
- Wählen Sie bei jeder Frage die Antwort(en) aus, die Sie für richtig halten
- Lesen Sie das Feedback zu den einzelnen Antwortoptionen sorgfältig durch
- Die Erklärungen helfen Ihnen, Ihr Verständnis zu vertiefen – auch bei korrekten Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse. Nutzen Sie dieses Assessment, um Wissenslücken zu identifizieren und gegebenenfalls die entsprechenden Abschnitte der Kapitel nochmals zu bearbeiten.

**Geschätzte Zeit**: 20 Minuten

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
    "question": """Welche Zuordnung von Modell und Aufgabe ist korrekt?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "TransNetV2 → Einstellungsübergänge; InsightFace → Gesichter/Figuren.",
            "correct": True,
            "feedback": """✓ Richtig: TransNetV2 ist das Modell zur Erkennung von Einstellungsübergängen; InsightFace wird für Gesichtsdetektion und -erkennung eingesetzt."""
        },
        {
            "answer": "TransNetV2 → Gesichter; InsightFace → Einstellungsübergänge.",
            "correct": False,
            "feedback": """× Nicht korrekt: Hier sind die Aufgaben vertauscht."""
        },
        {
            "answer": "Beide Modelle erkennen ausschließlich Farben.",
            "correct": False,
            "feedback": """× Nicht korrekt: Farbanalyse ist nicht die primäre Aufgabe dieser Modelle."""
        },
        {
            "answer": "Beide Modelle sind nur für die Tonanalyse geeignet.",
            "correct": False,
            "feedback": """× Nicht korrekt: Beide Modelle arbeiten primär mit visuellen Daten."""
        }
    ]
}]

display_quiz(multiple_choice1, colors=colors.jupyterquiz)
```

## Aufgabe 2

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice2 = [{
    "question": """Was beweist eine niedrige ASL allein nicht?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Dass ein Film viele Einstellungen hat.",
            "correct": False,
            "feedback": """× Nicht korrekt: Eine niedrige ASL bedeutet rechnerisch viele Einstellungen pro Laufzeit."""
        },
        {
            "answer": "Dass der Film schnell geschnitten ist.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das ist die naheliegende formale Beschreibung."""
        },
        {
            "answer": "Dass der Schnitt vom Publikum als schnell wahrgenommen wird.",
            "correct": True,
            "feedback": """✓ Richtig: Die Wahrnehmung von Schnittfrequenz ist historisch und genreabhängig; für die Interpretation braucht es Rezeptionskontext und qualitative Analyse."""
        },
        {
            "answer": "Dass die ASL aus Filmlänge und Einstellungsanzahl berechnet wird.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das ist die Definition der ASL, kein Beweis über die Wahrnehmung."""
        }
    ]
}]

display_quiz(multiple_choice2, colors=colors.jupyterquiz)
```

## Aufgabe 3

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice3 = [{
    "question": """Was bewirkt ein höherer Schwellenwert in der Regel?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Mehr Treffer, mehr falsch-positive Ergebnisse.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das beschreibt einen niedrigeren Schwellenwert."""
        },
        {
            "answer": "Weniger Treffer, weniger falsch-positive Ergebnisse, mögliche übersehene Merkmale.",
            "correct": True,
            "feedback": """✓ Richtig: Ein höherer Schwellenwert ist konservativer; er reduziert falsch-positive Treffer, kann aber echte Merkmale übersehen."""
        },
        {
            "answer": "Keine Veränderung der Treffer.",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Schwellenwert bestimmt, welche Werte als Treffer gelten."""
        },
        {
            "answer": "Eine Verbesserung der Bildqualität.",
            "correct": False,
            "feedback": """× Nicht korrekt: Die Bildqualität wird dadurch nicht verändert."""
        }
    ]
}]

display_quiz(multiple_choice3, colors=colors.jupyterquiz)
```

## Aufgabe 4

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice4 = [{
    "question": """Was bedeutet eine dicke Verbindung zwischen zwei Figuren im Netzwerk?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Sie haben eine besonders gute Beziehung.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das Netzwerk zeigt gemeinsame Erkennung, nicht die Qualität einer Beziehung."""
        },
        {
            "answer": "Sie wurden häufig gemeinsam in untersuchten Frames erkannt.",
            "correct": True,
            "feedback": """✓ Richtig: Die Dicke der Verbindung bildet die Häufigkeit bzw. Dauer gemeinsamer Erkennung ab."""
        },
        {
            "answer": "Sie sprechen häufig miteinander.",
            "correct": False,
            "feedback": """× Nicht korrekt: Dialoge werden nicht erfasst."""
        },
        {
            "answer": "Sie sind die Hauptfiguren.",
            "correct": False,
            "feedback": """× Nicht korrekt: Hauptfiguren lassen sich nicht allein aus der Verbindungsdicke ableiten."""
        }
    ]
}]

display_quiz(multiple_choice4, colors=colors.jupyterquiz)
```

## Aufgabe 5

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice5 = [{
    "question": """Warum sind Computer-Vision-Modelle nie vollständig „neutral“?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Weil sie immer zu langsam sind.",
            "correct": False,
            "feedback": """× Nicht korrekt: Geschwindigkeit ist kein Neutralitätsproblem."""
        },
        {
            "answer": "Weil ihre Trainingsdaten von Menschen erstellt und annotiert wurden und Werte, Auswahlentscheidungen und Bias enthalten.",
            "correct": True,
            "feedback": """✓ Richtig: Trainingsdaten und Annotationsentscheidungen sind menschlich geprägt; Modelle reproduzieren diese Muster und sind daher nicht objektiv."""
        },
        {
            "answer": "Weil sie nur in Schwarz-Weiß funktionieren.",
            "correct": False,
            "feedback": """× Nicht korrekt: Modelle können mit Farb- oder Schwarz-Weiß-Material arbeiten, aber die Eignung ist materialabhängig."""
        },
        {
            "answer": "Weil sie keine Wahrscheinlichkeiten ausgeben.",
            "correct": False,
            "feedback": """× Nicht korrekt: Viele Modelle geben gerade Wahrscheinlichkeitswerte aus."""
        }
    ]
}]

display_quiz(multiple_choice5, colors=colors.jupyterquiz)
```

## Aufgabe 6

Wählen Sie ein Filmkorpus von 3–5 Filmen. Skizzieren Sie ein Untersuchungsdesign mit folgenden Bausteinen:

1. Forschungsfrage und Annahmen,
2. Wahl der Annotationsparameter (Einstellungen und/oder Figuren),
3. Modellwahl und Begründung,
4. Schwellenwertstrategie,
5. Qualitätskontrolle und Dokumentation,
6. Auswertungs- und Visualisierungsplan,
7. Reflexion von Grenzen, Bias und Entstehungskontext.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_Reflexion')
```

````{admonition} Musterlösung
:class: solution, dropdown

**Fragestellung:**

Unterscheiden sich die Filme des Korpus in ihrer durchschnittlichen Einstellungslänge, und lassen sich die Unterschiede mit Genre oder Schaffensphase erklären?

**Parameter:**

Einstellungsübergänge und Einstellungslängen; optional Figurenpräsenz für eine ergänzende Frage.

**Modell:**

TransNetV2 für die Einstellungserkennung, weil es etabliert und für das Material geeignet erscheint; Prüfung an einem Testfilm.

**Schwellenwerte:**

Erster Durchlauf mit 0,5; anschließend Vergleich mit 0,25 und 0,75; Sichtung in VIAN; Dokumentation der gewählten Werte.

**Qualitätskontrolle:**

Stichprobenprüfung, Zählung auffälliger Fehler, transparente Dokumentation von Modell, Parametern und Grenzen.

**Auswertung:**

ASL, MSL, Anzahl der Einstellungen, längste/kürzeste Einstellung; Balkendiagramme im Vergleich, chronologische Sortierung; Rückgriff auf einzelne Filme.


**Reflexion:**

ASL allein beweist keinen Stil; Genre, Produktionskontext und Rezeptionserwartungen einbeziehen; Bias der Modelle und Fehler der Annotationen offenlegen.
````

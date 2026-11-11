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
Diese Übungsaufgaben dienen Ihrer Selbsteinschätzung und helfen Ihnen, das im Kapitel Gelernte zu reflektieren.

Sie können die Fragen in beliebiger Reihenfolge bearbeiten und die Beantwortung auch mehrfach versuchen.

**So funktioniert es:**
- Wählen Sie bei jeder Frage die Antwort(en) aus, die Sie für richtig halten
- Lesen Sie das Feedback zu den einzelnen Antwortoptionen sorgfältig durch
- Die Erklärungen helfen Ihnen, Ihr Verständnis zu vertiefen – auch bei korrekten Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse. Nutzen Sie dieses Assessment, um Wissenslücken zu identifizieren und gegebenenfalls die entsprechenden Abschnitte des Kapitels nochmals zu bearbeiten.

**Geschätzte Zeit**: 10 Minuten

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
    "question": """Was beschreibt Computer Vision am treffendsten?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Das Erzeugen von Bildern aus numerischen Daten.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das beschreibt eher die Computergrafik. Computer Vision geht den umgekehrten Weg: Sie beschreibt die Welt auf der Grundlage von Bildern."""
        },
        {
            "answer": "Das Erfassen, Verarbeiten und Analysieren von Bildern durch Computer.",
            "correct": True,
            "feedback": """✓ Richtig: Computer Vision umfasst Methoden zur Erfassung, Verarbeitung, Analyse und Interpretation von Bildern durch Computer."""
        },
        {
            "answer": "Das manuelle Annotieren von Filmen.",
            "correct": False,
            "feedback": """× Nicht korrekt: Manuelle Annotation ist ein anderer Zugang; Computer Vision automatisiert oder unterstützt Analyseprozesse."""
        },
        {
            "answer": "Das Training von Schauspieler:innen für Kameraeinstellungen.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das hat mit Computer Vision nichts zu tun."""
        }
    ]
}]

display_quiz(multiple_choice1, colors=colors.jupyterquiz)
```

## Aufgabe 2

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Bringen Sie die folgenden Schritte bei der Computer Vision in die im Kapitel beschriebene Reihenfolge.",
    descriptions=[
        "1",
        "2",
        "3",
        "4",
        "5"
    ],
    options=[
        "Vorverarbeitung",
        "Dateneingabe",
        "Verarbeitung",
        "Anwendung des Modells",
        "Ausgabe"
    ],
    correct_mapping={
        "1": "Vorverarbeitung",
        "2": "Dateneingabe",
        "3": "Verarbeitung",
        "4": "Anwendung des Modells",
        "5": "Ausgabe"
    }
)
```

````{admonition} Erläuterung
:class: solution, dropdown

- **Vorverarbeitung:** Das Kapitel nennt sie als möglichen ersten Schritt, etwa zur Verbesserung der Bildqualität oder zur Auswahl von Referenzbildern.
- **Dateneingabe:** Danach werden aus der Videodatei einzelne Frames extrahiert und importiert; Modelle arbeiten in der Regel auf der Basis von Einzelbildern.
- **Verarbeitung:** Hier werden technische Metadaten, Embeddings oder andere Zwischenprodukte erzeugt.
- **Anwendung des Modells:** Das Modell wird auf das vorbereitete Material angewendet und erzeugt z. B. Wahrscheinlichkeitswerte.
- **Ausgabe:** Schwellenwerte verwandeln die Werte in Annotationen; anschließend werden die Daten strukturiert ausgegeben und sollten ggf. geprüft werden.

*Hinweis:* Das Kapitel betont, dass der Ablauf schematisch ist und sich Schritte in der Praxis überschneiden können. Im Assessment wird die im Kapitel dargestellte Grundreihenfolge geprüft.
````

## Aufgabe 3

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice3 = [{
    "question": """Worin unterscheiden sich Algorithmus und Modell?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Ein Algorithmus ist eine Rechenvorschrift; ein Modell entsteht durch Training mit Daten.",
            "correct": True,
            "feedback": """✓ Richtig: Ein Algorithmus beschreibt eine Folge von Schritten. Ein Modell wird mit Trainingsdaten und Algorithmen bzw. Machine Learning erzeugt und wendet eine gelernte Lösung auf neue Daten an."""
        },
        {
            "answer": "Algorithmus und Modell sind dasselbe.",
            "correct": False,
            "feedback": """× Nicht korrekt: Algorithmen sind Bestandteile von Modellen, aber nicht mit ihnen identisch."""
        },
        {
            "answer": "Ein Modell ist eine Rechenvorschrift; ein Algorithmus entsteht durch Training.",
            "correct": False,
            "feedback": """× Nicht korrekt: Hier sind die Begriffe vertauscht."""
        },
        {
            "answer": "Ein Algorithmus benötigt immer eine GPU.",
            "correct": False,
            "feedback": """× Nicht korrekt: Algorithmen können auch ohne GPU und sogar ohne Computer ausgeführt werden; die GPU beschleunigt bestimmte Berechnungen."""
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

numeric4 = [{
    "question": """Ein Gesichtsdetektor liefert für vier Bildausschnitte die Werte 0,42; 0,55; 0,73; 0,81. Wie viele Gesichter gelten bei einem Schwellenwert von 0,60 als erkannt?""",
    "type": "numeric",
    "answers": [
        {
            "value": 2,
            "correct": True,
            "feedback": """✓ Richtig: 0,73 und 0,81 liegen über 0,60; 0,55 und 0,42 darunter."""
        },
        {
            "value": 3,
            "correct": False,
            "feedback": """× Nicht korrekt: 0,55 wird mitgezählt, weil es „nah“ an 0,60 liegt. Der Schwellenwert ist eine harte Grenze, keine unscharfe Toleranz."""
        },
        {
            "value": 4,
            "correct": False,
            "feedback": """× Nicht korrekt: Alle vier werden gezählt, weil alle Werte positiv erscheinen. Das ignoriert die Funktion des Schwellenwerts."""
        },
        {
            "type": "default",
            "feedback": """× Nicht korrekt: Ein höherer Schwellenwert erzeugt weniger, aber sicherere Treffer; ein niedrigerer mehr Treffer, aber auch mehr falsch-positive Ergebnisse. Die Wahl des Schwellenwertes muss dokumentiert werden."""
        }
    ]
}]

display_quiz(numeric4, colors=colors.jupyterquiz)
```

## Aufgabe 5

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice5 = [{
    "question": """Welche Frage ist typisch für Distant Viewing?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Wie ist eine einzelne Einstellung framegenau aufgebaut?",
            "correct": False,
            "feedback": """× Nicht korrekt: Die framegenaue Analyse eines einzelnen Films ist eher Close Reading."""
        },
        {
            "answer": "Welche Muster zeigen sich über 393 Episoden von Fernsehserien hinweg?",
            "correct": True,
            "feedback": """✓ Richtig: Distant Viewing untersucht große Sammlungen auf gemeinsame Merkmale und wiederkehrende Muster; das Kapitel nennt das Beispiel von 393 Episoden und 13 Millionen Frames zweier Fernsehserien."""
        },
        {
            "answer": "Wie annotiere ich eine einzelne Szene manuell?",
            "correct": False,
            "feedback": """× Nicht korrekt: Manuelle Annotation einer Szene ist kein Distant Viewing."""
        },
        {
            "answer": "Wie trainiere ich ein Modell auf einem einzelnen Film?",
            "correct": False,
            "feedback": """× Nicht korrekt: Modelltraining ist nicht der Kern des Distant Viewing; es geht um die Analyse großer Korpora."""
        }
    ]
}]

display_quiz(multiple_choice5, colors=colors.jupyterquiz)
```

## Aufgabe 6

In einem historischen Film erkennt ein Objekterkennungsmodell ein Handy, wo im Film eine Schusswaffe zu sehen ist. Bei einer weiblichen Figur schätzt dasselbe Modell „männlich“.

1. Nennen Sie zwei plausible Ursachen.
2. Nennen Sie zwei Konsequenzen für die filmanalytische Arbeit.
3. Schlagen Sie eine Maßnahme vor, wie Sie mit solchen Fehlern umgehen.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_Vision')
```

````{admonition} Musterlösung
:class: solution, dropdown

**Ursachen:**

(1) Das Modell wurde überwiegend mit aktuellem Farbmaterial trainiert und hat gelernt, Formen und Kontexte aus diesem Material zu erkennen; historische Schwarz-Weiß-Aufnahmen oder ungewöhnliche Bildkompositionen führen zu Fehlklassifikationen.

(2) Die Geschlechtsklassifikation basiert auf äußeren Merkmalen und den Kategorien der Trainingsdaten; sie reproduziert Stereotype und ist auf eine binäre Unterscheidung beschränkt.

**Konsequenzen:**

(1) Falsche Annotationen können die quantitative Auswertung verzerren, z. B. wenn Objekte oder Figuren falsch gezählt werden.

(2) Die Ergebnisse müssen gesichtet und mit dem Filmmaterial abgeglichen werden; die Herkunft des Modells, die Trainingsdaten und die angewendeten Schwellenwerte müssen dokumentiert werden.

**Maßnahme:**

Ergebnisse stichprobenartig mit Annotationstools wie VIAN am Videomaterial prüfen, alternative Modelle oder Schwellenwerte testen und die Unsicherheit im Forschungsbericht offenlegen. Age-/Gender-Schätzungen sollten kritisch hinterfragt und nicht ungeprüft übernommen oder gespeichert werden.
````
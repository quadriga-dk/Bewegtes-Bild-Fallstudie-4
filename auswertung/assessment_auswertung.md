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

**Geschätzte Zeit**: 20 Minuten

Viel Erfolg!
````

## Aufgabe 1

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Ordnen Sie die Dateien ihrem Inhalt zu.",
    descriptions=[
        "Filmname_shots_THRESHOLD.csv",
        "Filmname_shots_THRESHOLD_metadata.csv",
        "Filmname_characters_frames.csv",
        "Filmname_characters_annotations.csv"
    ],
    options=[
        "einzelne Einstellungen mit Start, Ende, Mitte und Dauer",
        "technische Metadaten, Parameter und Kennwerte",
        "einzelne Erkennungstreffer pro Frame",
        "zusammengefasste Zeitintervalle"
    ],
    correct_mapping={
        "Filmname_shots_THRESHOLD.csv": "einzelne Einstellungen mit Start, Ende, Mitte und Dauer",
        "Filmname_shots_THRESHOLD_metadata.csv": "technische Metadaten, Parameter und Kennwerte",
        "Filmname_characters_frames.csv": "einzelne Erkennungstreffer pro Frame",
        "Filmname_characters_annotations.csv": "zusammengefasste Zeitintervalle"
    }
)
```

````{admonition} Erläuterung
:class: solution, dropdown

- **Shots-CSV:** Enthält die zeitliche Segmentierung des Videos in Einstellungen.
- **Metadata-CSV:** Enthält Schlüssel-Wert-Paare zu Video, Modell, Schwellenwert und statistischen Kennwerten.
- **Frames-CSV:** Enthält die einzelnen Frames, in denen eine Figur erkannt wurde, inklusive Ähnlichkeits- und Konfidenzwert.
- **Annotations-CSV:** Fasst aufeinanderfolgende Erkennungen zu längeren Zeitintervallen zusammen.
````

## Aufgabe 2

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

numeric2 = [{
    "question": """Gegeben sind die Einstellungslängen in Sekunden: 2; 3; 3; 4; 18. Wie hoch ist der Median (MSL)?""",
    "type": "numeric",
    "answers": [
        {
            "value": 3,
            "correct": True,
            "feedback": """✓ Richtig: Sortiert lauten die Werte 2, 3, 3, 4, 18. Der mittlere Wert ist 3."""
        },
        {
            "value": 6,
            "correct": False,
            "feedback": """× Nicht korrekt: 6 ist der Mittelwert (30 / 5 = 6), der durch die lange Einstellung von 18 s nach oben gezogen wird."""
        },
        {
            "value": 18,
            "correct": False,
            "feedback": """× Nicht korrekt: 18 ist der größte Wert, nicht der Median."""
        },
        {
            "type": "default",
            "feedback": """× Nicht korrekt: Der Median ist robuster gegen Ausreißer; die ASL ist anfälliger für sehr lange Einstellungen. Deshalb werden oft beide Werte angegeben."""
        }
    ]
}]

display_quiz(numeric2, colors=colors.jupyterquiz)
```

## Aufgabe 3

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice3 = [{
    "question": """Sie möchten zeigen, wann eine Figur im Verlauf eines Films erkannt wird. Welche Visualisierung passt am besten?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Balkendiagramm der ASL über mehrere Filme",
            "correct": False,
            "feedback": """× Nicht korrekt: Das Balkendiagramm vergleicht Kennwerte zwischen Filmen, zeigt aber nicht die zeitliche Verteilung innerhalb eines Films."""
        },
        {
            "answer": "Zeitleiste mit einer Spur pro Figur",
            "correct": True,
            "feedback": """✓ Richtig: Eine Zeitleiste mit einer Spur pro Figur macht sichtbar, in welchen Abschnitten des Films eine Figur erkannt wurde."""
        },
        {
            "answer": "Netzwerk der gemeinsamen Erkennungen",
            "correct": False,
            "feedback": """× Nicht korrekt: Das Netzwerk zeigt gemeinsame Erkennungen, nicht die zeitliche Verteilung."""
        },
        {
            "answer": "Tabelle mit den technischen Metadaten",
            "correct": False,
            "feedback": """× Nicht korrekt: Eine Metadatentabelle liefert Zahlen zum analysierten Material, aber keine anschauliche zeitliche Darstellung der Figurenerkennung."""
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

many_choice4 = [{
    "question": """Welche Aussagen lassen sich aus der im Kapitel beschriebenen Visualisierung der Einstellungsdaten direkt stützen?""",
    "type": "many_choice",
    "answers": [
        {
            "answer": "Goya hat die höchste Anzahl erkannter Einstellungen.",
            "correct": True,
            "feedback": """✓ Richtig: Im Kapitel werden 1074 Einstellungen für Goya genannt; das ist der höchste Wert im Korpus."""
        },
        {
            "answer": "Goya ist deshalb der stilistisch komplexeste Film.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das ist eine Wertung, die aus der Anzahl der Einstellungen allein nicht gefolgert werden kann. Dafür braucht es weitere Variablen und eine theoretische Begründung."""
        },
        {
            "answer": "Sterne hat die höchste ASL und MSL.",
            "correct": True,
            "feedback": """✓ Richtig: Sterne wird als Spitzenreiter bei ASL und MSL beschrieben."""
        },
        {
            "answer": "Die ASL sinkt im chronologischen Vergleich tendenziell.",
            "correct": True,
            "feedback": """✓ Richtig: Die chronologische Sortierung zeigt diesen Trend; Sterne und Goya bleiben auffällige Abweichungen."""
        },
        {
            "answer": "Die ASL allein beweist, dass das Publikum ungeduldiger wurde.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das ist ein kausaler Fehlschluss. Die Wahrnehmung von Schnittfrequenz ist historisch unterschiedlich und genreabhängig; es braucht Rezeptionskontext und qualitative Analyse."""
        }
    ]
}]

display_quiz(many_choice4, colors=colors.jupyterquiz)
```

## Aufgabe 5

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice5 = [{
    "question": """Sunny ist im Figurennetzwerk mit allen anderen Figuren verbunden. Was folgt daraus?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Sie hat zu allen Figuren eine gute Beziehung.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das Netzwerk zeigt gemeinsame Erkennung, nicht die Qualität einer Beziehung."""
        },
        {
            "answer": "Sie wurde in Szenen mit allen anderen Figuren gemeinsam erkannt.",
            "correct": True,
            "feedback": """✓ Richtig: Eine Verbindung entsteht, wenn Figuren im selben untersuchten Frame erkannt wurden. Das ist ein Hinweis auf gemeinsame Sichtbarkeit, nicht auf Interaktion."""
        },
        {
            "answer": "Sie spricht im Film mit allen Figuren.",
            "correct": False,
            "feedback": """× Nicht korrekt: Dialoge werden damit nicht erfasst."""
        },
        {
            "answer": "Sie ist die Regisseurin des Films.",
            "correct": False,
            "feedback": """× Nicht korrekt: Die Regie lässt sich aus dem Netzwerk nicht ableiten."""
        }
    ]
}]

display_quiz(multiple_choice5, colors=colors.jupyterquiz)
```

## Aufgabe 6

Betrachten Sie die Netzwerkgrafik zu „Der geteilte Himmel“.

1. Beschreiben Sie zwei deutlich erkennbare Figurengruppen.
2. Formulieren Sie je eine filmanalytische Hypothese zu den Gruppen.
3. Erläutern Sie, warum die Grafik diese Hypothesen nahelegt, aber nicht beweist.
4. Nennen Sie eine Möglichkeit, die Hypothesen am Film zu prüfen.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_Auswertung')
```

````{admonition} Musterlösung
:class: solution, dropdown

**Gruppen:**

Im unteren Bereich sind Figuren der Arbeitswelt versammelt (Kuhl, Meternagel, Ermisch, Wendland), rechts ist Schwarzenbach für die Universität positioniert. Im oberen Bereich stehen Herr und Frau Herrfurth sowie Martin für den privaten Bereich Ritas und Manfreds.

**Hypothesen:**

Die räumliche Anordnung könnte auf unterschiedliche soziale Sphären verweisen: Arbeitswelt, Universität und Privatleben. Die Nähe von Rita zu Meternagel und Wendland könnte auf ihre beruflichen und politischen Bezüge hindeuten; die Verbindung zu Martin auf eine private Beziehung.

**Warum nicht bewiesen:**

Das Netzwerk zeigt gemeinsame Erkennung in untersuchten Frames, nicht die Qualität oder Bedeutung einer Beziehung. Fehlende Verbindungen können durch übersehene Gesichter, Kamerawinkel oder Schwellenwerte entstehen. Die Position der Knoten ist kein eigenständiges Maß für Nähe.

**Prüfung:**

Die entsprechenden Szenen im Film sichten, in VIAN mit den Annotationen abgleichen und den Handlungskontext sowie den Produktionskontext einbeziehen.
````

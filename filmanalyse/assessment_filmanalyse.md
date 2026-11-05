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

Dieser Selbsttest bezieht sich auf das Kapitel **Filmanalyse und automatisierte Annotation**.

````{admonition} Wie nutze ich den Selbsttest?
:class: hinweis, dropdown
Diese Übungsaufgaben dienen Ihrer Selbsteinschätzung und helfen Ihnen, das im Kapitel Gelernte zu reflektieren.

Sie können die Fragen in beliebiger Reihenfolge bearbeiten und die Beantwortung auch mehrfach versuchen.

**So funktioniert es:**
- Wählen Sie bei jeder Frage die Antwort(en) aus, die Sie für richtig halten
- Lesen Sie das Feedback zu den einzelnen Antwortoptionen sorgfältig durch
- Die Erklärungen helfen Ihnen, Ihr Verständnis zu vertiefen – auch bei korrekten Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse. Nutzen Sie dieses Assessment, um Wissenslücken zu identifizieren und gegebenenfalls die entsprechenden Abschnitte des Kapitels nochmals zu bearbeiten.

**Geschätzte Zeit**: 15 Minuten

Viel Erfolg!
````

## Aufgabe 1

Ordnen Sie die drei Orientierungen den passenden filmanalytischen Beispielinteressen zu.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import DragDropQuiz

quiz = DragDropQuiz()

quiz.create_matching_quiz(
    title="Ordnen Sie die drei Orientierungen den passenden filmanalytischen Beispielinteressen zu.",
    descriptions=[
        "Inhaltsstruktur",
        "Textstruktur",
        "Rezeption"
    ],
    options=[
        "Welche Themen und Konflikte stehen im Zentrum?",
        "Wie lang sind die Einstellungen?",
        "Wie reagieren Zuschauer:innen auf den Schnitt?"
    ],
    correct_mapping={
        "Inhaltsstruktur": "Welche Themen und Konflikte stehen im Zentrum?",
        "Textstruktur": "Wie lang sind die Einstellungen?",
        "Rezeption": "Wie reagieren Zuschauer:innen auf den Schnitt?"
    }
)
```

````{admonition} Erläuterung
:class: solution, dropdown

- **Inhaltsstruktur:** Richtig, wenn Sie Themen, Figurenkonstellationen oder Konflikte zuordnen. Das Kapitel unterscheidet die Ausrichtung auf den Inhalt von der formalen Textstruktur und der Rezeption.
- **Textstruktur:** Richtig, wenn Sie formale Gestaltungsmittel wie Einstellungslängen, Montage oder Farbgestaltung zuordnen. Diese OER konzentriert sich auf diese Orientierung.
- **Rezeption:** Richtig, wenn Sie die Wahrnehmung und Reaktion von Zuschauer:innen zuordnen.
- **Typischer Fehler:** „Themen und Konflikte“ der Textstruktur zuzuordnen. Themen sind Inhalt, nicht Form.
````

## Aufgabe 2

Welche Aussagen zur Annotation sind korrekt? Wählen Sie alle zutreffenden Optionen.

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

many_choice2 = [{
    "question": """Welche Aussagen zur Annotation sind korrekt?""",
    "type": "many_choice",
    "answers": [
        {
            "answer": "Annotationen reichern Untersuchungsgegenstände mit Informationen an.",
            "correct": True,
            "feedback": """✓ Richtig: Das Kapitel definiert Annotation als semantische Anreicherung von Untersuchungsgegenständen."""
        },
        {
            "answer": "Annotationen sind das Endergebnis der Filmanalyse.",
            "correct": False,
            "feedback": """× Nicht korrekt: Annotationen sind Ausgangspunkte für die Analyse, keine Endergebnisse. Sie müssen interpretiert und kontextualisiert werden."""
        },
        {
            "answer": "Für audiovisuelle Medien fehlen bisher einheitliche Annotationsstandards.",
            "correct": True,
            "feedback": """✓ Richtig: Anders als bei Texten (TEI) oder Musik (MEI) existieren für audiovisuelle Medien keine vergleichbaren einheitlichen Standards."""
        },
        {
            "answer": "Automatisierte Annotationen interpretieren die Bedeutung eines Films.",
            "correct": False,
            "feedback": """× Nicht korrekt: Automatisierte Annotationen liefern Wahrscheinlichkeitsaussagen über formale Merkmale, nicht Interpretationen von Bedeutung."""
        }
    ]
}]

display_quiz(many_choice2, colors=colors.jupyterquiz)
```

## Aufgabe 3

Ein Film läuft 96 Minuten und hat 720 Einstellungen. Ein zweiter läuft 96 Minuten und hat 480 Einstellungen. Wie unterscheiden sich die ASL-Werte?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice3 = [{
    "question": """Ein Film läuft 96 Minuten und hat 720 Einstellungen. Ein zweiter läuft 96 Minuten und hat 480 Einstellungen. Wie unterscheiden sich die ASL-Werte?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "8 s vs. 12 s",
            "correct": True,
            "feedback": """✓ Richtig: 96 Minuten = 5.760 Sekunden. 5.760 / 720 = 8 s; 5.760 / 480 = 12 s. Der zweite Film hat bei gleicher Laufzeit weniger Einstellungen und damit eine längere durchschnittliche Einstellungslänge."""
        },
        {
            "answer": "12 s vs. 8 s",
            "correct": False,
            "feedback": """× Nicht korrekt: Hier sind die Filme vertauscht."""
        },
        {
            "answer": "Beide 8 s",
            "correct": False,
            "feedback": """× Nicht korrekt: Die unterschiedliche Anzahl der Einstellungen wird ignoriert."""
        },
        {
            "answer": "Nicht berechenbar",
            "correct": False,
            "feedback": """× Nicht korrekt: Laufzeit und Anzahl der Einstellungen sind gegeben; die ASL ist berechenbar."""
        }
    ]
}]

display_quiz(multiple_choice3, colors=colors.jupyterquiz)
```

## Aufgabe 4

Welche Aufgabe lässt sich mit den im Kapitel genannten Verfahren derzeit am zuverlässigsten automatisieren?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice4 = [{
    "question": """Welche Aufgabe lässt sich mit den im Kapitel genannten Verfahren derzeit am zuverlässigsten automatisieren?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Erkennung von Einstellungswechseln",
            "correct": True,
            "feedback": """✓ Richtig: Die Erkennung von Einstellungswechseln ist ein etabliertes Verfahren und bildet die Grundlage für viele weitere Annotationen."""
        },
        {
            "answer": "Erkennung von Einstellungsgrößen",
            "correct": False,
            "feedback": """× Nicht korrekt: Einstellungsgrößen lassen sich nach dem Kapitel bislang nicht zuverlässig automatisiert erkennen."""
        },
        {
            "answer": "Erkennung von Kamerabewegungen",
            "correct": False,
            "feedback": """× Nicht korrekt: Figuren- und Kamerabewegungen sind in der Regel nicht gut automatisiert annotierbar."""
        },
        {
            "answer": "Erkennung von Figurenbewegungen",
            "correct": False,
            "feedback": """× Nicht korrekt: Figurenbewegungen sind nach dem Kapitel in der Regel nicht gut automatisiert annotierbar."""
        }
    ]
}]

display_quiz(multiple_choice4, colors=colors.jupyterquiz)
```

## Aufgabe 5

Was ist mit „Scalable Viewing“ gemeint?

```{code-cell} ipython3
:tags: [remove-input]
from jupyterquiz import display_quiz
import sys
sys.path.append("..")
from quadriga import colors

multiple_choice5 = [{
    "question": """Was ist mit „Scalable Viewing“ gemeint?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Nur die Analyse möglichst großer Datenmengen.",
            "correct": False,
            "feedback": """× Nicht korrekt: Große Datenmengen sind ein Anlass, aber nicht der Kern des Konzepts."""
        },
        {
            "answer": "Der Wechsel zwischen Zoom-in und Zoom-out und damit zwischen verschiedenen Perspektiven auf das Material.",
            "correct": True,
            "feedback": """✓ Richtig: Scalable Viewing meint das Wechseln zwischen der Gesamtperspektive auf ein Korpus und dem gezielten Blick auf einzelne Filme, Szenen oder Bildbereiche. Dadurch entstehen pluralere Perspektiven."""
        },
        {
            "answer": "Die automatische Interpretation von Filmen durch ein Modell.",
            "correct": False,
            "feedback": """× Nicht korrekt: Die Interpretation bleibt eine Aufgabe der Forschenden; das Kapitel betont die Ergänzung durch qualitative Verfahren."""
        },
        {
            "answer": "Das Training eines Modells auf einem großen Filmkorpus.",
            "correct": False,
            "feedback": """× Nicht korrekt: Modelltraining ist nicht mit Scalable Viewing gleichzusetzen."""
        }
    ]
}]

display_quiz(multiple_choice5, colors=colors.jupyterquiz)
```

## Aufgabe 6 – Selbstreflexion: Eine quantitative Fragestellung entwickeln

Formulieren Sie eine Fragestellung zur quantitativen Filmanalyse, die Sie mit automatisiert erkannten Einstellungslängen und/oder Figurenpräsenz für das Korpus Konrad Wolf bearbeiten könnten. Benennen Sie:

1. die Forschungsfrage,
2. die benötigten Annotationsdaten,
3. warum die Frage mit quantitativen Daten bearbeitbar ist,
4. wo qualitative Interpretation oder Kontextwissen nötig bleibt.

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_Filmanalyse')
```

````{admonition} Musterlösung
:class: solution, dropdown

> **Fragestellung:** Verändert sich die Average Shot Length (ASL) in den Filmen Konrad Wolfs zwischen 1958 und 1980 systematisch, und lassen sich die Veränderungen mit Schaffensphasen oder Genres in Verbindung bringen?
>
> **Benötigte Daten:** Einstellungsgrenzen, Filmlänge, Anzahl der Einstellungen, Erscheinungsjahr und Genre der Filme.
>
> **Warum quantitativ bearbeitbar:** Die ASL ist aus Filmlänge und Einstellungsanzahl berechenbar; die Werte können über das Korpus verglichen und chronologisch sortiert werden.
>
> **Grenzen:** Die ASL allein beweist keinen Stil oder eine Ursache. Die Wahrnehmung von Schnittfrequenz ist historisch und genreabhängig; für die Interpretation braucht es filmhistorischen Kontext, qualitative Filmanalyse und die Prüfung der Annotationsqualität.
````

### Bewertungsraster

| Kriterium | 0 Punkte | 1 Punkt | 2 Punkte |
|---|---|---|---|
| Antwortbarkeit | Frage nicht mit Shot-/Figurendaten bearbeitbar | teilweise operationalisierbar | klar operationalisierbar |
| Korpus und Variablen | fehlen | teilweise genannt | präzise genannt |
| Filmwissenschaftlicher Bezug | fehlt | allgemein | begründet |
| Reflexion der Grenzen | fehlt | ansatzweise | quantitative und qualitative Ergänzung, Kontext |
| Formulierung | unklar | verständlich | präzise und wissenschaftlich |

````{admonition} Hinweise zur Selbstkorrektur
:class: hinweis, dropdown

- Wenn Ihre Frage nur ein Einzelphänomen beschreibt („Wie lang ist die längste Einstellung?“), fehlt der Vergleich oder die analytische Stoßrichtung.
- Wenn Sie nur ein Modell nennen, aber keine Daten und keine Begründung, bleibt die Frage unter der Anforderung der Aufgabenstellung.
- Wenn Sie die Grenzen der ASL nicht nennen, lesen Sie `filmanalyse/quantitativ.md` erneut, insbesondere die Abschnitte zur Kritik und zu Scalable Viewing.
````

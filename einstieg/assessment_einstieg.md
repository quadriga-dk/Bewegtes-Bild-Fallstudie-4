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

Dieser Selbsttest bezieht sich auf das Kapitel **Einstieg**.

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
    "question": """Was unterscheidet ein Jupyter Notebook von einem Jupyter Book?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Ein Notebook kann Code ausführen, ein Book nicht.",
            "correct": True,
            "feedback": """✓ Richtig: Ein Jupyter Notebook verbindet erklärenden Text mit ausführbarem Code und dessen Ausgaben. Ein Jupyter Book ist die Website, die solche Textseiten und Notebooks zusammenführt."""
        },
        {
            "answer": "Ein Book ist immer nur ein PDF.",
            "correct": False,
            "feedback": """× Nicht korrekt: Ein Jupyter Book ist primär eine im Browser lesbare Website; PDF ist nur ein mögliches Exportformat."""
        },
        {
            "answer": "Ein Notebook enthält keinen erklärenden Text.",
            "correct": False,
            "feedback": """× Nicht korrekt: Notebooks enthalten sowohl Code- als auch Textzellen."""
        },
        {
            "answer": "Ein Book benötigt immer eine GPU.",
            "correct": False,
            "feedback": """× Nicht korrekt: Für das Lesen eines Jupyter Books ist keine GPU nötig. GPU-Leistung kann erst bei rechenintensiven Modellen relevant werden."""
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
    "question": """Sie haben lokal kein Python installiert und möchten den Code im Browser ausführen. Welcher Modus passt?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Book-Only Mode",
            "correct": False,
            "feedback": """× Nicht korrekt: Im Book-Only Mode können Sie lesen und teilweise interagieren, aber den Code nicht selbst ausführen."""
        },
        {
            "answer": "Cloud Mode",
            "correct": True,
            "feedback": """✓ Richtig: Im Cloud Mode führen Sie die Notebooks über einen webbasierten Dienst wie Google Colab aus; eine lokale Python-Installation ist dafür nicht nötig."""
        },
        {
            "answer": "Local Mode",
            "correct": False,
            "feedback": """× Nicht korrekt: Der Local Mode setzt eine lokale Python- bzw. Jupyter-Umgebung voraus."""
        },
        {
            "answer": "Offline Mode",
            "correct": False,
            "feedback": """× Nicht korrekt: Einen „Offline Mode“ nennt das Kapitel nicht."""
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
    "question": """Welche Hardware können Sie in Google Colab für die Analyse auswählen?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "T4 GPU",
            "correct": True,
            "feedback": """✓ Richtig: Das Kapitel beschreibt die Auswahl einer T4 GPU über „Laufzeit → Laufzeittyp ändern“."""
        },
        {
            "answer": "Apple M1",
            "correct": False,
            "feedback": """× Nicht korrekt: Apple M1 ist eine lokale Hardwareoption, keine Colab-Auswahl."""
        },
        {
            "answer": "CUDA-CPU",
            "correct": False,
            "feedback": """× Nicht korrekt: CUDA ist eine Plattform für NVIDIA-GPUs, keine CPU."""
        },
        {
            "answer": "RTX 4090",
            "correct": False,
            "feedback": """× Nicht korrekt: Eine RTX 4090 ist keine im Kapitel genannte Standardoption in Colab."""
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
    "question": """Welche Aussage zu Python-Kenntnissen entspricht dem Kapitel?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Python-Kenntnisse sind zwingende Voraussetzung.",
            "correct": False,
            "feedback": """× Nicht korrekt: Die OER ist so angelegt, dass die kommentierten Codeblöcke auch ohne Programmierkenntnisse nachvollziehbar sein sollen."""
        },
        {
            "answer": "Python-Kenntnisse sind hilfreich, aber nicht notwendig.",
            "correct": True,
            "feedback": """✓ Richtig: Der Einstieg nennt Python-Kenntnisse als Vorteil, aber nicht als Bedingung."""
        },
        {
            "answer": "Python-Kenntnisse sind nur unter Windows nötig.",
            "correct": False,
            "feedback": """× Nicht korrekt: Das Betriebssystem ist dafür nicht ausschlaggebend."""
        },
        {
            "answer": "Python-Kenntnisse werden nur für VIAN gebraucht.",
            "correct": False,
            "feedback": """× Nicht korrekt: VIAN ist ein Annotationsprogramm mit grafischer Oberfläche; Python ist dafür nicht die Voraussetzung."""
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
    "question": """Woher beziehen Sie die aktuelle VIAN-Version?""",
    "type": "multiple_choice",
    "answers": [
        {
            "answer": "Über die GitHub-Releases des VIAN-Projekts",
            "correct": True,
            "feedback": """✓ Richtig: Das Kapitel verweist für die aktuellen Installationsdateien auf die GitHub-Releases; es gibt Versionen für macOS und Windows."""
        },
        {
            "answer": "Über den Apple App Store",
            "correct": False,
            "feedback": """× Nicht korrekt: VIAN wird nicht über den App Store vertrieben."""
        },
        {
            "answer": "Über PyPI",
            "correct": False,
            "feedback": """× Nicht korrekt: PyPI ist eine Plattform für Python-Bibliotheken, nicht für die VIAN-Installationsdateien."""
        },
        {
            "answer": "Über Hugging Face",
            "correct": False,
            "feedback": """× Nicht korrekt: Hugging Face ist im Kapitel eine Plattform für Machine-Learning-Modelle, nicht für VIAN."""
        }
    ]
}]

display_quiz(multiple_choice5, colors=colors.jupyterquiz)
```

## Aufgabe 6 – Selbstreflexion: Bin ich startklar?

Beantworten Sie für sich die folgenden Fragen, bevor Sie mit den Inhaltskapiteln beginnen.

| Frage | Ja | Teilweise | Nein | Wo nachlesen |
|---|---|---|---|---|
| Kann ich ein Jupyter Book von einem Jupyter Notebook unterscheiden? | ☐ | ☐ | ☐ | `einstieg/technische-voraussetzungen.md` |
| Weiß ich, in welchem Modus ich arbeiten möchte? | ☐ | ☐ | ☐ | `einstieg/technische-voraussetzungen.md` |
| Habe ich – falls nötig – einen Google-Account für Colab? | ☐ | ☐ | ☐ | `einstieg/technische-voraussetzungen.md` |
| Weiß ich, wie ich eine Code-Zelle ausführe? | ☐ | ☐ | ☐ | `einstieg/technische-voraussetzungen.md` |
| Habe ich verstanden, dass Python-Kenntnisse hilfreich, aber nicht nötig sind? | ☐ | ☐ | ☐ | `einstieg/vorkenntnisse.md` |
| Weiß ich, wofür ich VIAN benötige und wo ich es bekomme? | ☐ | ☐ | ☐ | `einstieg/technische-voraussetzungen.md` |

```{code-cell} ipython3
:tags: [remove-input]
import sys
sys.path.append("../quadriga")
from assessment import create_answer_box

create_answer_box('Assessment_Einstieg')
```

````{admonition} Musterlösung
:class: solution, dropdown

Ein möglicher Einstieg könnte so aussehen:

> Ich arbeite im Cloud Mode, weil ich keinen lokalen Python-Zugang habe. Ich habe einen Google-Account und weiß, dass ich in Colab eine T4 GPU auswählen kann. Python-Kenntnisse sind bei mir gering; ich werde die Kommentare in den Notebooks nutzen und die Codeblöcke einzeln ausführen. VIAN installiere ich erst, wenn ich die Annotationsdaten sichten möchte.
````

````{admonition} Hinweis zur Selbstkorrektur
:class: hinweis, dropdown

Wenn Sie mehrere Punkte mit „Nein“ beantwortet haben, lesen Sie zuerst die entsprechenden Abschnitte im Einstieg, bevor Sie mit Kapitel 1 beginnen. Das ist keine Bewertung, sondern eine Orientierungshilfe.
````

# Auswahl der Modelle
Die Auswahl eines Machine-Learning-Modells hängt davon ab, welche Aufgabe es erfüllen soll und wie die Ergebnisse weiterverwendet werden. Existierende Literatur wie die im vorherigen Abschnitt erwähnten Fallstudien des Distant Viewing Labs können dabei helfen, sich einen ersten Überblick über die Möglichkeiten der ML-gestützten Annotation zu verschaffen. Je nach Fragestellung können auch Modelle genutzt werden, die nicht zur Annotation von Videomaterial vorgesehen sind.  sondern von Bildern vorgesehen sindDarüber hinaus können auch im Fall von Filmen auch Ton und Untertitel ausgewertet werden.


## Recherche
Nachdem ein grundlegendes Verfahren ausgewählt wurde, kann auf unterschiedlichen Plattformen anhand von englischen Stichworten gesucht werden. In der Vorbereitung zu dieser OER haben wir u.a.  diese Stichworte verwendet:

- Shot detection
- Face detection
- Object detection
- Depth detection
- image captioning

Auf [**Hugging Face**](https://huggingface.co) lassen sich Machine-Learning-Modelle suchen und vergleichen. Zu vielen Modellen gibt es Angaben zu ihrer vorgesehenen Anwendung, den Trainingsdaten und der Nutzung. Diese Angaben bieten eine erste Orientierung, ihre Qualität und Vollständigkeit kann jedoch unterschiedlich sein. Im Reiter 'Models' können außerdem Modelle gefiltert werden unter anderem nach 'Tasks', also nach Verfahren: 

```{figure} ../assets/annotation/huggingface.png
---
align: center
width: 100%
name: Huggingface_interface
alt: Die Suchmaske von Huggingface mit Filteroptionen.
---
Die Suchmaske von Huggingface mit Filteroptionen.
```

Auf [**arXiv**](https://arxiv.org) kann hingegen nach wissenschaftlichen Arbeiten aus dem Bereich Machine-Learning gesucht wurden. Die Veröffentlichungen erläutern häufig, wie ein Modell entwickelt und getestet wurde. Ein dort verfügbarer Text kann ein Preprint sein und muss nicht bereits ein Peer-Review-Verfahren durchlaufen haben. Deshalb sollte geprüft werden, ob und wo die Arbeit später veröffentlicht wurde. 

Auf [**PyPI**](https://pypi.org) lassen sich Python-Bibliotheken finden, die sich installieren und in eigene Arbeitsabläufe einbinden lassen. Die Einträge enthalten unter anderem Angaben zu Versionen und Abhängigkeiten. Häufig adaptieren die Bibliotheken existierende Machine-Learning Modelle für Python und werden von Personen unterhalten, die nicht an der Entwicklung des ursprünglichen Modells bearbeitet waren. Solche inoffiziellen Bibliotheken können in ihrer Qualität stark variieren und sich in ihrer Anwendungen zu offiziellen Anwendungsbeispielen unterscheiden. 

Ergänzend bietet sich [**GitHub**](https://github.com) an. Dort können Quellcode, Dokumentation und Beispiele eines Projekts gefunden werden. Hinweise wie aktuelle Änderungen oder offene Fehlerberichte können bei der Einschätzung der technischen Nutzbarkeit helfen. Zudem kann auf Fehler im Code hingewiesen oder Anwendungsfälle diskutiert werden.

## Auswahl für die Einstellungsanalyse
Für die Erkennung von Einstellungsübergängen fiel die Wahl auf das Modell [**TransNetV2**](https://arxiv.org/abs/2008.04838). Das Verfahren wird vom Distant Viewing Lab und in VIAN verwendet und ist in weiteren Projekten sowie wissenschaftlichen Arbeiten aufgegriffen worden. Diese Verbreitung sprach dafür, das Modell ebenfalls zu verwenden, um Vergleiche zu anderen Projekten zu ermöglichen. Bekanntheit und Zitierhäufigkeit allein sind jedoch kein Beleg für die Eignung in jedem Forschungskontext und für jedes Videomaterial. Die Ergebnisse müssen weiterhin am Material gesichtet und geprüft werden.


## Auswahl für die Gesichtsanalyse
Für die Gesichtsanalyse haben wir mehrere verbreitete Modelle beziehungsweise Python-Bibliotheken verglichen.
Begonnen haben wir mit [**Deepface**](https://github.com/serengil/deepface), einer Python-Bibliothek, die mehrere Modelle zur Face Detection und Face Recognition zusammenführt **[Anmerkung: wollen wir die deutschen Begriffe stattdessen verwenden? Die sind allerdings etwas sperrig: Gesichtsdetektion und Biometrische Gesichtserkennung]**. So konnten wir uns einen Überblick über unterschiedliche Modelle mit unterschiedlicher Präzision und Geschwindigkeit verschaffen.

Schließlich haben wir uns jedoch für die Modell-Pakete von Insightface entschieden, die Modelle zur Face Detection und Face Recognition verbinden und so den Code im Jupyter Notebook vereinfachen. Zudem stellte sich in unseren Tests die Genauigkeit und GPU-Beschleunigung der Modelle als ausgezeichnet heraus. Worum genau es sich bei dieser Beschleunigung handelt erläutert das nächste Kapitel zu den [technischen Grundlagen](technik.md). 
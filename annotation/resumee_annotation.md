# Resümee
In diesem Kapitel werden Workflows zur automatisierten Filmannotation vorgestellt und anhand konkreter Beispiele durchgeführt. Dabei werden folgenden Teilbereichen behandelt:

```{admonition} Keypoints
:class: keypoint

**Entwicklung des Workflows**

Für die automatisierte Annotation von Film- und Videodateien haben wir einen Workflow mit verschiedenen Schritten entwickelt und dargestellt. Es müssen Parameter und Schwellenwerte festgelegt werden, das Analysematerial vorbereitet und eingelesen werden und für die Annotation passende Modelle angewendet werden. Schließlich werden die Annotationsergebnisse in verschiedenen Formaten ausgegeben, überprüft und ausgewertet.

**Auswahl von Modellen**

Für unsere Fallstudie haben wir uns für die Annotation von Einstellungsübergängen und das Auftreten von Figuren in Filmen entschieden. Wir haben beschrieben, wie nach geeigneten Modellen zur Film-Annotation recherchiert werden kann und welche Kriterien dabei beachtet werden sollten, z.B. der ursprüngliche Einsatzbereich und der Entstehungskontext. Für die Einstellungs-Annotation haben wir uns für das TransNetV2 Modell entschieden, das weit verbreitet und gut dokumentiert ist, zudem liefert es gute Ergebnisse. Für die Figurenerkennung bzw. die dafür notwendige Gesichtsanalyse kommen Modell-Pakete von Insightface zum Einsatz. Insightface kombiniert verschiedene Pakete und liefert eine sehr gute Genauigkeit bei der Erkennung und Zuordnung der Gesichter bzw. Figuren.


**Python-Skripte zur Einstellungs- und Figurenerkennung**

Für die Einstellungs- und Figurenerkennung haben wir Python-Skripte entwickelt und in Form von Jupyter Notebooks umgesetzt. Diese Notebooks ermöglichen eine ausführliche Erklärung der Funktion einzelner Code-Teile. Somit werden die einzelnen Schritte, die für die jeweiligen Annotationsprozesse und Anwendung der Modelle notwendig sind, deutlich gemacht. Einzelne Parameter wie Schwellenwerte und Speicherorte von Dateien können in diesen Notebooks verändert und für verschiedene Annotationsprojekte angepasst werden. Am Ende steht die Ausgabe der Annotationsdaten in verschiedenen Dateiformaten zur Überprüfung der Ergebnisse und zur Auswertung der Annotationen.


**Sichtung und Überprüfung der Ergebnisse in VIAN**

Mithilfe der von den Notebooks ausgegebenen `.eaf-Datei` lassen sich die Annotationsdaten in das Annotationstool VIAN importieren. Dort werden die Annotationsergebnisse als einzelne Spuren dargestellt und es kann überprüft werden, wie genau und korrekt die Annotationen automatisiert erstellt wurden. Finden sich Abweichungen in den Annotationen, kann versucht werden, die Ergebnisse mit veränderten Schwellenwerten zu verbessern. Ebenso ist eine manuelle Korrektur der Resultate der Annotation mit VIAN möglich.

```

Es hat sich gezeigt, dass sie Ergebnisse der automatisierten Annotation von Videodateien zwar nicht fehlerfrei sind, aber dennoch die Grundlage für eine weitere Auswertung bilden können.

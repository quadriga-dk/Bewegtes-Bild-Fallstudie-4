# Entwicklung des Workflows

Im vorherigen Abschnitt wurden Verfahren zur automatisierten Annotation von Filmen vorgestellt. Hier geht es um den Workflow, der diesen Verfahren zugrunde liegt. Er lässt sich auch für andere Analyseaufgaben anpassen, etwa indem ein anderes Machine-Learning-Modell eingebunden wird.
Der Ablauf orientiert sich an der Pipeline for Distant Viewing von Taylor Arnold und Lauren Tilton (2023, S. 34–36). Arnold und Tilton übertragen dabei einen in der Datenwissenschaft verbreiteten Arbeitsablauf auf die Analyse von Bild- und Filmmaterial.

```{figure} ../assets/annotation/DistantViewing_Pipeline.png
---
align: center
width: 100%
name: DistantViewing_Pipeline
alt: Visualisierung der von Arnold und Tilton entwickelten Distant Viewing Pipeline.
---
Visualisierung der von Arnold und Tilton (2023) entwickelten Distant Viewing Pipeline (p. 35).
```

Für die hier vorgestellten Verfahren orientieren wir uns außerdem am Distant Viewing Toolkit und an den dazugehörigen Jupyter Notebooks. Unser Workflow gliedert die Analyse in mehrere Schritte. Zuerst werden die benötigten Einstellungen festgelegt und die technische Arbeitsumgebung vorbereitet. Dann werden die Daten eingelesen und analysiert. Zum Schluss werden die Ergebnisse aufbereitet, exportiert und geprüft.

**[Anmerkung für Tom]:** Das oben könnte ggf. auch als Admonition gesetzt werden. Zudem wäre eine Verlinkung sinnvoll, darum kann ich mich später kümmern.
https://github.com/distant-viewing/dvt
https://colab.research.google.com/drive/1VpaZn0G52aLiI4C2TG1ti_jR3umnYq4Q?usp=share_link

Die hier für diese Schritte verwendeten Bezeichnungen finden sich auch in den Jupyter Notebooks wieder, sodass jeder Abschnitt einer konkreten Funktion zugeordnet werden kann.


## Festlegen von Parametern und Schwellwerten

Zu Beginn eines jeden Notebooks werden die Einstellungen festgelegt, die das Jupyter Notebook zu seiner Ausführung benötigt. Wir unterscheiden für diese Einstellungen zwischen *Parametern* und *Schwellwerten*. Auf technischer Ebene sind Parameter und Schwellwerte *Variablen*: benannte Platz-Halter für einen Wert, der im Code Anwendung findet. 

Parameter legen zum Beispiel fest, wo die Eingabedateien liegen, wohin Ergebnisse gespeichert werden oder welche Frames eines Films analysiert werden sollen. 

Schwellwerte bestimmen, ab welchem Wert ein Analyseergebnis als Treffer gilt. Bei der automatisierten Erkennung von Einstellungsübergängen kann ein Verfahren beispielsweise für jeden möglichen Übergang einen Wahrscheinlichkeitswert berechnen. Ein Schwellwert von 0,5 bedeutet dann, dass Werte ab 0,5 als erkannte Übergänge behandelt werden.
Ein höherer Schwellwert führt tendenziell zu weniger, dafür sichereren Treffern. Ein niedrigerer Schwellwert kann mehr mögliche Übergänge erfassen, aber auch mehr falsche Treffer erzeugen. 

Die Wahl der passenden Werte hängt davon ab, was die Analyse leisten soll, um welches Filmmaterial es sich handelt und wie die Ergebnisse anschließend verwendet werden sollen.

## Technische Vorbereitung

Bevor die Analyse beginnen kann, muss die Programmierumgebung vorbereitet werden. Dazu gehören die Installation und der Import von Programmbibliotheken, die Bereitstellung des Analysematerials und gegebenenfalls der Download und das Konfigurieren eines Machine-Learning-Modells.

### Installation der Programmbibliotheken
Programmbibliotheken sind Sammlungen vorgefertigter Funktionen, die eine Programmiersprache um zusätzliche Möglichkeiten erweitern. Für eine Filmanalyse können beispielsweise Bibliotheken benötigt werden, um Videos einzulesen, Tabellen zu bearbeiten, ein Machine-Learning-Modell auszuführen oder Annotationsdateien zu erstellen.

Die Installation fügt die benötigten Bibliotheken zur Programmierumgebung hinzu. In einer lokalen Umgebung müssen bereits installierte Bibliotheken normalerweise nicht bei jeder Sitzung erneut installiert werden. Bei cloudbasierten Umgebungen wie Google Colab wird die Umgebung typischerweise nach dem Beenden zurückgesetzt. Daher müssen dort die Bibliotheken bei einer neuen Sitzung erneut installiert werden.


### Import der Programmbibliotheken
Nach der Installation müssen die Bibliotheken noch importiert werden. Beim Import wird Python mitgeteilt, welche Bibliotheken in der aktuellen Sitzung verwendet werden sollen. Eine installierte Bibliothek ist also nicht automatisch für jeden Code verfügbar, erst durch den Import kann  auf ihre Funktionen zugegriffen werden.

Manche Arbeitsabläufe verwenden außerdem Funktionen aus der Standardbibliothek von Python, die zwar importiert, aber nicht separat installiert werden müssen.

### Download des Analysematerials
Die zu analysierenden Dateien können lokal abgelegt oder aus einer Onlinequelle heruntergeladen werden.

In den Jupyter Notebooks werden die Trailerdateien zur Analyse aus einem Online-Repositorium heruntergeladen und in einem Ordner abgelegt  – alternativ können zudem eigene Videodateien heruntergeladen werden.

### Vorbereitung des ML-Modells

Wenn ein Verfahren ein Machine-Learning-Modell verwendet, muss dieses vor der Analyse noch vorbereitet werden. Dazu gehören je nach Verfahren etwa dessen Download und Konfiguration. Etwa ist es wichtig, ein Modell vor der Analyse vom Trainingsmodus in den Evaluationsmodus zu versetzen. In diesem Modus berechnet es Vorhersagen, statt weiter trainiert zu werden.

## Einlesen und Analyse des Videomaterials
Nun beginnt die eigentliche Analyse. Welche Schritte dabei konkret nötig sind, hängt von der Analysemethode ab.

### Erfassung der technischen Videometadaten
Zunächst werden die abgelegten Videodateien erfasst, ihr Ablageort gespeichert und Metadaten wie Auflösung und Laufzeit ermittelt. Metadaten helfen insbesondere dabei, Analyseergebnisse einzuordnen.

### Anwendung des Modells
Nachdem Videodateien vorbereitet sind, wird das ausgewählte Analyseverfahren auf die Daten angewendet. Bei einer automatisierten Erkennung von Einstellungsübergängen kann das Verfahren beispielsweise für einzelne Frames berechnen, wie wahrscheinlich ein Übergang ist. Andere Methoden erkennen möglicherweise Objekte, Gesichter oder weitere visuelle Merkmale.

Hier unterscheidet sich das Vorgehen erheblich nach dem gewählten Verfahren, etwa danach ob ein Film zuerst in Frames aufgeteilt werden muss oder nicht. Parameter und Schwellwerte kommen insbesondere während dieses Schritts zum Einsatz und bestimmen maßgeblich das Ergebnis der Analyse.

### Tabellarische Aufbereitung des Ergebnisses
Analyseergebnisse liegen zunächst oft in einer Form vor, die sich nur schwer weiterverarbeiten lässt, etwa als Liste von Werten. Bevor die Ergebnisse exportiert und weiterverarbeitet werden können, müssen diese daher in ein tabellarisches Format transformiert werden. 

### Berechnung der Analysemetadaten
Anschließend Metadaten zum Analyseergebnis gesammelt und berechnet.
Hierzu gehören etwa die gewählten Parameter, Schwellwerte und Dauer der Analyse, aber auch Durchschnittswerte des eigentlichen Ergebnisses. 

## Export der Ergebnisse
Die Ergebnisse sind damit soweit aufbereitet, das sie auch außerhalb von Python weitergenutzt werden können. Zu diesem Zweck müssen sie in externe, interoperable Formate **exportiert** werden. 

### Export der Tabellen als CSV-Datei
Ein dabei besonders häufig verwendetes Format ist **CSV** (**c**omma **s**eparated **v**alues). Das Format speichert tabellarische Daten als Text, in dem Werte durch Komma als Trennzeichen voneinander abgegrenzt werden. CSV-Dateien lassen sich zum Beispiel in Tabellenkalkulationsprogramme wie Microsoft Exel oder OpenRefine importieren, eignen sich darüber hinaus aber auch zur Erstellung von Visualisierungen. 

### Export der Einstellungsannotationen als EAF-Datei
Für die Arbeit mit filmischen Material eignet sich zudem das Format **EAF**, das **E**LAN **A**nnotation **F**ormat. In diesem Format können Annotationen als Zeitabschnitte mit einem Start- und Endzeitpunkt gespeichert werden, ähnlich einer Untertitelspur.

Eine EAF-Datei kann in VIAN oder anderen geeigneten Annotationsprogrammen geöffnet und weiterbearbeitet werden. So können die automatisch erstellten Annotationen gemeinsam mit dem analysierten Video gesichtet, korrigiert und inhaltlich ergänzt werden.

## Sichtung der Ergebnisse
Da es während der automatisierten Annotation zu Fehler kommen kann, ist es essenziell, das Ergebnis zu sichten.
Während einer Sichtung sollten falscher oder übersehene Treffer korrigiert, aber auch die generelle Qualität des Verfahrens eingeschätzt werden. Häufig bedürfen etwa die Parameter und Schwellwerte einer Feinjustierung, die vom jeweiligen Film abhängig ist und erst nach einem ersten Durchlauf eingeschätzt werden kann.

Innerhalb dieser OER verwenden wir zur Sichtung **VIAN**: ein open-source Annotationsprogramm für die Filmanalyse, das momentan an der Universität Zürich entwickelt wird. In VIAN können die Ergebnisse als EAF-Format importiert und mit dem analysierten Videomaterial verknüpft werden. So lassen sich Annotationen framegenau mit dem Material abgleichen, anhand dessen sie erstellt wurden. 

Das spätere Kapitel zu den [Technischen Grundlagen](technik.md) führt in die Installation und Nutzung von VIAN ein.

## Visualisierung der Ergebnisse
Ein Mittel zur explorativen Auswertung der Ergebnisse ist die Datenvisualisierung. Eine Visualisierung ist typischerweise der erste Schritt in der Auswertung und kann u.a. dabei helfen, Forschungsfragen zu präzisieren. Welche Visualisierung sinnvoll ist, hängt jedoch vom initialen Forschungsinteresse ab – die selben Daten lassen sich in einer Vielzahl von Varianten visualisieren. 

Zur Erstellung von Visualisierungen können Programme zur Tabellenkalkulation wie Microsoft Excel oder Online Plattformen wie Datawrapper genutzt werden. Im Rahmen dieser OER verwenden wir allerdings auch für die Visualisierung die Programmiersprache Python, um Visualisierungen mit interaktiven Elementen zu erstellen. 

## Spezifische Implementierung
Wie bereits in diesem Abschnitt angeklungen, ist das gewählte Verfahren dafür ausschlaggebend, wie dieser Workflow im Detail ausgestaltet wird. Ein Machine-Learning Modells gibt bereits vor, welcher Input, welche Ausgaben, und welche Einstellungen in Form von Parametern und Schwellwerten im Code berücksichtigt werden müssen. Umso entscheidender ist es, ein zum eingenen Forschungsinteresse passendes Modell auszuwählen. Das folgende Kapitel widmet sich genau diesem Prozess. 
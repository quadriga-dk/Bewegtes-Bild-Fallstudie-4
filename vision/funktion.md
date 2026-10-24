# Funktionsweise Computer Vision
Nachdem in den letzten Abschnitten einige Grundlagen und zentrale Begriffe geklärt worden sind, werden wir nun auf die Funktionsweise und Abläufe bei Computer Vision näher eingehen, insbesondere auch im Hinblick auf die automatisierte Annotation von Filmen.

Zu Beginn muss zunächst festgelegt werden, welches Material - in unserem Fall welcher Film oder welche Filme - annotiert wird und welche Art von Annotationen durch Computer Vision erstellt werden sollen. Annotationen können dabei ganz unterschiedliche Formen annehmen, wie Taylor Arnold und Lauren Tilton herausarbeiten {cite}`bc-Arnold_Tilton_2023`:
- numerische Werte: z.B. wie viele Personen sind im Bild, wie viel Prozent des Bildes nimmt der Hintergrund ein etc.
- Kategorisierungen: z.B. Bild als Landschaft oder Porträt
- dominante Farben
- Namen von Objekten im Bild
- Verortung von Personen im Bild
- Beschreibungen des Bildinhalts
- etc.

Es sind also eine Vielzahl unterschiedlicher Annotationen denkbar. Arnold und Tilton weisen auch darauf hin, dass nie alle Informationen in einem Bild durch strukturierte Annotationen erfasst werden können. Es existiert also immer auch ein Unterschied zwischen den Informationen im Originalbild und den extrahierten Annotationsinformationen {cite}`bc-Arnold_Tilton_2023`. Entscheidend für die Art der Annotation ist auch, ob und welche [Algorithmen](../vision/begriffe.md#algorithmus) oder [Modelle](../vision/begriffe.md#modell) für die Erkennung durch Computer Vision überhaupt zur Verfügung stehen.

Nach der Festlegung des Materials und der Art der Annotationen folgen verschiedene weitere Schritte, die in der folgenden Grafik zusammengefasst sind:

```{figure} ../assets/annotation/Grafik_Funktionsweise.png
---
align: center
width: 100%
name: Grafik Funktionsweise
alt: Schritte Funktionsweise Computer Vision.
---
Schritte Funktionsweise Computer Vision.
```

Wichtig ist hierbei zu bedenken, dass es sich bei diesen Schritten um einen schematisierten, grundlegenden Ablauf handelt. In der Praxis können sich die einzelnen Schritte überschneiden oder auch gleichzeitig ausgeführt werden.

Als erster Schritt kann eine **Vorverarbeitung** der Bilddateien bzw. Videodateien erfolgen, bevor ein Code oder ein Modell auf das Material angewendet wird. Damit ist eine technische Bearbeitung der Bilder gemeint, bei der z.B. versucht werden kann, die Qualität zu verbessern. Dies kann bei schlechtem Ausgangsmaterial wie etwa Digitalisaten von alten Videokassetten oder schlecht erhaltenen analogen Filmen sinnvoll sein. In den Bereich der Vorverarbeitung fällt etwa auch die Auswahl von Bilddateien, die als Referenz für die weitere Verarbeitung des zu untersuchenden Materials dienen. Dies ist in unserem Beispiel z.B. bei der Auswahl geeigneter Screenshots von Figuren der Fall, die als Vorlage für die [Erkennung von Figuren](../annotation/figuren_intro.md) dienen.

Für den nächsten Schritt der **Dateneingabe** muss zunächst eine Datengrundlage geschaffen werden. Im Fall von Computer Vision bei Filmen müssen hierfür aus der digitalen Videodatei einzelne Bilder - also Frames - extrahiert werden. Die Modelle zur Computer Vision werden nämlich in der Regel nicht auf die "bewegten Bilder" sondern jeweils auf einzelne Bilder nacheinander angewendet. Diese Frames werden dann für die weitere Verarbeitung importiert.

Beim Schritt der **Verarbeitung** finden alle Prozesse statt die notwendig sind, um ein Modell oder einen Algorithmus auf das Material anzuwenden. Dabei können je nach angewendeten Verfahren und Annotationsziel unterschiedliche Schritte notwendig sein. Bei unserem Fallbeispiel werden etwa verschiedene Metadaten aus der Videodatei extrahiert, die für eine weitere Verarbeitung erforderlich sind, wie z.B. der Ablageort der Videodatei, die Auflösung, die Bildrate oder die Laufzeit des Videos (vgl Kapitel [Erfassung der technischen Videometadaten](../annotation/einstellungen_notebook.ipynb#erfassung-der-technischen-videometadaten)). Auch die Erstellung von [Vergleichsembeddings](../annotation/figuren_intro.md#vergleichs-embeddings-zur-figurenerkennung) zur Figurenerkennung fällt in diesen Bereich. Bei entsprechenden Annotationen können in der Verarbeitung auch nur Teilgebiete des Bildes ausgewählt und ausgeschnitten werden, also spezielle "Regions of Interest" (ROI) festgelegt werden. Dabei muss bedacht werden, dass somit auch andere Informationen im Bild, die außerhalb des ausgeschnittenen Bereichs liegen, verloren gehen können.

Nachdem das Analysematerial vorbereitet wurde, findet nun die **Auswertung** statt und das ausgewählte **Modell wird angewendet**. Es werden also bestimmte Merkmale aus den Bildern extrahiert. Wie oben bereits erwähnt müssen für die gewünschten Annotationen passende Modelle gesucht werden, die entsprechenden Merkmale und Muster in der Datengrundlage der einzelnen Bilder erkennen können. Hierbei können auch mehrere Modelle nacheinander angewendet werden. Bei der [Figurenerkennung](../annotation/figuren_intro.md#grundlagen-der-gesichtserkennung) wird z.B. zunächst mit einem Modell ein Gesicht oder Gesichter in einem Bild erkannt (face detection) und daran anschließen mit einem anderen Modell das erkannte Gesicht einer Person zugeordnet (face recognition). Auf diesen Prozess werden wir in einem [eigenen Kapitel](../annotation/figuren_intro.md) noch genauer eingehen. Die Kombination von verschiedenen Modellen mit spezifischen Aufgaben und aus oft ganz unterschiedlichen Anwendungsbereichen kann also sinnvoll sein. Aus existierenden Modellen wird somit etwas Neues zusammengesetzt und es werden neue Funktionen geschaffen. Für diese Auswertung müssen aber nicht immer Machine Learning oder Deep Learning zur Anwendung kommen. Dies geschieht meist bei sehr komplexen Erkennungsaufgaben. Bei der Erkennung von Farben oder Kanten in Bildern finden etwa mathematische Berechnungen auf der Grundlage von einfachen algorithmischen Verfahren statt.

Bei der Ausführung von Modellen kann es sinnvoll sein, diese nicht auf alle aus einer Videodatei extrahierten Frames anzuwenden. Je nach Modell und Komplexität der Aufgabe kann die Erkennung durchaus erhebliche Zeit und Rechenleistung in Anspruch nehmen. In solchen Fällen können durch einen festgelegten Wert eine bestimmte Anzahl an Frames in der Abfolge bei der Analyse übersprungen und damit die Annotationsdauer verkürzt werden. Hier muss beachtet werden, ob die Reduzierung der Anzahl von analysierten Frames die Qualität der Annotation beeinträchtigt.

Schließlich werden auf die von dem Modellen erzeugten Werte **Schwellenwerte angewendet**. Wie im vorigen Abschnitt erläutert legen [Schwellenwerte](../vision/begriffe.md/#schwellenwert) fest, was als 'richtig' erkanntes Merkmal gilt und in die Annotationsdaten eingehen soll. Daher sollte genau geprüft und begründet werden, welche Schwellenwerte festgelegt werden.

Abschließend erfolgt nun die **Ausgabe der Annotationsdaten** in strukturierter Form, z.B. als Wahrscheinlichkeitswerte, Koordinaten eines Gesichts in einem Bild, Werte zum Farbverlauf etc. Diese Werte können zur Auswertung weiter verarbeitet werden, etwa durch Erstellen von Visualisierungen oder Berechnungen (z.B. Einstellungslängen aus erkannten Einstellungswechseln, durchschnittliche Einstellungslängen...). Gegebenenfalls kann eine Überprüfung der ausgegebenen Annotationsdaten notwendig sein. Werden z.B. Einstellungswechsel oder Gesichter exakt genug erkannt? Durch Veränderung von Schwellenwerten oder die Anwendung von alternativen Modellen können evtl. bessere Annotationsergebnisse erzielt werden.


## Literatur
```{bibliography}
:filter: docname in docnames
:keyprefix: bc-
```
# Funktionsweise Computer Vision
Nachdem in den letzten Abschnitten einige Grundlagen und zentrale Begriffe geklärt worden sind, werden wir nun auf die Funktionsweise und Abläufe bei Computer Vision näher eingehen, insbesondere auch im Hinblick auf die automatisierte Annotation von Filmen.

**hier evtl. Überblicksgrafik mit Schritten einfügen**

Zu Beginn muss zunächst festgelegt werden, welches Material - in unserem Fall welcher Film oder welche Filme - annotiert wird und welche Art von Annotationen durch Computer Vision erstellt werden sollen. Annotationen können dabei ganz unterschiedliche Formen annehmen, wie Taylor Arnold und Lauren Tilton herausarbeiten {cite}`bc-Arnold_Tilton_2023`:
- numerische Werte: z.B. wie viele Personen sind im Bild, wie viel Prozent des Bildes nimmt der Hintergrund ein etc.
- Kategorisierungen: z.B. Bild als Landschaft oder Porträt
- dominante Farben
- Namen von Objekten im Bild
- Verortung von Personen im Bild
- Beschreibungen des Bildinhalts
- etc.

Es sind also eine Vielzahl unterschiedlicher Annotationen denkbar. Arnold und Tilton weisen auch darauf hin, dass nie alle Informationen in einem Bild durch strukturierte Annotationen erfasst werden können. Es existiert also immer auch ein Unterschied zwischen den Informationen im Originalbild und den extrahierten Annotationsinformationen {cite}`bc-Arnold_Tilton_2023`. Entscheidend für die Art der Annotation ist auch, ob und welche [Algorithmen](../vision/begriffe.md#algorithmus) oder [Modelle](../vision/begriffe.md#modell) für die Erkennung durch Computer Vision überhaupt zur Verfügung stehen.

Für die **Dateneingabe** muss zunächst eine Datengrundlage geschaffen werden. Im Fall von Computer Vision bei Filmen müssen hierfür aus der digitalen Videodatei einzelne Bilder - also Frames - extrahiert werden. Die Modelle zur Computer Vision werden nämlich in der Regel nicht auf die "bewegten Bilder" sondern jeweils auf einzelne Bilder nacheinander angewendet. Da bei Videodateien meist von 25 einzelnen Bildern pro Sekunde ausgegangen werden kann, ergibt sich hier sehr schnell eine sehr große Anzahl von Bildern, die analysiert werden müssen. Dies hat Auswirkungen auf die Dauer des Computer Vision Prozesses und auch auf die hierfür benötigte Rechenleistung. Daher kann es bereits an dieser Stelle sinnvoll sein, nicht alle Frames zu extrahieren, sondern sich auf eine kleinere Zahl zu beschränken, z.B. auf ein Frame pro Minute. Diese Beschränkung sollte jedoch begründet werden und es sollte bedacht werden, ob die beabsichtige Annotation mit einer kleineren Anzahl von Frames noch sinnvoll möglich ist.

Als nächster Schritt kann eine **Vorverarbeitung** der Bilddateien bzw. extrahierten Frames erfolgen. Damit ist eine technische Bearbeitung der Bilder gemeint, bei der z.B. versucht werden kann, die Qualität zu verbessern. Dies kann bei schlechtem Ausgangsmaterial wie etwa Digitalisaten von alten Videokassetten oder schlecht erhaltenen analogen Filmen sinnvoll sein. Bei entsprechenden Annotationen können in der Vorverarbeitung auch nur Teilgebiete des Bildes ausgewählt und ausgeschnitten werden, also spezielle "Regions of Interest" (ROI) festgelegt werden. So können ggf. auch Logos von Fernsehsendern entfernt werden, falls sich diese für die automatisierte Erkennung als störend erweisen sollten. Dabei muss bedacht werden, dass somit auch andere Informationen im Bild, die außerhalb des ausgeschnittenen Bereichs liegen, verloren gehen können.

Nachdem nun die Datengrundlage geschaffen wurde, wird nun das ausgewählte **Modell angewendet**, also bestimmte Merkmale aus den Bildern extrahiert. Wie oben bereits erwähnt müssen für die gewünschten Annotationen passende Modelle gesucht werden, die entsprechenden Merkmale und Muster in der Datengrundlage der einzelnen Bilder erkennen können. Hierbei können auch mehrere Modelle nacheinander angewendet werden. Bei der Figurenerkennung wird z.B. zunächst mit einem Modell ein Gesicht oder Gesichter in einem Bild erkannt (face detection) und daran anschließen mit einem anderen Modell das erkannte Gesicht einer Person zugeordnet (face recognition). Auf diesen Prozess werden wir in einem **eigenen Kapitel** noch genauer eingehen. Die Kombination von verschiedenen Modellen mit spezifischen Aufgaben und aus oft ganz unterschiedlichen Anwendungsbereichen kann also sinnvoll sein. Aus existierenden Modellen wird somit etwas Neues zusammengesetzt und es werden neue Funktionen geschaffen. 

Auch bei der Ausführung von Modellen kann es sinnvoll sein, diese nicht auf alle aus einer Videodatei extrahierten Frames anzuwenden. Je nach Modell und Komplexität der Aufgabe kann die Erkennung durchaus erhebliche Zeit und Rechenleistung in Anspruch nehmen. In solchen Fällen können durch einen festgelegten Wert eine bestimmte Anzahl an Frames in der Abfolge bei der Analyse übersprungen und damit die Annotationsdauer verkürzt werden. Auch hier muss beachtet werden, ob die Reduzierung der Anzahl von analysierten Frames die Qualität der Annotation beeinträchtigt.

Schließlich werden auf die von dem Modellen erzeugten Werte **Schwellenwerte angewendet**. Wie im vorigen Abschnitt erläutert legen [Schwellenwerte](../vision/begriffe.md/#schwellenwert) fest, was als 'richtig' erkanntes Merkmal gilt und in die Annotationsdaten eingehen soll. Daher sollte genau geprüft und begründet werden, welche Schwellenwerte festgelegt werden.

Abschließend erfolgt nun die **Ausgabe der Annotationsdaten** in strukturierter Form, z.B. als Wahrscheinlichkeitswerte, Koordinaten eines Gesichts in einem Bild, Werte zum Farbverlauf etc. Diese Werte können zur Auswertung weiter verarbeitet werden, etwa durch Erstellen von Visualisierungen oder Berechnungen (z.B. Einstellungslängen aus erkannten Einstellungswechseln, durchschnittliche Einstellungslängen...). Gegebenenfalls kann eine Überprüfung der ausgegebenen Annotationsdaten notwendig sein. Werden z.B. Einstellungswechsel oder Gesichter exakt genug erkannt? Durch Veränderung von Schwellenwerten oder die Anwendung von alternativen Modellen können evtl. bessere Annotationsergebnisse erreicht werden.


## Literatur
```{bibliography}
:filter: docname in docnames
:keyprefix: bc-
```
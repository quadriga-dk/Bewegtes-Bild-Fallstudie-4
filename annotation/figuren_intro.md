# Figurenerkennung: Einführung

Dieser Abschnitt widmet sich der Vorstellung des zweiten Jupyter Notebooks: der automatisierten Erkennung von Figuren in Filmen.

Auch dieses Notebook verwendet den [zuvor vorgestellten Workflow](workflow.md) und bezieht sich auf die [etablierten technischen Grundlagen](technik.md).

Das Notebook zur Einstellungserkennung hat mit TransNetV2 zugleich das technische Verfahren vorgestellt, mit dem dieses Modell Einstellungen erkennt. Für das Verfahren der Figurenerkennung – bzw. allgemein formuliert der Gesichtserkennung – existiert eine Vielzahl von Modellen, die ähnlich funktionieren. Dieser grundlegende Ablauf verändert sich nicht durch die Verwendung eines anderen Modells und wird voraussichtlich auch in naher Zukunft Bestand haben.

## Grundlagen der Gesichtserkennung

Der Ablauf der Gesichtserkennung lässt sich in vier Schritte einteilen:

- Detection
- Alignment
- Representation
- Recognition (beim Vergleich zweier Gesichter auch *Verification*)

Verfahren zur Gesichtserkennung gehen grundsätzlich davon aus, dass Einzelbilder analysiert werden. Im Folgenden ist daher von Bildern die Rede, die im Fall der Filmanalyse zuvor aus einer Videodatei extrahiert werden (siehe Abschnitt [Funktionsweise Computer Vision](../vision/funktion.md)).


### Detection

Im ersten Schritt *Detection* gilt es, Gesichter in einem Bild zu erkennen. Für diesen Prozess wird ein spezialisiertes ML-Modell benötigt. Die Position eines erkannten Gesichts wird anhand von vier Koordinaten bestimmt, die einen Rahmen um das Gesicht bilden:

```{figure} ../assets/annotation/detection.png
---
align: center
width: 100%
name: detection
alt: Ein Beispiel für das Ergebnis der Gesichtserkennung mit der Python-Bibliothek Insightface.
---
Ein Beispiel für das Ergebnis der Gesichtserkennung mit der Python-Bibliothek *Insightface*.
```

In diesem Beispiel wurde das erkannte Gesicht außerdem als das eines `36` jährigen Mannes (`M`) identifiziert. Die Punkte im Gesicht zeigen die erkannten Gesichtsmerkmale an: Augen, Nase, Mund. Die Merkmale auf der linken Gesichtshälfte sind grün, die der rechten Seite rot.
Dem auf diese Weise identifizierten Gesicht wird zusätzlich ein Konfidenzwert zugeordnet. Dieser gibt an, wie sicher sich das Modell bei der Erkennung eines Gesichts ist.

### Alignment

Im zweiten Schritt *Alignment* wird das erkannte Gesicht begradigt und zugeschnitten, um eine höhere Vergleichbarkeit in den nächsten Schritten zu erzielen.
Teilweise wird zusätzlich der Hintergrund des Gesichts entfernt.
In Python-Bibliotheken wie InsightFace und DeepFace ist dieser Schritt in andere Funktionen integriert und muss nicht im eigenen Code umgesetzt werden.

### Representation

Im dritten Schritt *Representation* werden aus dem erkannten Gesicht Vektorrepräsentationen, sogenannte Embeddings, erstellt. Hierfür ist ebenfalls ein spezialisiertes ML-Modell nötig.

Das vorherige Kapitel erläutert im Abschnitt [Zentrale Begriffe](../vision/begriffe.md#embeddings) im Detail, worum es sich bei einem Embedding handelt. In aller Kürze wird eine mathematische Repräsentation eines Gesichts erstellt, anhand derer sich Gesichter im nächsten Schritt miteinander vergleichen lassen.

**[Anmerkung]: Sollten wir hier noch ausführlicher auf Vektoren eingehen und vielleicht im nächsten Schritt den Vergleich visualisieren?**

### Recognition

Im vierten Schritt *Recognition* können mehrere Gesichter anhand ihrer Vektorrepräsentationen miteinander verglichen werden. Um die Ähnlichkeit zwischen zwei Vektoren festzustellen, lässt sich ein sogenanntes *Skalarprodukt* berechnen (englisch *dot product*).

Stellt man sich die Vektoren als Richtungsangaben oder Pfeile in einem Raum vor, so sagt das Skalarprodukt aus, wie sehr sich die Richtungen zweier Pfeile ähneln. Das Ergebnis ist ein Ähnlichkeitswert zwischen 0 und 1, entsprechend einer prozentualen Wahrscheinlichkeit, dass es sich um die Gesichter derselben Person handelt. Anhand eines Schwellwerts kann entschieden werden, ob zwei Gesichter derselben Person zugeordnet werden.

Eine wichtige Frage bei der konkreten Implementierung der Gesichtserkennung ist, welche Gesichter miteinander verglichen werden.
Eine Möglichkeit ist ein exploratives Vorgehen, bei dem alle Gesichter miteinander verglichen und anhand eines Schwellwerts in Gruppen eingeteilt werden, die dasselbe Gesicht bzw. dieselbe Figur repräsentieren.
Bei der Auswertung eines Langfilms ergibt diese Methode allerdings eine sehr große Anzahl an Figuren, da neben dem zentralen Ensemble auch Statist:innen auftauchen. Die Anzahl der Figuren lässt sich zwar durch die Einführung eines zweiten Schwellwerts reduzieren, dieser bedarf allerdings einer schrittweisen Feinjustierung. Ein weiteres Problem der Methode ist, dass die erkannten Figuren namenlos bleiben und händisch klassifiziert werden müssen.

Aus diesen Gründen verwendet unser Notebook die folgende nicht-explorative Methode, bei der die zu findenden Figuren bereits vor der Analyse festgelegt werden.

## Vergleichs-Embeddings zur Figurenerkennung

Für den späteren Schritt der *Recognition* erstellt unser Notebook noch vor der Analyse *Vergleichs-Embeddings* für jene Figuren, die tatsächlich erkannt werden sollen.

Hierzu wird nicht eine Videodatei ausgewertet, sondern mehrere ausgesuchte Frames, welche die Figuren idealerweise aus mehreren Perspektiven und in unterschiedlichen Szenen zeigen. Diese Frames (oder Screenshots) müssen händisch ausgewählt und vorbereitet werden. Der Name der Figur lässt sich automatisch aus dem Dateinamen der Bilddateien ermitteln. Dieser muss sich daher aus dem Namen und einer zweistelligen Zahl zusammensetzen, z. B. `ErikaMusterfrau01.png`. Die Bilder dürfen nur ein einziges Gesicht enthalten, da ansonsten unklar bleibt, welches Gesicht zur Figur gehört. Bei einer begrenzten Auswahl an Material, etwa aufgrund eines kurzen Trailers, ist es daher sinnvoll, das Bild auf das Gesicht der Figur zuzuschneiden oder die Gesichter anderer Figuren abzudecken:

```{figure} ../assets/annotation/Zuschnitt.png
---
align: center
width: 50%
name: Zuschnitt
alt: Ein auf das Gesicht zugeschnittener Screenshot.
---
Ein auf das Gesicht zugeschnittener Screenshot.
```

```{figure} ../assets/annotation/Abdeckung.jpg
---
align: center
width: 100%
name: Abdeckung
alt: Ein Screenshot mit abgedeckten Gesichtern, die so von der Figurenerkennung ausgeschlossen sind. 
---
Ein Screenshot mit abgedeckten Gesichtern, die so von der Figurenerkennung ausgeschlossen sind. 
```

Liegen passende Bilddateien vor, wird pro Figur ein Vergleichs-Embedding vorbereitet, anhand dessen sich später in der Analyse ein erkanntes Gesicht einer Figur zuordnen lässt. Die Schritte bis dahin folgen dem oben beschriebenen Muster, abgesehen vom letzten Schritt: *Detection*, *Alignment* und *Representation*.

## InsightFace-Implementierung

Wie im Abschnitt [Auswahl der Modelle](modelle.md#auswahl-für-die-gesichtsanalyse) erläutert, verwenden wir zur Gesichtserkennung die Python-Bibliothek <a href="https://pypi.org/project/insightface/" class="external-link" target="_blank">InsightFace</a>. Neben ihrer ausgezeichneten Genauigkeit und Geschwindigkeit zeichnet sich diese Bibliothek auch dadurch aus, dass für *Detection* und *Representation* nicht zwei getrennte ML-Modelle vorbereitet werden müssen. Diese existieren zwar weiterhin im Hintergrund, werden von der Bibliothek allerdings in einem Modellpaket zusammengefasst. Das ermöglicht eine einfachere Anwendung und eine bessere Abstimmung der beiden Modelle. Für Anwendungsfälle, die größere Anpassungen erfordern, etwa um eine höhere Auswertungsgeschwindigkeit zu erzielen, empfehlen wir die Bibliothek <a href="https://pypi.org/project/deepface/" class="external-link" target="_blank">DeepFace</a>.

## Analysematerial

Auch für dieses Jupyter Notebook stellen wir als Testmaterial den Trailer zum Film Konrad Wolfs *Der geteilte Himmtel* zur Verfügung. Der Trailer ist erneut Teil des automatischen Downloads einer ZIP-Datei. Diese enthält neben der `readme.md`-Datei und der `DEFA_Nutzungshinweis.md` diesmal auch die Datei `xx_shots.csv` mit den Ergebnissen der Einstellungserkennung zum *Der geteilte Himmel-Trailer*. 
Im Jupyter Notebook werden die Trailer automatisch als Teil eines ZIP-Archivs heruntergeladen und im Eingabeordner abgelegt.

Zur Erstellung der Vergleichs-Embeddings liefern wir die erwähnten Screenshots der Hauptfiguren mit. Für den *Der geteilte Himmel*-Trailer haben wir Bilder der Figuren Rita und Manfred ausgewählt.

Wie in den [Vorbemerkungen zu diesem Kapitels](intro.md) angemerkt, können wir aus urheberrechtlichen Gründen nicht die Langfilme Konrad Wolfs zum Download zur Verfügung stellen. Selbstständig können jedoch auch Langfilme ausgewertet werden.  

## Ausgabe

Für jede analysierte Videodatei werden bis zu vier Ergebnisdateien erstellt. Im Exportordner (`EXPORT_PATH`) wird für jeden Film ein eigener Unterordner angelegt, dessen Name dem jeweiligen Eingabeordner entspricht.

Die Datei **`Filmname_characters_frames.csv`** dokumentiert die Erkennung einzelner Figuren in den analysierten Videoframes. Sie enthält für jede erfolgreiche Erkennung den Figurennamen, den Zeitpunkt in Sekunden und im Format Stunden:Minuten:Sekunden sowie den Ähnlichkeitswert (*Dot Product*) und den Konfidenzwert der Gesichtserkennung (*Detection Score*).

Die Datei **`Filmname_characters_annotations.csv`** fasst aufeinanderfolgende Erkennungen einer Figur zu längeren Zeitintervallen zusammen. Jede Zeile enthält den Namen der Videodatei, die erkannte Figur sowie den Beginn und das Ende ihres Auftretens in Frames, Sekunden und im Format Stunden:Minuten:Sekunden.

Die Datei **`Filmname_characters_metadata.csv`** enthält die technischen Metadaten und die Analyseparameter. Hierzu zählen unter anderem die Bildrate, die Anzahl der analysierten Frames, die verwendeten Schwellenwerte und die benötigte Rechenzeit. Zusätzlich werden für jede erkannte Figur Metadaten gespeichert, beispielsweise die Anzahl erfolgreicher Erkennungen, die durchschnittlichen Erkennungswerte und die geschätzte Gesamtdauer ihres Auftretens.

Schließlich wird eine **`Filmname_annotations.eaf`** erzeugt. Anhand dieser lassen sich die Figurenerkennung und die Einstellungserkennung gemeinsam in VIAN überprüfen und weiterbearbeiten.
Für jede erkannte Figur enthält diese eine eigene Annotationsebene mit ihren Auftritten im Film. Wurde zusätzlich eine CSV-Datei mit den Ergebnissen der Einstellungserkennung bereitgestellt, werden die Einstellungen auf der Ebene  `shots` gespeichert. Außerdem werden in diesem Fall jeder Figur auf einer zusätzlichen Ebene jene Einstellungen zugeordnet, in  denen sie für mindestens einen Frame erkannt wurden(`Figurenname_matched`).

Alle Ergebnisdateien eines Films werden in einem eigenem Unterordner gespeichert. In Google Colab kann der gesamte Exportordner als ZIP-Archiv heruntergeladen werden.
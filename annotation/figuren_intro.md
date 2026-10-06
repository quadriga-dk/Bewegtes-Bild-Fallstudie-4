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

Verfahren zur Gesichtserkennung gehen grundsätzlich davon aus, dass Einzelbilder analysiert werden. Im Folgenden ist daher von Bildern die Rede, die im Fall der Filmanalyse zuvor aus einer Videodatei extrahiert werden (siehe **#xxx**).

**[Winter]: Auch hier: blieben wir bei den englischen Begriffen?**

### Detection

Im ersten Schritt *Detection* gilt es, Gesichter in einem Bild zu erkennen. Für diesen Prozess wird ein spezialisiertes ML-Modell benötigt. Die Position eines erkannten Gesichts wird anhand von vier Koordinaten bestimmt, die einen Rahmen um das Gesicht bilden:

**[Winter]: Hier fehlt noch ein Bild.**

Dem auf diese Weise identifizierten Gesicht wird zusätzlich ein Konfidenzwert zugeordnet. Dieser gibt an, wie sicher sich das Modell bei der Erkennung eines Gesichts ist.

### Alignment

Im zweiten Schritt *Alignment* wird das erkannte Gesicht begradigt und zugeschnitten, um eine höhere Vergleichbarkeit in den nächsten Schritten zu erzielen.
Teilweise wird zusätzlich der Hintergrund des Gesichts entfernt.
In Python-Bibliotheken wie InsightFace und DeepFace ist dieser Schritt in andere Funktionen integriert und muss nicht im eigenen Code umgesetzt werden.

**[Winter]Sollen wir hier auch die Normalisierung erwähnen? Das ist ein kleiner Schritt, aber wichtig und ich weiß gerade nicht recht, wohin damit. Vielleicht genügt auch der Stichpunkt unten.**

### Representation

Im dritten Schritt *Representation* werden aus dem erkannten Gesicht Vektorrepräsentationen, sogenannte Embeddings, erstellt. Hierfür ist ebenfalls ein spezialisiertes ML-Modell nötig.

Das vorherige Kapitel erläutert im Abschnitt [Zentrale Begriffe](../vision/begriffe.md#embeddings) im Detail, worum es sich bei einem Embedding handelt. In aller Kürze wird eine mathematische Repräsentation eines Gesichts erstellt, anhand derer sich Gesichter im nächsten Schritt miteinander vergleichen lassen.

**[Winter]: Sollte ich hier noch ausführlicher auf Vektoren eingehen und vielleicht im nächsten Schritt den Vergleich visualisieren?**

### Recognition

Im vierten Schritt *Recognition* können mehrere Gesichter anhand ihrer Vektorrepräsentationen miteinander verglichen werden. Um die Ähnlichkeit zwischen zwei Vektoren festzustellen, lässt sich ein sogenanntes *Skalarprodukt* berechnen (englisch *dot product*).

Stellt man sich die Vektoren als Richtungsangaben oder Pfeile in einem Raum vor, so sagt das Skalarprodukt aus, wie sehr sich die Richtungen zweier Pfeile ähneln. Das Ergebnis ist ein Ähnlichkeitswert zwischen 0 und 1, entsprechend einer prozentualen Wahrscheinlichkeit, dass es sich um die Gesichter derselben Person handelt. Anhand eines Schwellwerts kann entschieden werden, ob zwei Gesichter derselben Person zugeordnet werden.

Eine wichtige Frage bei der konkreten Implementierung der Gesichtserkennung ist, welche Gesichter miteinander verglichen werden.
Eine Möglichkeit ist ein exploratives Vorgehen, bei dem alle Gesichter miteinander verglichen und anhand eines Schwellwerts in Gruppen eingeteilt werden, die dasselbe Gesicht bzw. dieselbe Figur repräsentieren.
Bei der Auswertung eines Langfilms ergibt diese Methode allerdings eine sehr große Anzahl an Figuren, da neben dem zentralen Ensemble auch Statist:innen auftauchen. Die Anzahl der Figuren lässt sich zwar durch die Einführung eines zweiten Schwellwerts reduzieren, dieser bedarf allerdings einer schrittweisen Feinjustierung. Ein weiteres Problem der Methode ist, dass die erkannten Figuren namenlos bleiben und händisch klassifiziert werden müssen.

Aus diesen Gründen verwendet unser Notebook die folgende nicht-explorative Methode, bei der die zu findenden Figuren bereits vor der Analyse festgelegt werden.

## Vergleichs-Embeddings zur Figurenerkennung

Für den späteren Schritt der *Recognition* erstellt unser Notebook noch vor der Analyse *Vergleichs-Embeddings* für jene Figuren, die tatsächlich erkannt werden sollen.

Hierzu wird nicht eine Videodatei ausgewertet, sondern mehrere ausgesuchte Frames, welche die Figuren idealerweise aus mehreren Perspektiven und in unterschiedlichen Szenen zeigen. Diese Frames (oder Screenshots) müssen händisch ausgewählt und vorbereitet werden. Der Name der Figur lässt sich automatisch aus dem Dateinamen der Bilddateien ermitteln. Dieser muss sich daher aus dem Namen und einer zweistelligen Zahl zusammensetzen, z. B. `ErikaMusterfrau01.png`. Die Bilder dürfen nur ein einziges Gesicht enthalten, da ansonsten unklar bleibt, welches Gesicht zur Figur gehört. Bei einer begrenzten Auswahl an Material, etwa aufgrund eines kurzen Trailers, ist es daher sinnvoll, das Bild auf das Gesicht der Figur zuzuschneiden oder die Gesichter anderer Figuren abzudecken. **[Winter]Wollen wir hier noch ausführlicher werden? Oder mit Bildern als Beispielen arbeiten?**

Liegen passende Bilddateien vor, wird pro Figur ein Vergleichs-Embedding vorbereitet, anhand dessen sich später in der Analyse ein erkanntes Gesicht einer Figur zuordnen lässt. Die Schritte bis dahin folgen dem oben beschriebenen Muster, abgesehen vom letzten Schritt: *Detection*, *Alignment* und *Representation*.

## InsightFace-Implementierung

Wie im Abschnitt [Auswahl der Modelle](modelle.md#auswahl-für-die-gesichtsanalyse) erläutert, verwenden wir zur Gesichtserkennung die Python-Bibliothek <a href="https://pypi.org/project/insightface/" class="external-link" target="_blank">InsightFace</a>. Neben ihrer ausgezeichneten Genauigkeit und Geschwindigkeit zeichnet sich diese Bibliothek auch dadurch aus, dass für *Detection* und *Representation* nicht zwei getrennte ML-Modelle vorbereitet werden müssen. Diese existieren zwar weiterhin im Hintergrund, werden von der Bibliothek allerdings in einem Modellpaket zusammengefasst. Das ermöglicht eine einfachere Anwendung und eine bessere Abstimmung der beiden Modelle. Für Anwendungsfälle, die größere Anpassungen erfordern, etwa um eine höhere Auswertungsgeschwindigkeit zu erzielen, empfehlen wir die Bibliothek <a href="https://pypi.org/project/deepface/" class="external-link" target="_blank">DeepFace</a>.

## Analysematerial

Wie bereits in Kapitel xx diskutiert, können wir die Langfilme Konrad Wolfs aus urheberrechtlichen Gründen nicht im Rahmen dieser OER zur Verfügung stellen. Freundlicherweise haben wir jedoch von der DEFA-Stiftung die Genehmigung erhalten, die Trailer der Filme zu nutzen.
Für die Demonstration der Einstellungserkennung haben wir die Trailer zu den Filmen XX und YY ausgewählt. Wir haben uns für diese Trailer entschieden, da …

Im Jupyter Notebook werden die Trailer automatisch als Teil eines ZIP-Archivs heruntergeladen und im Eingabeordner abgelegt. Ein ZIP-Archiv bündelt mehrere Dateien und Ordner in einer komprimierten Datei. Ein separater Download der Trailer ist daher nicht erforderlich. Neben den Trailern enthält das Archiv auch eine `readme.md`-Datei **(Wird das so sein?)** sowie die Datei `DEFA_Nutzungshinweis.md` mit den genauen Angaben zur Nutzungslizenz der Trailer.

Auch für dieses Jupyter Notebook stellen wir als Testmaterial einen Trailer zu einem Film Konrad Wolfs zur Verfügung, in diesem Fall XX. Der Trailer ist erneut Teil des automatischen Downloads einer ZIP-Datei. Diese enthält neben der `readme.md`-Datei und der `DEFA_Nutzungshinweis.md` diesmal auch die Datei `xx_shots.csv` mit den Ergebnissen der Einstellungserkennung zum XX-Trailer. Diese Ergebnisse werden später im Notebook verwendet ([siehe xx](#xx)).

Zur Erstellung der Vergleichs-Embeddings liefern wir die erwähnten Screenshots der Hauptfiguren mit. Für den XX-Trailer haben wir Bilder der Figuren XX und YY ausgewählt.

## Ablauf des Jupyter Notebooks zur Figurenerkennung

### Festlegen von Parametern und Schwellwerten

- `VIDEO_PATH`: Ordner für die Eingabedateien. Standardmäßig heißt er `videos_face`.
- Pro Video ein eigener Unterordner direkt in `videos_face`. Darin liegen eine Videodatei, die Referenzbilder und gegebenenfalls die passende Einstellungs-CSV.
- `EXPORT_PATH`: Ordner für die Ergebnisse. Standardmäßig heißt er `export_face`. Beide Ordner werden bei Bedarf automatisch erstellt.
- `FACE_DETECTION_THRESHOLD`: Schwellwert für die Erkennung eines Gesichts. Voreingestellt ist `0.3`.
- `CHARACTER_RECOGNITION_THRESHOLD`: Schwellwert für die Zuordnung zu einer Figur. Voreingestellt ist `0.3`.
- `SKIP_FRAMES`: Anzahl der zwischen zwei Analysen übersprungenen Frames. Bei `4` wird jeder fünfte Frame analysiert.
- `TOLERANCE_FRAMES`: Zusätzliche Lücken zwischen Treffern, die beim Zusammenfügen der Annotationen toleriert werden. Voreingestellt sind `25` Frames.
- `DOWNLOAD_TESTFILES`: Download der Testdateien ein- oder ausschalten.
- `CUSTOM_ZIP_LINK` und `CUSTOM_ARCHIVE_NAME`: Direktlink und Dateiname für ein eigenes ZIP-Archiv.

### Technische Vorbereitung

#### Installation der Programmbibliotheken

- Erkennung der Colab-Umgebung und des Betriebssystems.
- Prüfung auf eine NVIDIA-GPU mit `nvidia-smi`.
- `insightface`: Modelle zur Gesichtsanalyse.
- `onnxruntime` bzw. `onnxruntime-gpu`: Ausführung der Modelle auf CPU oder GPU.
- Prüfung, ob ONNX Runtime den CUDA-Anbieter bereitstellt. Andernfalls Auswahl der CPU-Version.
- `torch`: Bei lokaler GPU-Ausführung Bereitstellung benötigter CUDA-Bibliotheken.
- `pandas` und `numpy`: Tabellen und Berechnungen mit Zahlenarrays.
- `opencv-python`: Einlesen von Videos und Referenzbildern.
- `pympi-ling`: Erstellung von EAF-Dateien.
- `tqdm`: Anzeige des Analysefortschritts.

#### Import der Programmbibliotheken

- Einbindung der Bibliotheken in die aktuelle Notebook-Sitzung.
- `os`, `sys` und `Path`: Betriebssystemabfragen und Verwaltung der Dateipfade.
- `time` und `datetime`: Messung der Rechenzeit und Darstellung von Zeitangaben.
- `urlretrieve` und `zipfile`: Download und Entpacken der Archive.
- `warnings`: Ausblenden bestimmter Hinweise zu künftigen Bibliotheksänderungen.

#### Download des Analysematerials

- `download_zip`: Funktion zum Herunterladen und Entpacken der ZIP-Archive.
- Speicherung der Archive im Arbeitsverzeichnis. Bereits vorhandene Archive werden nicht erneut heruntergeladen.
- Entpacken in `VIDEO_PATH`. Die enthaltenen Unterordner bleiben erhalten.

#### Vorbereitung des ML-Modells

- Download des Modellpakets `antelopev2` für die GPU oder `buffalo_m` für die CPU.
- Speicherung der Modelle im Ordner `.insightface/models`.
- Vorbereitung mit `FaceAnalysis` und `model.prepare`.
- Festlegung des Schwellwerts für die Gesichtsdetektion und der Eingabegröße von 640 × 640 Pixeln.

#### Definition der Hilfsfunktion

- `insightface_embed`: Gemeinsame Funktion für Gesichtsdetektion und Erstellung der Embeddings.
- Berücksichtigung von Gesichtern, deren Konfidenzwert den Schwellwert erreicht.
- Rückgabe normierter Embeddings mit 512 Werten. Zusätzlich Rückgabe der Gesichtsrahmen und Konfidenzwerte.

### Einlesen und Analyse des Videomaterials

#### Erfassung des Analysematerials

- Suche in den direkten Unterordnern von `VIDEO_PATH`. Keine Suche auf der obersten Ebene oder in tiefer verschachtelten Ordnern.
- Pro Unterordner Erfassung einer Videodatei, aller Referenzbilder und einer CSV-Datei mit `_shots` im Dateinamen.
- Weitere Videos oder Einstellungs-CSV-Dateien im selben Unterordner werden ignoriert.
- Speicherung im Dictionary `videos`. Der Unterordnername dient als Bezeichnung für das Video.

#### Erstellung und Prüfung der Vergleichs-Embeddings

- Ermittlung des Figurennamens aus dem Bilddateinamen. Die letzten beiden Zeichen vor der Dateiendung werden entfernt.
- Erkennung der Gesichter in den Referenzbildern mit einem festen Schwellwert von `0.6`.
- Verwendung eines Referenzbildes nur dann, wenn genau ein Gesicht erkannt wird.
- Mittelung der Embeddings aller geeigneten Bilder einer Figur. Anschließend erneute Normierung.
- Ausgabe der Ähnlichkeitswerte zwischen den Figuren und beim Vergleich jeder Figur mit sich selbst.

#### Anwendung des Modells

- Einlesen der Videos mit OpenCV. Erfassung von Bildrate und Frameanzahl.
- Auswahl der zu analysierenden Frames anhand von `SKIP_FRAMES`.
- Erstellung von Embeddings für die erkannten Gesichter.
- Vergleich mit allen Vergleichs-Embeddings über das Skalarprodukt.
- Zuordnung zur ähnlichsten Figur, wenn `CHARACTER_RECOGNITION_THRESHOLD` erreicht wird.
- Speicherung von Frameposition, Zeitpunkt, Ähnlichkeitswert und Konfidenzwert im Dictionary.
- Anzeige des Fortschritts und Messung der Rechenzeit.

#### Tabellarische Aufbereitung der Ergebnisse

- Erstellung eines DataFrames pro erkannter Figur. Jede Zeile entspricht einem Treffer in einem analysierten Frame.
- Erfassung der Trefferanzahl und der mittleren Ähnlichkeits- und Konfidenzwerte.
- Schätzung der Auftrittsdauer anhand der Trefferanzahl, der Bildrate und von `SKIP_FRAMES`.
- Speicherung dieser Angaben zusammen mit den Analyseparametern und der Rechenzeit als Metadaten.

#### Zusammenfügen der Frames zu Annotationen

- Sortierung der Treffer nach Frameposition.
- Zusammenfügen benachbarter Treffer derselben Figur zu Zeitintervallen.
- Berücksichtigung des regulären Frameabstands und von `TOLERANCE_FRAMES`.
- Speicherung von Figurennamen sowie Start- und Endpositionen als Frames und Zeitangaben.
- Zusammenfassung der Annotationen aller Figuren eines Videos in einer Tabelle.

### Export der Ergebnisse

#### Export der Tabellen als CSV-Dateien

- Drei Dateien pro Video. Einzelbildtreffer als `…_frames.csv`, Zeitintervalle als `…_annotations.csv` und Metadaten als `…_meta.csv`.
- Speicherung in einem Unterordner von `export_face`. Dieser trägt denselben Namen wie der Eingabe-Unterordner.
- Vorhandene Dateien gleichen Namens werden überschrieben.

#### Export der Figurenannotationen als EAF-Datei

- Eine Annotationsspur pro erkannter Figur. Umrechnung der Zeitangaben in Millisekunden.
- Falls eine Einstellungs-CSV vorhanden ist, zusätzliche Spur `shots` mit den Einstellungen.
- Zusätzliche Spuren `…_matched` mit den vollständigen Einstellungen, die sich mit Figurenauftritten überschneiden.
- Speicherung als `…_annotations.eaf` im jeweiligen Export-Unterordner.
- Ohne Figurenannotationen wird keine EAF-Datei erzeugt.

#### Download des Exportordners in Google Colab

- Verpacken des gesamten Exportordners als ZIP-Archiv und Download über den Browser.
- Bei lokaler Ausführung bleiben die Ergebnisse im Exportordner.

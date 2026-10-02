# Einstellungserkennung: Einführung
Dieser Abschnitt beschreibt im Detail die Funktionsweise des folgenden Jupyter Notebooks zur Einstellungserkennung. Die Grundlagen des Ablaufs wurden bereits im Abschnitt zur [Entwicklung des Workflows](workflow.md) vorgestellt. Die technischen Grundlagen wurden hingegen im [vorherigen Abschnitt](technik.md) erläutert. 

Zunächst werden das TransNetV2-Modells zur Einstellungserkennung und das zur Demonstration verwendete Analysematerial vorgestellt.

## Funktionsweise des TransNetV2-Modells
**TransNetV2** ist ein neuronales Netz zur automatischen Erkennung von Einstellungsübergängen. Es verarbeitet Bildfolgen und berücksichtigt dabei sowohl Bildinhalte als auch Veränderungen im zeitlichen Verlauf. Dafür verwendet es unter anderem sogenannte *3D-Faltungen*, die Bildmerkmale über mehrere Frames hinweg erfassen, und Ähnlichkeitsvergleiche zwischen Frames, zum Beispiel hinsichtlich Farbe. 

Das Modell wurde mit harten Schnitten und graduellen Übergängen sowie Überblendungen trainiert. Das Modell kann Übergänge übersehen oder Veränderungen innerhalb einer Einstellung fälschlich als Übergang werten. Weitere Informationen bieten das [Paper von Souček und Lokoč (2020)](https://arxiv.org/abs/2008.04838) und das [offizielle TransNetV2-Repositorium](https://github.com/soCzech/TransNetV2).

## Analysematerial
Wie bereits im Kapitel xx diskutiert können wir im Rahmen dieser OER aus urheberrechtlichen Gründen nicht die Langfilme Konrad Wolfs selbst zur Verfügung stellen. Freundlicherweise haben wir jedoch seitens der DEFA-Stiftung die Genehmigung erhalten, die Trailer der Filme nutzen zu können.
Für die Demonstration der Einstellungserkennung haben wir die Trailer zu den Filmen XX und YY ausgewählt. Wir haben uns für diese Trailer entschieden, da...

Im Jupyter Notebook werden die Trailer automatisch als Teil eines ZIP-Archivs heruntergeladen und im Eingabeordner abgelegt. Ein ZIP-Archiv bündelt mehrere Dateien und Ordner in einer komprimierten Datei. Ein separater Download der Trailer ist daher nicht erforderlich. Neben den Trailern enthält das Archiv auch eine `readme.md`-Datei **(Wird das so sein?)** sowie die Datei `DEFA_Nutzungshinweis.md` mit den genauen Angaben zur Nutzungslizenz der Trailer.

## Ablauf des Jupyter Notebooks zur Einstellungserkennung

### Festlegen von Parametern und Schwellwerten

- `VIDEO_PATH`: Ordner für die Videos. Standardmäßig heißt er `videos`. Videos können in Unterordnern oder direkt in diesem Ordner liegen.
- `EXPORT_PATH`: Ordner für die Ergebnisse. Standardmäßig heißt er `export`. Beide Ordner werden bei Bedarf automatisch erstellt.
- Jedes Video benötigt einen eigenen Dateinamen. Das gilt auch für Videos in verschiedenen Unterordnern.
- `THRESHOLD`: Schwellwert für die Erkennung von Einstellungsübergängen. Der Wert liegt zwischen `0` und `1`. Voreingestellt ist `0.5`.
- `DOWNLOAD_TESTFILES`: Download der Testdateien ein- oder ausschalten (`True` bzw. `False`).
- `CUSTOM_ZIP_LINK` und `CUSTOM_ARCHIVE_NAME`: Direktlink und Dateiname für ein eigenes ZIP-Archiv.
- `DIVIDER`: Trennlinie zur übersichtlichen Darstellung der Notebook-Ausgaben.

### Technische Vorbereitung

#### Installation der Programmbibliotheken

- `pip`: Installation der Bibliotheken. Für einige sind bestimmte Versionen festgelegt. `-q` zeigt weniger Meldungen an.
- `transnetv2-pytorch`: TransNetV2-Modell für die Verwendung mit PyTorch.
- `pandas`: Bearbeitung und Export von Tabellen.
- `opencv-python`: Einlesen von Videos und technischen Metadaten.
- `static-ffmpeg`: Stellt `ffmpeg` und `ffprobe` zum Lesen von Videodateien bereit.
- `pympi-ling`: Erstellung von EAF-Annotationsdateien.
- In Colab müssen die Bibliotheken nach einem Neustart der Laufzeit erneut installiert werden.

#### Import der Programmbibliotheken

- Einbindung der Bibliotheken in die aktuelle Notebook-Sitzung. Im Code stehen teilweise Kurznamen wie `pd` für `pandas` und `cv2` für OpenCV.
- `TransNetV2` und `torch`: Laden und Ausführen des neuronalen Netzes.
- NumPy: Verarbeitung von Zahlenarrays, also geordneten Sammlungen von Zahlen. Die Modellvorhersagen werden in dieses Format umgewandelt. Der Kurzname `np` wird hier nicht direkt verwendet.
- `os` und `Path`: Verwaltung von Ordnern und Dateipfaden.
- `datetime` und `time`: Darstellung von Zeitangaben und Messung der Rechenzeit.
- `urlretrieve` und `zipfile`: Download und Entpacken der Archive.
- `pympi` und `static_ffmpeg`: Einbindung der zuvor installierten EAF- und FFmpeg-Werkzeuge.

#### Download des Analysematerials

- `download_zip`: Funktion zum Herunterladen und Entpacken der ZIP-Archive.
- Download entsprechend den zuvor festgelegten Parametern.
- Speicherung der ZIP-Datei im Arbeitsverzeichnis. Bereits vorhandene Archive werden nicht erneut heruntergeladen.
- Entpacken in den Eingabeordner `VIDEO_PATH`. Unterordner aus dem Archiv bleiben erhalten.

#### Vorbereitung des ML-Modells

- Laden des vortrainierten Modells mit `TransNetV2()`.
- `model.eval()`: Wechsel in den Auswertungsmodus zur Anwendung des trainierten Modells.
- Anzeige, ob das Modell auf einer CPU oder GPU liegt.
- Bereitstellung der FFmpeg-Programme über `static_ffmpeg.add_paths()`.

### Einlesen und Analyse des Videomaterials

#### Erfassung der technischen Videometadaten

- Suche nach Videodateien im Eingabeordner und allen Unterordnern.
- Erfassung von Dateipfad, Auflösung, Anzahl der Frames und Bildrate. Berechnung der Laufzeit.
- Nicht lesbare Videos und Dateien mit ungültigen Metadaten werden übersprungen.
- Speicherung im Dictionary `videos`. Diese Python-Datenstruktur ordnet jedem Videonamen seine Metadaten und späteren Ergebnisse zu.

#### Anwendung des Modells

- Analyse aller erfassten Videos nacheinander mit `predict_video`.
- `torch.no_grad()`: Schaltet die Berechnung von "Gradienten" ab. Diese werden für das Training benötigt. Dadurch sinkt der Rechen- und Speicherbedarf.
- Verwendung von `single_frame_predictions`. Die zurückgegebenen Frames und `all_frame_predictions` werden hier nicht weiter ausgewertet.
- Umwandlung der Vorhersagen in NumPy-Arrays. Ermittlung der Einstellungen mit `predictions_to_scenes` und dem Schwellwert `THRESHOLD`.
- Messung und Speicherung der Rechenzeit pro Video.
- `scenes` ist im Code die Bezeichnung für die erkannten Einstellungen.

#### Tabellarische Aufbereitung des Ergebnisses

- Erstellung eines DataFrames, also einer Tabelle mit einer Zeile pro Einstellung.
- Berechnung von Startframe, Endframe, mittlerem Frame und Dauer. Der Endframe zählt zur Einstellung.
- Umrechnung der Framewerte in Sekunden mithilfe der Bildrate. Rundung auf zwei Nachkommastellen.
- Ausgabe der ersten fünf Tabellenzeilen als Vorschau.

#### Berechnung der Analysemetadaten

- Erfassung von Schwellwert, Einstellungsanzahl, Videolaufzeit, Rechenzeit, Auflösung und Bildrate.
- Berechnung der kürzesten, längsten, mittleren und medianen Einstellungsdauer.
- Mittelwert: Summe der Einstellungsdauern geteilt durch ihre Anzahl.
- Median: Mittlerer Wert der nach Länge sortierten Einstellungsdauern. Bei gerader Anzahl wird der Mittelwert der beiden mittleren Werte verwendet.
- Speicherung des kleinsten und größten Vorhersagewerts. Diese Werte messen nicht die Genauigkeit der Erkennung.

### Export der Ergebnisse

#### Export der Tabellen als CSV-Datei

- Zwei Dateien pro Video: Einstellungstabelle (`…_shots_0.5.csv`) und Analysemetadaten (`…_metadata_0.5.csv`).
- Einstellungstabelle ohne zusätzliche Zeilennummern. Metadaten als Paare aus Bezeichnung und Wert.
- Alle Dateien werden direkt in `EXPORT_PATH` gespeichert. Die Unterordner der Eingabe werden nicht übernommen.
- Videoname und Schwellwert stehen im Dateinamen. Vorhandene Dateien gleichen Namens werden überschrieben.

#### Export der Einstellungsannotationen als EAF-Datei

- Eine EAF-Datei pro Video mit der Annotationsspur `shots`.
- Jede Einstellung als Zeitintervall ohne Annotationstext.
- Umrechnung der Framepositionen in Millisekunden. Das Intervall endet unmittelbar nach dem letzten Frame der Einstellung.
- Speicherung direkt im Exportordner als `…_shots_0.5.eaf`. Die Datei kann beispielsweise in VIAN importiert werden.

#### Download des Exportordners in Google Colab

- Verpacken des gesamten Exportordners als ZIP-Archiv und Download über den Browser.
- Bei lokaler Ausführung wird dieser Schritt übersprungen.


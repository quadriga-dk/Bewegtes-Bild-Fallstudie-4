# Einstellungserkennung: Einführung
Dieser Abschnitt beschreibt im Detail die Funktionsweise des folgenden Jupyter Notebooks zur Einstellungserkennung. Die Grundlagen des Ablaufs wurden bereits im Abschnitt zur [Entwicklung des Workflows](workflow.md) vorgestellt. Die technischen Grundlagen wurden hingegen im [vorherigen Abschnitt](technik.md) erläutert. 

Zunächst werden das TransNetV2-Modells zur Einstellungserkennung und das zur Demonstration verwendete Analysematerial vorgestellt.

## Funktionsweise des TransNetV2-Modells
**TransNetV2** ist ein neuronales Netz zur automatischen Erkennung von Einstellungsübergängen. Es verarbeitet Bildfolgen und berücksichtigt dabei sowohl Bildinhalte als auch Veränderungen im zeitlichen Verlauf. Dafür verwendet es unter anderem sogenannte *3D-Faltungen*, die Bildmerkmale über mehrere Frames hinweg erfassen, und Ähnlichkeitsvergleiche zwischen Frames, zum Beispiel hinsichtlich Farbe. 

Das Modell wurde mit harten Schnitten und graduellen Übergängen sowie Überblendungen trainiert. Das Modell kann Übergänge übersehen oder Veränderungen innerhalb einer Einstellung fälschlich als Übergang werten. Weitere Informationen bieten der <a href="https://arxiv.org/abs/2008.04838" class="external-link" target="_blank">Artikel von Souček und Lokoč (2020)</a> und das <a href="https://github.com/soCzech/TransNetV2" class="external-link" target="_blank">offizielle TransNetV2-Repositorium</a>.

## Analysematerial
Wie bereits in den [Vorbemerkungen dieses Kapitels](intro.md) diskutiert, können wir im Rahmen dieser OER aus urheberrechtlichen Gründen nicht die Langfilme Konrad Wolfs selbst zur Verfügung stellen. Freundlicherweise haben wir jedoch seitens der DEFA-Stiftung die Genehmigung erhalten, die Trailer der Filme nutzen zu können.
Für die Demonstration der Einstellungserkennung haben wir den Trailer zum Film *Der geteilte Himmel* von 1964 ausgewählt. 

<figure style="max-width: 640px; margin: 1.5em auto; text-align: center;">
  <div style="position: relative; padding-bottom: 56.25%; height: 0;">
    <iframe style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
      src="https://www.youtube.com/embed/1LKLZNsU3_o"
      title="Der geteilte Himmel - DEFA-Trailer"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen></iframe>
  </div>
  <figcaption style="font-size: 0.9em; color: gray; margin-top: 0.5em;">
     Trailer zu Konrad Wolfs <em>Der geteilte Himmel</em>
  </figcaption>
</figure>

Im Jupyter Notebook wird der Trailer automatisch als Teil eines ZIP-Archivs heruntergeladen und im Eingabeordner abgelegt. Ein ZIP-Archiv bündelt mehrere Dateien und Ordner in einer komprimierten Datei. Ein separater Download des Trailers ist daher nicht erforderlich. Neben dem Trailer enthält das Archiv auch eine `readme.md`-Datei sowie die Datei `DEFA_Nutzungshinweis.md` mit den genauen Angaben zur Nutzungslizenz der DEFA-Trailer.

Für die Auswertung eigener Filme können die entsprechenden Dateien im Import-Ordner abgelegt werden. 

## Ausgabe

Für jede analysierte Videodatei werden drei Ergebnisdateien im festgelegten Exportordner (`EXPORT_PATH`) gespeichert. Die Dateinamen setzen sich aus dem Namen der Videodatei, `shots` und dem Schwellenwert `THRESHOLD` zusammen, beispielsweise **`Filmtitel_shots_0.5.csv`**. Beim erneuten Export werden weitere Versionen der Ergebnisdateien angelegt. Bestehende Dateien bleiben erhalten. 

Die Datei **`Filmname_shots_THRESHOLD.csv`** enthält die erkannten Einstellungen als Tabelle. Jede Zeile beschreibt eine Einstellung mit ihrem Start, Ende, Mittelpunkt und ihrer Dauer, jeweils in Frames und Sekunden.

Die Datei **`Filmname_shots_THRESHOLD_metadata.csv`** dokumentiert die technischen Metadaten der Videodatei, den verwendeten Analyseparameter und statistische Kennwerte des Ergebnisses. Wie bei der Figurenerkennung werden die Metadaten als Schlüssel-Wert-Paare gespeichert: Jede Zeile enthält den Namen eines Metadatums und seinen Wert: 

| Metadatum | Beschreibung |
|---|---|
| **Technische Metadaten** | |
| `video_name` | Dateiname der analysierten Videodatei einschließlich Dateiendung. |
| `title` | Aus dem Dateinamen ermittelter Filmtitel, ohne eine gegebenenfalls angehängte Jahreszahl. |
| `release_year` | Gegebenenfalls aus dem Dateinamen ermitteltes Erscheinungsjahr des Films. Andernfalls bleibt der Wert leer. |
| `frame_count` | Gesamtanzahl der Frames der Videodatei. |
| `frame_height` | Höhe des Videobildes in Pixeln. |
| `frame_width` | Breite des Videobildes in Pixeln. |
| `frame_rate` | Bildrate des Videos in Frames pro Sekunde (FPS). |
| `duration_hh_mm_ss` | Berechnete Gesamtlaufzeit des Videos im Format Stunden:Minuten:Sekunden, auf volle Sekunden gerundet. |
| `model` | Bezeichnung des verwendeten Modells: `transnetv2`. |
| `device` | Rechengerät des PyTorch-Modells bei der Analyse (`cpu` oder `cuda`). |
| `analysis_timestamp` | Zeitpunkt des Beginns der Videoanalyse in UTC (ISO-8601-Format). |
| `processing_time_hh_mm_ss` | Benötigte Rechenzeit für die eigentliche Videoanalyse im Format Stunden:Minuten:Sekunden. |
| **Analyseparameter** | |
| `threshold` | Verwendeter Schwellenwert für die Erkennung von Einstellungsgrenzen. Er bestimmt, ab welchem Vorhersagewert ein Übergang berücksichtigt wird. |
| **Analyseergebnisse** | |
| `shot_count` | Anzahl der erkannten Einstellungen. |
| `mean_duration_s` | Arithmetischer Mittelwert der Dauer aller erkannten Einstellungen in Sekunden. |
| `median_duration_s` | Median der Einstellungsdauern in Sekunden: die mittlere Dauer der nach Länge sortierten Einstellungen. |
| `max_duration_s` | Dauer der längsten erkannten Einstellung in Sekunden. |
| `min_duration_s` | Dauer der kürzesten erkannten Einstellung in Sekunden. |
| `min_prediction_score` | Niedrigster vom Modell berechneter Vorhersagewert für eine Einstellungsgrenze im gesamten Video. |
| `max_prediction_score` | Höchster vom Modell berechneter Vorhersagewert für eine Einstellungsgrenze im gesamten Video. |

Ein Erscheinungsjahr wird nur dann erkannt, wenn der Videodateiname vor seiner Endung mit `_Jahr` endet, beispielsweise `Der_geteilte_Himmel_1964.mp4`. Der Analysezeitpunkt wird in beiden Notebooks einheitlich in UTC angegeben.

Die Vorhersagewerte beschreiben die Einschätzung des Modells, nicht die überprüfte Genauigkeit seiner Ergebnisse. Die Werte zur Einstellungsdauer basieren auf den erkannten Einstellungsgrenzen und der Bildrate des Videos.

Zusätzlich wird eine **`Filmname_shots_THRESHOLD.eaf`** erstellt. Mit dieser Datei können die erkannten Einstellungen in Annotationsprogramme wie VIAN importiert werden, um die Ergebnisse zu überprüfen und weiterzubearbeiten.

Alle drei Dateien werden direkt im Exportordner abgelegt, unabhängig von der ursprünglichen Ordnerstruktur der Videodateien. Beim wiederholten Export werden zusätzliche Dateiversionen angelegt. Bei einer Ausführung in Google Colab kann der gesamte Exportordner zusätzlich als ZIP-Archiv heruntergeladen werden.
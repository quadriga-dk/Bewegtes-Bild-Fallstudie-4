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

Für jede analysierte Videodatei werden drei Ergebnisdateien im festgelegten Exportordner (`EXPORT_PATH`) gespeichert. Die Dateinamen setzen sich aus dem Namen der Videodatei und der Art der Ergebnisse zusammen.

Die Datei **`Filmname_shots.csv`** enthält die erkannten Einstellungen als Tabelle. Jede Zeile beschreibt eine Einstellung mit ihrem Start, Ende, Mittelpunkt und ihrer Dauer, jeweils in Frames und Sekunden.

Die Datei **`Filmname_shots_metadata.csv`** dokumentiert die technischen Metadaten und Analyseergebnisse. Dazu zählen unter anderem die Bildrate und die Anzahl erkannter Einstellungen.

Zusätzlich wird eine **`Filmname_shots.eaf`** erstellt. Mit dieser Datei können die erkannten Einstellungen in Annotationsprogramme wie VIAN importiert werden, um die Ergebnisse zu überprüfen und weiterzubearbeiten.

Alle drei Dateien werden direkt im Exportordner abgelegt, unabhängig von der ursprünglichen Ordnerstruktur der Videodateien. Bei einer Ausführung in Google Colab kann der gesamte Exportordner zusätzlich als ZIP-Archiv heruntergeladen werden.
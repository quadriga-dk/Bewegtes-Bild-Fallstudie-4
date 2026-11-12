# Figurenerkennung: Datensichtung mit VIAN

Nach erfolgreicher Ausführung des [Notebooks zur Figurenerkennung](figuren_notebook.ipynb) steht nun die Sichtung der Ergebnisse im Annotations-Tool VIAN an. Die Installation und die grundlegenden Funktionen von VIAN wurden im Kapitel zu den [Technischen Grundlagen](technik.md#vian-installation-und-verwendung) vorgestellt.

````{admonition} Download der Übungsdateien
:class: seealso
Die begleitenden Dateien zu diesem Abschnitt können Sie <a href="https://owncloud.gwdg.de/index.php/s/aCkAjEDa4HsCKTX/download" class="external-link" target="_blank">hier gebündelt herunterladen</a>. Anleitungen zum Arbeiten mit `.zip`-Archiven finden Sie hier:

<a href="https://support.microsoft.com/de-de/windows/experience/storage-filemanagement/zip-and-unzip-files" class="external-link" target="_blank">Windows</a>

<a href="https://support.apple.com/de-de/guide/mac-help/mchlp2528/mac" class="external-link" target="_blank">macOS</a>

Im Ordner Trailer des Archivs befinden sich jeweils eigene Unterordner für die Trailer zu <a href="https://www.youtube.com/watch?v=1LKLZNsU3_o" class="external-link" target="_blank"><em>Der geteilte Himmel</em></a> und <a href="https://www.youtube.com/watch?v=piyd6gxw63s" class="external-link" target="_blank"><em>Solo Sunny</em></a>. Neben den Videodateien enthalten diese jeweils einen Unterordner Figurenreferenzen mit den Bildern, anhand derer die Figuren in den Trailern identifiziert werden können.

Der Trailer zu Der geteilte Himmel wird bereits im Jupyter-Notebook zur Figurenerkennung als Teil der Testdateien heruntergeladen und analysiert. Im zugehörigen Ordner finden Sie die Ergebnisse der Figurenerkennung in zwei Varianten: einmal mit dem voreingestellten Schwellenwert 0.3 und einmal mit dem niedrigeren Wert 0.1. Die Werte wurden jeweils für beide Parameter, `FACE_DETECTION_THRESHOLD` und `CHARACTER_RECOGNITION_THRESHOLD`, verwendet.

Die Dateien zu Solo Sunny dienen hingegen als Grundlage für die anschließende Übung in diesem Abschnitt.
````

Für die Sichtung in VIAN (oder einem anderen Annotationsprogramm) wurde vom Jupyter Notebook eine `.eaf`-Datei erstellt, mit der sich sowohl die Einstellungs- als auch Figurenannotationen ins Tool importieren lassen.

````{admonition} Hinweis zum Import von .eaf-Dateien in VIAN
:class: hinweis, dropdown
Starten Sie VIAN und wählen Sie durch einen Klick auf "Video öffnen" die entsprechende Videodatei aus, für die die Annotationen in der `.eaf`-Datei importiert werden sollen.

```{figure} ../assets/annotation/VIAN_open_video.png
---
align: center
width: 100%
name: VIAN_open_video_figuren
alt: Auswahl einer Videodatei in VIAN.
---
Auswahl einer Videodatei in VIAN.
```

Für den Import in VIAN klicken Sie nun im Auswahlmenü auf der rechten Seite auf "Daten importieren" und dort auf "ELAN-Annotationen importieren". Wählen Sie die erzeugte `.eaf`-Datei am entsprechenden Export-Speicherort aus. Der Import wird dann ausgeführt.

```{figure} ../assets/annotation/VIAN_ImportMenu.png
---
align: center
width: 100%
name: VIAN_ImportMenu_figuren
alt: Das Importmenü von VIAN.
---
Das Importmenü von VIAN.
```

Nach dem Import erscheinen die Annotationen als einzelne Spuren unter der Zeitleiste am unteren Rand des Hauptfensters. Wird das Video abgespielt, bewegt sich auch der rote Positionsanzeiger in der Zeitleiste. Sie können den Anzeiger außerdem mit der Maus verschieben oder auf die Zeitleiste klicken, um zur entsprechenden Stelle im Video zu gelangen.

```{figure} ../assets/annotation/VIAN_postImport.mp4
---
align: center
width: 100%
name: _VIAN_postImport_figuren
alt: Das Hauptfenster von VIAN nach dem Import von Annotationen.
---
Das Hauptfenster von VIAN nach dem Import von Annotationen.
```
````

Für die folgenden Ergebnisse wurde als Schwellenwerte für den `FACE_DETECTION_THRESHOLD` und
`CHARACTER_RECOGNITION_THRESHOLD` der voreingestellte Wert von `0.3` verwendet. Insgesamt funktioniert die Figurenerkennung für den Trailer zu *Der geteilte Himmel* mit diesen Werten gut, jedoch wurden die Figuren nicht in allen Einstellungen korrekt erkannt.

So ist etwa die Figur Rita an einigen Stellen des Trailers nur von hinten zu sehen. Ihr Gesicht ist nicht im Bild, sodass auch das beste Verfahren zur Gesichtserkennung hier unmöglich Rita erkennen kann:

```{figure} ../assets/annotation/Himmel_Fehler1.mp4
---
align: center
width: 100%
name: Himmel_Fehler1
alt: Rita konnte im Trailer zu Der geteilte Himmel nicht von hinten erkannt werden.
---
Rita konnte im Trailer zu *Der geteilte Himmel* nicht von hinten erkannt werden.
```

Anders verhält es sich bei Einstellungen, in denen die Figuren zwar gut zu sehen sind, aber dennoch nicht erkannt wurden. Dies ist in einer Einstellung des Trailers der Fall, in der Rita und Manfred gemeinsam im Bett liegen. Aufgrund der Einstellungsgröße und der Beleuchtung sind die Gesichter nicht vollständig zu sehen. Es ist nur eine Gesichtshälfte Manfreds sichtbar und Ritas Augen werden teilweise von ihren Haaren verdeckt. Wesentliche Merkmale für die Gesichtserkennung stehen also nur teilweise zur Verfügung (vgl. Kapitel zu [Grundlagen der Gesichtserkennung](../annotation/figuren_intro.md#grundlagen-der-gesichtserkennung)). Während Manfred in dieser Einstellung bei den Standard-Schwellenwerten von jeweils `0.3` gar nicht erkannt wird, wurde Rita für ein paar Frames erfasst. Daher wurde ihr trotz der schlechten Erkennung in der Spur *Rita_matched* die gesamte Einstellung zugeordnet (vgl. im Kapitel [Ausgabe](../annotation/figuren_intro.md#ausgabe) die Erklärung zu `Figurenname_matched`): 

```{figure} ../assets/annotation/Himmel_Fehler2.mp4
---
align: center
width: 100%
name: Himmel_Fehler2
alt: Rita und Manfred konnten im Trailer zu Der geteilte Himmel in dieser Einstellung nicht vollständig erkannt werden.
---
Rita und Manfred konnten im Trailer zu *Der geteilte Himmel* in dieser Einstellung nicht vollständig erkannt werden.
```

Die Wahl geringerer Schwellenwerte wie `0.1` verbessert zwar die Erkennung von Manfred in dieser Einstellung, führt allerdings gleichzeitig auch zu falschen Ergebnissen. So werden bei einem derart niedrigen Schwellenwert auch andere Figuren fälschlicherweise als Rita oder Manfred erkannt:

```{figure} ../assets/annotation/Himmel_Fehler3.png
---
align: center
width: 100%
name: Himmel_Fehler3
alt: Rolf Meternagel wurde fälschlicherweise als Rita identifiziert.
---
Rolf Meternagel wurde fälschlicherweise als Rita identifiziert.
```

Die Setzung geeigneter Schwellenwerte spielt also auch hier eine wichtige Rolle für die Qualität der Annotationsergebnisse. Für eine Verbesserung der Ergebnisse der Figurenerkennung kann es wie schon bei der Einstellungserkennung sinnvoll sein, mit verschiedenen Schwellenwerten zu experimentieren.

Auch wenn die automatisiert erstellten Annotationen zum Auftreten von Figuren in Filmen nie vollkommen fehlerfrei sein werden, sind sie doch exakt genug, um mit ihnen weiterzuarbeiten. Wie sich hier gezeigt hat, müssen die Ergebnisse jedoch immer überprüft werden. Zudem ist zu reflektieren, in welchen Kontexten Erkennungsfehler auftreten können.

``````{admonition} Übung
:class: exercise
Führen Sie selbstständig die Analyse für den *Solo Sunny* Trailer aus, der bereits in der allgemeinen `.zip`-Datei für dieses Kapitel im Ordner `Trailer` beiliegt. Der Ordner für *Solo Sunny* enthält zudem die Referenzabbildungen für die Figuren Ralph und Sunny. 

Alternativ können Sie auch eine andere Videodatei Ihrer Wahl verwenden. Bereiten Sie die notwendigen Screenshots der Figuren [zur Erstellung der Vergleichsembeddings](figuren_intro.md#vergleichs-embeddings-zur-figurenerkennung) in diesem Fall selbst vor. Benennen Sie die Bilddateien dabei nach dem Schema `Erika01.png`. Ein einzelnes Bild pro Figur genügt, eine höhere Anzahl von Abbildungen aus verschiedenen Perspektiven verbessert jedoch die Genauigkeit der Erkennung.

Wählen Sie selbst die Schwellenwerte, beispielsweise von sehr geringer Höhe wie `0.1`, und beurteilen Sie die Auswirkungen auf die Annotationsergebnisse.

`````{admonition}  Lösung
:class: solution, dropdown

Öffnen Sie das [Jupyter Notebook zur Figurenerkennung](../annotation/figuren_notebook.ipynb) in Colab (vgl. Unterkapitel [Ausführung des Notebooks](../annotation/figuren_notebook.ipynb#ausfuhrung-des-notebooks)).

Verändern Sie nun im ersten Codeblock des Notebooks die voreingestellten Parameter.

```{figure} ../assets/annotation/figuren_nb_paramter_1.png
---
align: center
width: 100%
name: Figuren Parameter Colab 1
alt: Einstellung der Parameter im Notebook in Colab.
---
Einstellung der Parameter im Notebook in Colab.
```

Mit `FACE_DETECTION_THRESHOLD = 0.3` wird der Schwellenwert für die Gesichtserkennung eingestellt, mit `CHARACTER_RECOGNITION_THRESHOLD = 0.3` der Schwellenwert für die Figurenerkennung, hier jeweils mit 0.3. Verändern Sie diese Einstellung, zulässig sind Werte zwischen 0.0 und 1.0. (1) Hier können Sie also mit verschiedenen Schwellenwert-Einstellungen experimentieren.

Da Sie dieses Mal mit einer eigenen Videodatei arbeiten wollen, müssen Sie zusätzlich `DOWNLOAD_TESTFILES = False` setzen, damit die für Demonstrationszwecke vorbereitete Videodatei zu *Der geteilte Himmel* nicht heruntergeladen wird. (2) Standardmäßig ist dieser Parameter im Notebook auf `True` eingestellt.

Führen Sie nun den Codeblock durch einen Klick auf das Dreieckssymbol oben links im Block aus. (3) 

```{figure} ../assets/annotation/warnung_google.png
---
align: center
width: 100%
name: warnung google figuren
alt: Warnmeldung vor der Ausführung des Notebooks.
---
Warnmeldung vor der Ausführung des Notebooks.
```

Evtl. wird eine Warnung angezeigt, dass das Notebook nicht von Google erstellt wurde, klicken Sie auf "Trotzdem ausführen" rechts unten. Dadurch werden die Ordner "videos_characters" und "export_characters" in der Colab-Umgebung erstellt.

Laden Sie nun die Videodatei, hier die Trailerdatei, und die Referenzabbildungen der zu erkennenden Figuren in die Colab-Umgebung hoch.

```{figure} ../assets/annotation/figuren_nb_paramter_2.png
---
align: center
width: 100%
name: Figuren Parameter Colab 2
alt: Ordner für die Videodateien in Colab.
---
Ordner für die Videodateien in Colab.
```

Klicken Sie auf das Ordnersymbol in der linken Randspalte von Colab. (1) Es öffnet sich eine Liste mit den verfügbaren Ordnern. In den Ordner "videos_characters" laden Sie die zu annotierende Trailerdatei und die Abbildungen der zu erkennenden Figuren aus dem Trailer hoch. (2) Wenn Sie mit der Maus auf den Ordnernamen deuten, werden rechts drei Punkte sichtbar, ein Klick auf die Punkte öffnet ein Fenster zum Hochladen der Datei.

Führen Sie nun die weiteren Codeblöcke des Notebooks nacheinander aus.

```{figure} ../assets/annotation/figuren_nb_paramter_3.png
---
align: center
width: 100%
name: Figuren Parameter Colab 3
alt: Ausführen der Codeblöcke in Colab.
---
Ausführen der Codeblöcke in Colab.
```

Klicken Sie hierzu wiederum bei jedem Codeblock auf das Dreiecksymbol in der linken oberen Ecke des Blocks. (1) Bedenken Sie, dass je nach Rechenkapazität, die Google Colab zur Verfügung stellt, das Ausführen eines Codeblocks einige Zeit in Anspruch nehmen kann, insbesondere im Codeblock zur "Anwendung des Modells". Indem Sie alle Codeblöcke einzeln nacheinander ausführen, können Sie deren spezifische Funktionen nochmals nachvollziehen und werden sofort auf eventuell auftretende Probleme aufmerksam.

Durch einen Klick auf "Alle ausführen" in der Colab-Kopfzeile können auch alle Codeblöcke automatisch nacheinander ausgeführt werden. (2) Dies vereinfacht den Ablauf, wenn Sie etwa lediglich den Schwellenwert ändern wollen und alle Codeblöcke in einem ersten Durchlauf bereits erfolgreich ausgeführt wurden.

```{figure} ../assets/annotation/figuren_nb_export.png
---
align: center
width: 100%
name: Figuren Notebook Export
alt: Export der Annotationsdateien.
---
Export der Annotationsdateien.
```

Am Ende des Notebooks werden die entstandenen Annotationsdateien im Ordner "export_characters" der Colab-Umgebung abgelegt. (1) Zusätzlich öffnet sich ein Dialogfenster, mit dem Sie die Annotationsdateien als ZIP-Datei mit dem Namen `export.zip` auf Ihrem Computer speichern können. (2)

Beim mehrmaligen Ausführen des Jupyter Notebooks, etwa mit neuen Schwellenwerten, werden die erzeugten Annotationsergebnisse im Ordner "export_characters" durch Versionsnummern wie `_v2`, `_v3` usw. ergänzt.

Entpacken Sie ggf. die Exportdateien in einen Ordner Ihrer Wahl. Importieren Sie nun die Annotationsergebnisse mit der `.eaf-Datei` in VIAN (vgl. "Hinweis zum Import von .eaf-Dateien in VIAN" in diesem Kapitel).

Sie können nun die Annotationsergebnisse in VIAN sichten und überprüfen. Wiederholen Sie die Annotation mit anderen Schwellenwerten und vergleichen Sie die Erkennungsqualität. Welche Schwellenwerte führen zu den besten Ergebnissen?

Wir haben im Trailer zu <a href="https://www.youtube.com/watch?v=piyd6gxw63s" class="external-link" target="_blank">*Solo Sunny*</a> nach den beiden Hauptfiguren Sunny und Ralph suchen lassen. Für die Figurenerkennung haben wir die Referenzabbildungen verwendet, die im `.zip`-Archiv zu diesem Abschnitt unter `Trailer` → `Solo Sunny_Trailer_1980` → `Figurenreferenzen` zu finden sind.

Mit den voreingestellten Schwellenwerten von `0.3` haben wir erneut ein gutes Ergebnis erzielen können. Die Probleme ähneln denen aus dem *Der geteilte Himmel* Trailer. So wurde etwa auch Sunny in dieser Sequenz nicht erkannt, da ihr Gesicht nicht vollständig zu sehen ist:

```{figure} ../assets/annotation/SoloSunny_Figuren_Fehler1.mp4
---
align: center
width: 100%
name: SoloSunny_Figuren_Fehler1
alt: Sunny wurde in den gezeigten Einstellungen nicht erkannt. 
---
Sunny wurde in den gezeigten Einstellungen nicht erkannt. 
```
Durch die Wahl geringerer Schwellenwerte von `FACE_DETECTION_THRESHOLD = 0.1` und `CHARACTER_RECOGNITION_THRESHOLD = 0.15` konnte die Erkennung in diesen Einstellungen leicht verbessert werden. Zwar wird Sunny weiterhin nicht durchgehend erkannt, jedoch reichen Treffer in einzelnen Frames aus, damit ihr in der `Sunny_matched` Spur die gesamte Einstellung zugeordnet wird. Allerdings führten dieselben Schwellenwerte auch zu Falscherkennungen, bei denen etwa die "Frau im Bett" als Sunny erkannt wurde.

```{figure} ../assets/annotation/SoloSunny_Figuren_Änderung1.mp4
---
align: center
width: 100%
name: SoloSunny_Figuren_Änderung1
alt: Sunny wurde in den gezeigten Einstellungen mit den Schwellenwerten FACE_DETECTION_THRESHOLD = 0.1 und CHARACTER_RECOGNITION_THRESHOLD = 0.15 teilweise erkannt. 
---
Sunny wurde in den gezeigten Einstellungen mit den Schwellenwerten `FACE_DETECTION_THRESHOLD = 0.1` und `CHARACTER_RECOGNITION_THRESHOLD = 0.15` teilweise erkannt. 
```

Was passiert, wenn wir stattdessen sehr hohe Schwellenwerte einsetzen, etwa `0.8`?
In diesem Fall verringert sich die Anzahl an Treffern deutlich:

```{figure} ../assets/annotation/SoloSunny_Figuren_Änderung2.png
---
align: center
width: 100%
name: SoloSunny_Figuren_Änderung2
alt: Mit den Schwellenwerten FACE_DETECTION_THRESHOLD = 0.8 und CHARACTER_RECOGNITION_THRESHOLD = 0.8 werden die Figuren nur noch sehr selten erkannt.
---
Mit den Schwellenwerten `FACE_DETECTION_THRESHOLD = 0.8` und `CHARACTER_RECOGNITION_THRESHOLD = 0.8` werden die Figuren nur noch sehr selten erkannt.
```
Sehr hohe Schwellenwerte können also dazu führen, dass die Figuren in vielen Einstellungen nicht mehr erkannt werden, obwohl sie dort präsent und ihre Gesichter zu sehen sind.

Mit welchen Schwellenwerten haben Sie die besten Ergebnisse erzielt?

``````
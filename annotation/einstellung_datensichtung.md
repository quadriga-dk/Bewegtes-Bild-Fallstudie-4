# Einstellungserkennung: Datensichtung mit VIAN

Nachdem die Einstellungs-Annotationen für den Trailer zu *Der geteilte Himmel* automatisch durch das [Jupyter Notebook](../annotation/einstellungen_notebook.ipynb) erstellt wurden, ist es an der Zeit, diese mithilfe des Annotations-Tools VIAN zu sichten. Die Installation und die für unsere Sichtung notwendigen grundlegenden Funktionen von VIAN wurden bereits im Kapitel zu den [technischen Grundlagen](../annotation/technik.md#vian-installation-und-verwendung) vorgestellt.

````{admonition} Download der Übungsdateien
:class: seealso

Die begleitenden Dateien zu diesem Abschnitt können Sie <a href="https://owncloud.gwdg.de/remote.php/webdav/quadriga/Fallstudie_2/Zip_Files/Zip%20files_final/shots_results.zip" class="external-link" target="_blank">hier gebündelt herunterladen</a>. Anleitungen zum Arbeiten mit `.zip`-Archiven finden Sie hier:

<a href="https://support.microsoft.com/de-de/windows/experience/storage-filemanagement/zip-and-unzip-files" class="external-link" target="_blank">Windows</a>

<a href="https://support.apple.com/de-de/guide/mac-help/mchlp2528/mac" class="external-link" target="_blank">macOS</a>

Im Ordner `Trailer` des Archivs befinden sich die Videodateien und die Ergebnisse der automatischen Einstellungserkennung für die Trailer zu <a href="https://www.youtube.com/watch?v=1LKLZNsU3_o" class="external-link" target="_blank"><em>Der geteilte Himmel</em></a>, <a href="https://www.youtube.com/watch?v=wdY5MxWyGrU&t=13s" class="external-link" target="_blank"><em>Mama, ich lebe</em></a> und <a href="https://www.youtube.com/watch?v=piyd6gxw63s" class="external-link" target="_blank"><em>Solo Sunny</em></a>. Für alle drei Trailer wurde der voreingestellte Schwellenwert von `0.5` verwendet.

Der Trailer zu *Der geteilte Himmel* wird bereits im [Jupyter-Notebook zur Einstellungserkennung](../annotation/einstellungen_notebook.ipynb) als Teil der Testdateien heruntergeladen und analysiert. Um mögliche Problemstellen und Fehler bei der automatischen Erkennung von Einstellungsübergängen zu verdeutlichen, haben wir mit demselben Notebook zusätzlich die Trailer zu *Mama, ich lebe* und *Solo Sunny* ausgewertet.
````

Für die Sichtung in VIAN (oder einem anderen Annotationsprogramm) wurde vom Jupyter Notebook jeweils eine `.eaf`-Datei erstellt, mittels derer sich die Einstellungs-Annotationen in die entsprechenden Tools importieren lassen.

````{admonition} Hinweis zum Import von .eaf-Dateien in VIAN
:class: hinweis, dropdown
Starten Sie VIAN und wählen Sie durch einen Klick auf "Video öffnen" die entsprechende Videodatei aus, für die die Annotationen in der `.eaf` Datei importiert werden sollen.

```{figure} ../assets/annotation/VIAN_open_video.png
---
align: center
width: 100%
name: VIAN_open_video_einstellungen
alt: Auswahl einer Videodatei in VIAN.
---
Auswahl einer Videodatei in VIAN.
```

Für den Import in VIAN klicken Sie nun im Auswahlmenü auf der rechten Seite auf "Daten importieren" und dort auf "ELAN-Annotationen importieren". Wählen Sie die erzeugte `.eaf`-Datei am entsprechenden Export-Speicherort aus. Der Import wird dann ausgeführt.

```{figure} ../assets/annotation/VIAN_ImportMenu.png
---
align: center
width: 100%
name: VIAN_ImportMenu_einstellungen
alt: Das Importmenü von VIAN.
---
Das Importmenü von VIAN.
```

Nach dem Import erscheinen die Annotationen als einzelne Spuren unter der Zeitleiste am unteren Rand des Hauptfensters. Wird das Video abgespielt, bewegt sich auch der rote Positionsanzeiger in der Zeitleiste. Sie können den Anzeiger außerdem mit der Maus verschieben oder auf die Zeitleiste klicken, um zur entsprechenden Stelle im Video zu gelangen.

```{figure} ../assets/annotation/VIAN_postImport.gif
---
align: center
width: 100%
name: _VIAN_postImport_einstellungen
alt: Das Hauptfenster von VIAN nach dem Import von Annotationen.
---
Das Hauptfenster von VIAN nach dem Import von Annotationen.
```
````

Nach dem Import können Sie nun das Ergebnis der Einstellungserkennung für *Der geteilte Himmel* in VIAN sichten. Mit dem Abspielen des Trailers bzw. anhand der Navigation in der Timeline werden Sie feststellen, dass die Einstellungserkennung in diesem Fall tadellos funktioniert hat. Die einzelnen nummerierten 'Annotationsblöcke' sind perfekt mit den Einstellungswechseln synchronisiert. Insgesamt wurden 23 Einstellungen erkannt.

```{figure} ../assets/annotation/Himmel_results.png
---
align: center
width: 100%
name: VIAN_Himmel
alt: Die Einstellungsannotationen nach dem Import in VIAN.
---
Die Einstellungsannotationen nach dem Import in VIAN.
```

Allerdings funktioniert die Erkennung mit dem Standard-Schwellenwert von `0.5` nicht für alle Trailer der Filme Konrad Wolfs fehlerlos.

Im Trailer zu *Mama, ich lebe* werden zu Beginn Standbilder aus anderen Produktionen Konrad Wolfs gezeigt. Hier wurde bei einem Schwellenwert von `0.5` der Übergang zwischen zwei ähnlichen Bildern innerhalb der Einstellung 12 nicht erkannt:

```{figure} ../assets/annotation/MamaIchLebe_Fehler1.gif
---
align: center
width: 100%
name: MamaIchLebe_Fehler1
alt: Der erste Fehler in Mama, ich lebe.
---
Der erste Fehler in *Mama, ich lebe*.
```

Ein weiterer Fehler im selben Trailer findet sich beim Übergang von einer Totalen in eine Nahaufnahme in der Bewegung in Einstellung 36:

```{figure} ../assets/annotation/MamaIchLebe_Fehler2.gif
---
align: center
width: 100%
name: MamaIchLebe_Fehler2
alt: Der zweite Fehler in Mama, ich lebe.
---
Der zweite Fehler in *Mama, ich lebe*.
```
Auch in die Einstellungserkennung zum *Solo Sunny* Trailer hat sich ein Fehler eingeschlichen. Der kurze Wechsel zu einer Einstellung am Ende von Einstellung 5 wurde nicht erkannt:

```{figure} ../assets/annotation/SoloSunny_Fehler.gif
---
align: center
width: 100%
name: SoloSunny_Fehler
alt: Der Fehler in Solo Sunny.
---
Der Fehler in *Solo Sunny*.
```

Es zeigt sich also, dass die Ergebnisse automatisiert erstellter Annotationen immer überprüft und ggf. ergänzt und korrigiert werden müssen. In den oben dargestellten Trailer-Beispielen ergeben sich z.B. insbesondere Probleme bei der Einstellungserkennung, wenn die aufeinander folgenden Frames unterschiedlicher Einstellungen für die Prozesse der Computer Vision eine zu große Ähnlichkeit aufweisen oder wenn Übergänge durch starke Bewegungen im Bild nicht erfasst werden.

Durch das Experimentieren mit unterschiedlichen Schwellenwerten lassen sich ggf. bessere Erkennungsergebnisse erzielen. Die mit dem Notebook bzw. Computer Vision erstellten Annotationsergebnisse werden dabei nie vollkommen fehlerfrei sein. Dennoch lassen sich Ergebnisse erzielen, die exakt genug sind, um mit ihnen weiterzuarbeiten. 

``````{admonition} Übung
:class: exercise
Versuchen Sie, die aufgeführten Fehler in einem der Trailer durch dessen erneute Auswertung mit einem anderen Schwellenwert zu beseitigen. Die Trailer zu *Mama, ich lebe* und *Solo Sunny* liegen dem eingangs erwähnten`.zip`-Archiv zu diesem Abschnitt im Ordner `Trailer` bei.


`````{admonition}  Lösung
:class: solution, dropdown

Öffnen Sie das [Jupyter Notebook zur Einstellungserkennung](../annotation/einstellungen_notebook.ipynb) in Colab (vgl. Unterkapitel [Ausführung des Notebooks](../annotation/einstellungen_notebook.ipynb#ausfuhrung-des-notebooks)).

Verändern Sie nun im ersten Codeblock des Notebooks die voreingestellten Parameter.

```{figure} ../assets/annotation/einstellungen_nb_paramter_1.png
---
align: center
width: 100%
name: Parameter Colab 1
alt: Einstellung der Parameter im Notebook in Colab.
---
Einstellung der Parameter im Notebook in Colab.
```

Mit `THRESHOLD = 0.5` wird der Schwellenwert eingestellt, hier ist er mit 0.5 festgelegt. Verändern Sie diese Einstellung, zulässig sind Werte zwischen 0.0 und 1.0. (1) Hier können Sie also mit verschiedenen Schwellenwert-Einstellungen experimentieren.

Da Sie dieses Mal mit einer eigenen Videodatei arbeiten wollen, müssen Sie zusätzlich `DOWNLOAD_TESTFILES = False` setzen, damit die für Demonstrationszwecke vorbereitete Videodatei nicht heruntergeladen wird. (2) Standardmäßig ist dieser Parameter im Notebook auf `True` eingestellt.

Führen Sie nun den Codeblock durch einen Klick auf das Dreieckssymbol oben links im Block aus. (3)

```{figure} ../assets/annotation/warnung_google.png
---
align: center
width: 100%
name: warnung google einstellungen
alt: Warnmeldung vor der Ausführung des Notebooks.
---
Warnmeldung vor der Ausführung des Notebooks.
```

Evtl. wird eine Warnung angezeigt, dass das Notebook nicht von Google erstellt wurde, klicken Sie auf "Trotzdem ausführen" rechts unten. Dadurch werden die Ordner "videos_shots" und "export_shots" in der Colab-Umgebung erstellt.

Nun wird die Videodatei, hier die Trailerdatei, in die Colab-Umgebung hochgeladen.

```{figure} ../assets/annotation/einstellungen_nb_paramter_2.png
---
align: center
width: 100%
name: Parameter Colab 2
alt: Ordner für die Videodateien in Colab.
---
Ordner für die Videodateien in Colab.
```

Klicken Sie auf das Ordnersymbol in der linken Randspalte von Colab. (1) Es öffnet sich eine Liste mit den verfügbaren Ordnern. In den Ordner "videos_shots" laden Sie die zu annotierende Trailerdatei hoch. (2) Wenn Sie mit der Maus auf den Ordnernamen deuten, werden rechts drei Punkte sichtbar, ein Klick auf die Punkte öffnet ein Fenster zum Hochladen der Datei.

Führen Sie nun die weiteren Codeblöcke des Notebooks nacheinander aus.

```{figure} ../assets/annotation/einstellungen_nb_paramter_3.png
---
align: center
width: 100%
name: Parameter Colab 3
alt: Ausführen der Codeblöcke in Colab.
---
Ausführen der Codeblöcke in Colab.
```

Klicken Sie hierzu wiederum bei jedem Codeblock auf das Dreiecksymbol in der linken oberen Ecke des Blocks. (1) Bedenken Sie, dass je nach Rechenkapazität, die Google Colab zur Verfügung stellt, das Ausführen eines Codeblocks einige Zeit in Anspruch nehmen kann, insbesondere im Codeblock zur "Anwendung des Modells". Indem Sie alle Codeblöcke einzeln nacheinander ausführen, können Sie deren spezifische Funktionen nochmals nachvollziehen und werden sofort auf eventuell auftretende Probleme aufmerksam.

Durch einen Klick auf "Alle ausführen" in der Colab-Kopfzeile können auch alle Codeblöcke automatisch nacheinander ausgeführt werden. (2) Dies vereinfacht den Ablauf, wenn Sie etwa lediglich den Schwellenwert ändern wollen und alle Codeblöcke in einem ersten Durchlauf bereits erfolgreich ausgeführt wurden.

```{figure} ../assets/annotation/einstellungen_nb_export.png
---
align: center
width: 100%
name: Notebook Export
alt: Export der Annotationsdateien.
---
Export der Annotationsdateien.
```

Am Ende des Notebooks werden die entstandenen Annotationsdateien im Ordner "export_shots" der Colab-Umgebung abgelegt. (1) Zusätzlich öffnet sich ein Dialogfenster, mit dem Sie die Annotationsdateien als Zip-Datei mit dem Namen `export.zip` auf Ihrem Computer speichern können. (2)

Beim mehrmaligen Ausführen des Jupyter Notebooks, etwa mit neuen Schwellenwerten, werden die erzeugten Ausgabedateien im Ordner "export_shots" durch Versionsnummern ergänzt, wie etwa `v2`, `v3` usw.

Entpacken Sie ggf. die Exportdateien in einen Ordner Ihrer Wahl. Importieren Sie nun die Annotationsergebnisse mit der `.eaf-Datei` in VIAN (vgl. "Hinweis zum Import von .eaf-Dateien in VIAN" in diesem Kapitel).

Sie können nun die Annotationsergebnisse in VIAN sichten und überprüfen. Wiederholen Sie die Annotation mit anderen Schwellenwerten und Trailern und vergleichen Sie die Erkennungsqualität. Welche Schwellenwerte führen zu den besten Ergebnissen?


Ein Schwellenwert von 0.25 bereinigt z.B. die Fehler im *Mama, ich lebe* Trailer. Im Fall des Trailers zu *Solo Sunny* führt derselbe Schwellenwert allerdings zu einer falsch erkannten Einstellung. So wurde etwa Einstellung 53 fälschlicherweise aufgeteilt, da plötzlich ein grelles Licht im Bild sichtbar wird:

```{figure} ../assets/annotation/SoloSunny_Fehler2.gif
---
align: center
width: 100%
name: SoloSunny_Fehler2
alt: Der neu entstandene Fehler in Solo Sunny.
---
Der neu entstandene Fehler in *Solo Sunny*.
```
Ein Schwellenwert, der für einen Film gute Ergebnisse liefert, passt nicht zwangsläufig auch für andere Filme. Es kann daher je nach Forschungsvorhaben sinnvoll sein, für jeden Film einen passenden Schwellenwert zu finden. 
``````


# Figurenerkennung: Datensichtung mit VIAN

Nach erfolgreicher Ausführung des [Notebooks zur Figurenerkennung](figuren_notebook.ipynb) ist es erneut Zeit für die Sichtung der Ergebnisse in VIAN. 

VIAN wurde im Kapitel zu den [Technischen Grundlagen](technik.md#vian-installation-und-verwendung) vorgestellt.

Mittels der im Notebook erstellten `.eaf`-Datei können in einem Schritt sowohl die Einstellungs- als auch Figurenannotationen ins VIAN-Projekt importiert werden. 

````{admonition} Hinweis zum Import von .eaf-Dateien in VIAN
:class: hinweis, dropdown
Für den Import in VIAN Klicken Sie im Auswahlmenü auf der rechten Seite auf "ELAN-Annotationsergebnisse importieren" und wählen sie die erzeugte `.eaf`-Datei am entsprechenden Export-Speicherort aus. Der Import wird dann ausgeführt.

```{figure} ../assets/annotation/VIAN_ImportMenu.png
---
align: center
width: 100%
name: VIAN_ImportMenu_figuren
alt: Das Importmenü von VIAN.
---
Das Importmenü von VIAN.
```

Nach dem Import erscheinen die Annotationen als einzelne Spuren unter der Zeitleiste am unteren Rand des Hauptfensters. Wird das Video abgespielt, bewegt sich auch der rote Positionsanzeiger in der Zeitleiste. Sie können den Anzeiger außerdem mit der Maus verschieben oder auf die Zeitleiste Klicken, um zur entsprechenden Stelle im Video zu gelangen.

```{figure} ../assets/annotation/VIAN_postImport.png
---
align: center
width: 100%
name: _VIAN_postImport_figuren
alt: Das Hauptfenster von VIAN nach dem Import von Annotationen.
---
Das Hauptfenster von VIAN nach dem Import von Annotationen.
```
````

Für die folgenden Ergebnisse wurden als Schwellenwerte für den `FACE_DETECTION_THRESHOLD` und
`CHARACTER_RECOGNITION_THRESHOLD`der voreingestellt Wert von `0.3` verwendet. In der Zusammenfassung funktioniert die Figurenerkennung für den Trailer zu *Der geteilte Himmel* mit diesen Werten gut, jedoch wurden die Figuren nicht in allen Einstellungen korrekt erkannt.
So ist etwa die Figur Rita teilweise nur von hinten so sehen. Ihr Gesicht ist nicht zu erkennen, sodass auch das beste Verfahren zur Gesichtserkennung hier unmöglich Rita erkennen kann:

```{figure} ../assets/annotation/Himmel_Fehler1.gif
---
align: center
width: 100%
name: Himmel_Fehler1
alt: Rita konnte im Trailer zu Der geteilte Himmel nicht von hinten erkannt werden.
---
Rita konnte im Trailer zu *Der geteilte Himmel* nicht von hinten erkannt werden.
```

Anders ist die Lage für Einstellungen, in denen die Figuren zwar gut zu sehen sind, aber nicht erkannt wurden. Dies ist in einer der frühen Einstellungen der Fall, in der Rita und Manfred gemeinsam im Bett liegen. Aufgrund der Einstellungsgröße und der Beleuchtung sind die Gesichter nicht vollständig zu sehen. Außerdem liegt Manfred auf der Seite und Ritas Augen werden teilweise von ihren Haaren verdeckt. Während Manfred in dieser Einstellung bei den Standard-Schwellenwerten von jeweils `0.3` gar nicht erkannt wird, wurde Rita für eine paar Frames erfasst. Daher wurde ihr trotz der schlechten Erkennung in der Spur *Rita_matched* die gesamte Einstellung zugeordnet: 

```{figure} ../assets/annotation/Himmel_Fehler2.gif
---
align: center
width: 100%
name: Himmel_Fehler2
alt: Rita und Manfred konnte im Trailer zu Der geteilte Himmel in dieser Einstellung nicht vollständig erkannt werden.
---
Rita und Manfred konnte im Trailer zu Der geteilte Himmel in dieser Einstellung nicht vollständig erkannt werden.
```

Zwar verbessert die Wahl geringerer Schwellenwerte wie `0.1` zwar die Erkennung von Manfred in dieser Einstellung, führt allerdings auch die falschen Erkennungen. So werden bei einem derart niedrigen Schwellenwert auch andere Figuren inkorrekterweise als Rita oder Manfred identifiziert.

``````{admonition} Übung
:class: exercise
Führen Sie die Analyse für einen weiteren Trailer Ihrer Wahl durch. Sie können die Trailer hier herunterladen. **[Link folgt]** Bereiten Sie die notwendigen Screenshots [zur Erstellung der Vergleichsembeddings](figuren_intro.md#vergleichs-embeddings-zur-figurenerkennung) vor. Benennen Sie die Bilddateien dabei nach dem Schema `Erika_Musterfrau01`. Ein einzelnes Bild pro Figur genügt, eine höhere Anzahl verbessert jedoch die Genauigkeit der Erkennung. Die Namen der Figuren können Sie im [Filmportal](https://www.filmportal.de) recherchieren oder zu Übungszwecken eigene Namen wählen. Wählen Sie selbst die Schwellenwerte, beispielsweise von sehr geringer Höhe wie `0.1`.

`````{admonition}  Lösung
:class: solution, dropdown
Wir haben im Trailer zu *Solo Sunny* nach den beiden Hauptfiguren Sunny und Ralph suchen lassen. Mit den voreingestellten Schwellenwerten von `0.3` habe wir ein erneut gutes Ergebnis erzielen können. Die Probleme ähneln denen aus dem *Der geteilte Himmel* Trailer. So wurde etwa auch Sunny in diesen Einstellungen nicht erkannt, da ihr Gesicht nicht vollständig zu sehen ist:

```{figure} ../assets/annotation/SoloSunny_Figuren_Fehler1.gif
---
align: center
width: 100%
name: SoloSunny_Figuren_Fehler1
alt: Sunny wurde in den gezeigten Einstellungen nicht erkannt. 
---
Sunny wurde in den gezeigten Einstellungen nicht erkannt. 
```
Durch die Wahl geringerer Schwellenwerte von `FACE_DETECTION_THRESHOLD = 0.1` und `CHARACTER_RECOGNITION_THRESHOLD = 0.15` konnte die Erkennung in diesen Einstellung leicht verbessert werden. Zwar wird Sunny weiterhin nicht durchgehend erkannt, jedoch reichen Treffer in einzelnen Frames aus, damit ihr in der `Sunny_matched` Spur die gesamte Einstellung zugeordnet wird. Allerdings führten dieselben Schwellenwerte auch zu Falscherkennungen, bei denen etwa Frau im Bett als Sunny erkannt wurde.

```{figure} ../assets/annotation/SoloSunny_Figuren_Änderung1.gif
---
align: center
width: 100%
name: SoloSunny_Figuren_Änderung1
alt: Sunny wurde in den gezeigten Einstellungen mit den Schwellenwerten FACE_DETECTION_THRESHOLD = 0.1 und CHARACTER_RECOGNITION_THRESHOLD = 0.15 teilweise erkannt. 
---
Sunny wurde in den gezeigten Einstellungen mit den Schwellenwerten `FACE_DETECTION_THRESHOLD = 0.1` und `CHARACTER_RECOGNITION_THRESHOLD = 0.15` teilweise erkannt. 
```

Was passiert, wenn wir stattdessen sehr hohe Schwellenwert einsetzten, etwa `0.8`?
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
``````
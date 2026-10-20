# Einstellungserkennung: Datensichtung mit VIAN

Nachdem die Einstellungs-Annotationen für den Trailer zu *Der geteilte Himmel* automatisch durch das [Jupyter Notebook](einstellung_notebook.ipynb) erstellt wurden, ist es an der Zeit, diese in VIAN zu sichten.
Die Verwendung von VIAN wurde bereits im Kapitel zu den [Technischen Grundlagen](technik.md#vian-installation-und-verwendung) auszugsweise vorgestellt.

Für die Sichtung in VIAN (oder einem anderen Annotationsprogramm) wurde vom Jupyter Notebook eine `.eaf`-Datei erstellt, mittels derer sich die Einstellungs-Annotationen importieren lassen.

Nach dem Verlinken des Trailer und dem Import der dazugehörigen `.eaf`-Datei kann das Ergebnis der Einstellungserkennung für *Der geteilte Himmel* gesichtet werden.

```{figure} ../assets/annotation/VIAN_postImport.png
---
align: center
width: 100%
name: VIAN_Himmel
alt: Die Einstellungsannotationen nach dem Import in VIAN.
---
Die Einstellungsannotationen nach dem Import in VIAN.
```

Mit dem Abspielen des Trailers bzw. dem Scrubbing in der Timeline werden Sie feststellen, dass die Einstellungserkennung in diesem Fall tadellos funktioniert hat. Die einzelnen nummerierten 'Annotationsblöcke' sind perfekt mit den Einstellungswechseln synchronisiert. Insgesamt wurden 23 Einstellungen erkannt.

Allerdings funktioniert die Erkennung mit dem Standard-Schwellenwert von `0.5` nicht für alle Trailer der Filme Konrad Wolfs fehlerlos.

Im Trailer zu *Mama, ich lebe* werden zu Beginn *behind-the-scenes* Fotografien gezeigt. Hier wurde bei einem Schwellenwert von ´0.5`der Übergang zwischen zwei ähnlichen Bildern innerhalb der Einstellung 12 nicht erkannt:

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

Weniger ein Fehler als eine Inkonsistenz ist die die Erkennung von Vor- und Abspann, die teilweise als eigene Einstellung, teilweise aufgrund einer Transition als Teil einer Einstellung erkannt wurden. Im Fall des Trailers zu *Leute mit Flügeln* wurde der Vorspann zudem mit dem Auftauchen des Texts in mehrere Einstellungen unterteilt. Zwar handelt es sich hierbei nur um kleine Abweichungen, aber bei einem Vergleich von Filmen sollten derartige Inkonsistenzen bereinigt werden, zum Beispiel durch eine händische Bearbeitung in VIAN.

``````{admonition} Übung
:class: exercise
Versuchen Sie, die oben aufgelisteten Fehler durch eine erneute Auswertung der Trailer mit einem anderen Schwellenwert zu beseitigen. Sie können die zusätzlichen Trailer hier herunterladen **[Link folgt]**.

`````{admonition}  Lösung
:class: solution, dropdown
Ein Schwellenwert von 0.25 bereinigt die Fehler im *Mama, ich lebe* Trailer. Im Fall vom *Solo Sunny* Trailer führt derselbe Schwellenwert  allerdings zu falsch erkannten Einstellung. So wurde etwa Einstellung 53 aufgrund des zuvor abgedeckten Lichts in die Kamera fälschlicherweise aufgeteilt:

```{figure} ../assets/annotation/SoloSunny_Fehler2.gif
---
align: center
width: 100%
name: SoloSunny_Fehler2
alt: Der neu entstandene Fehler in Solo Sunny.
---
Der neu entstandene Fehler in *Solo Sunny*.
```
Ein Schwellenwert, der für einen Film gute Ergebnisse liefert, passt nicht zwangsläufig für andere Filme. Es kann daher ja nach Forschungsvorhaben sinnvoll sein, für jeden Film einen passenden Schwellenwert zu finden. 
``````

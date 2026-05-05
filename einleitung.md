# Workflows zur automatisierten Filmannotation – Einstellungs- und Figurenerkennung am Beispiel der Filme Konrad Wolfs

````{margin}
```{admonition} Fragen oder Feedback
:class: frage-feedback

<a href="https://github.com/quadriga-dk/Bewegtes-Bild-Fallstudie-4/issues/new?assignees=&labels=question&projects=&template=frage.yml" class="external-link" target="_blank">
    Stellen Sie eine Frage
</a> <br>
<a href="https://github.com/quadriga-dk/Bewegtes-Bild-Fallstudie-4/issues/new?assignees=&labels=feedback&projects=&template=feedback.yml" class="external-link" target="_blank">
    Geben Sie uns Feedback
</a>

Mit Ihren Rückmeldungen können wir unser Template gezielt an Ihre Bedürfnisse anpassen.


```
````

`````{margin}
````{admonition} Zitierhinweis
:class: citation-information
```{literalinclude} /CITATION.bib
:language: bibtex
```
Schick, T., Winter, M., Loist, S. & Gieseke, L. (2026). _Workflows zur automatisierten Filmannotation – Einstellungs- und Figurenerkennung am Beispiel der Filme Konrad Wolfs_ https://doi.org/10.5281/zenodo.ToDo

````
`````

Im Rahmen der Digital Humanities werden in verschiedenen Bereichen der Geisteswissenschaften in den letzten Jahren verstärkt digitale Werkzeuge und digitale Methoden eingesetzt. Auch die Filmwissenschaft beschäftigt sich mit den Möglichkeiten und Grenzen digitaler Ansätze. So widmet die Zeitschrift _montage/av_ im Jahr 2020 eine Ausgabe dem Thema <a href="https://montage-av.de/29-1-2020/" class="external-link" target="_blank">Digitale Praktiken</a> in der Filmforschung, im gleichen Jahr erscheint in _Digital Humanities Quarterly (DHQ)_ ein Themenschwerpunkt zu <a href="https://digitalhumanities.org/dhq/vol/14/4/index.html" class="external-link" target="_blank">Digital Humanities & Film Studies</a>. Für die Filmgeschichtsschreibung zeigt der Sammelband _Doing Digital Film History_ {cite}`a-Dang_van_der_Heijden_Olesen_2025` verschiedene Perspektiven digitaler Herangehensweisen auf.

Die vorliegende _Open Educational Resource (OER)_[^1] wurde in Form eines <a href="https://jupyterbook.org/" class="external-link" target="_blank">Jupyter Books</a> auf der Grundlage einer Fallstudie entwickelt. Sie befasst sich mit einer filmwissenschaftlichen Fragestellung und erkundet, wie für deren Bearbeitung digitale Verfahren sinnvoll eingesetzt werden können. Im Mittelpunkt der exemplarischen Untersuchung stehen die Filme <a href="https://de.wikipedia.org/wiki/Konrad_Wolf" class="external-link" target="_blank">Konrad Wolfs</a>. Ausgangspunkt für die Fallstudie bildet folgende Frage: **Welche besonderen stilistischen Merkmale und welche persönliche Handschrift weisen die Filme Konrad Wolfs auf?**

Die OER führt anhand eines konkreten Beispiels in einige grundlegende Aspekte des digitalen Arbeitens in der Filmwissenschaft ein. Dabei nimmt die Fallstudie vor allem die automatisierte Erstellung von Film-Annotationen in den Blick. Mit Python-Skripten werden in Jupyter-Notebooks die Länge der Einstellungen und das Auftreten von Figuren in Filmen annotiert und die Ergebnisse als Werte in csv-Dateien ausgegeben. Diese Annotationen werden überprüft, interpretiert und für die weitere Analyse der Filme Konrad Wolfs nutzbar gemacht.

## Zielgruppe

Diese _Open Educational Resource (OER)_ richtet sich in Form eines _Selbstlernkurses_ an Wissenschaftler:innen, die sich für die Bearbeitung filmwissenschaftlicher Fragestellungen mithilfe digitaler Methoden und Tools interessieren. Die Fallstudie wurde in erster Linie für Forschende der Film- und Medienwissenschaft entwickelt. Sie bietet aber auch wertvolle Einblicke für Vertreter:innen anderer geisteswissenschaftlicher Disziplinen wie z.B. der Geschichts- oder Informationswissenschaft, die sich in ihren Forschungsprojekten mit Bewegtbildmaterial beschäftigen möchten. Besondere Vorkenntnisse sind nicht erforderlich. Die OER kann dabei sowohl für das eigene Lernen als auch in der Lehre eingesetzt werden.

## Struktur der Fallstudie

Die Darstellung der Fallstudie in dieser Open Educational Resource ist in mehrere Schritte unterteilt.

```{figure} ./assets/intro/Grafik_Schritte.png
---
align: center
width: 100%
---
Schritte der Fallstudie
```

In einem [einleitenden Kapitel](einstieg/einleitung) werden die Lernziele und die technischen Voraussetzungen vorgestellt. Die daran anschließende Fallstudie ist folgendermaßen gegliedert:

- im **1. Schritt** wird die Rolle von Annotationen für die Analyse von Filmen beschrieben. Quantitative Ansätze in der Filmwissenschaft werden dargestellt und kritisch reflektiert, bevor mögliche Einsatzbereiche der automatisierten Filmannotation vorgestellt werden. Schließlich wird eine filmwissenschaftliche Fragestellung formuliert und operationalisiert, die mithilfe automatisierter Filmannotation bearbeitet werden kann (siehe Kapitel [Filmanalyse und automatisierte Annotation](filmanalyse/einleitung)).

- im **2. Schritt** werden die Möglichkeiten von Computer Vision im Rahmen filmanalytischer Prozesse genauer beleuchtet und grundlegende Begriffe wie Machine Learning, Algorithmus und Modell erläutert. Die Möglichkeiten und Grenzen von Computer Vision Modellen bei der automatisierten Annotation von Filmen werden diskutiert (siehe Kapitel [Computer Vision für die Filmanalyse](vision/einleitung)).

- im **3. Schritt** werden geeignete Modelle für die Einstellungs- und Figurenerkennung in einem Film ausgewählt und diese mithilfe von Python-Skripten durchgeführt. Daran anschließend wird die Qualität der erhaltenen Annotationsdaten überprüft und beurteilt. (siehe Kapitel [Automatisierte Annotation von Filmen](annotation/einleitung)).

- im **4.Schritt** findet eine Auswertung des automatisiert erstellten Film-Annotationen statt. Es werden Berechnungen aus den erhaltenden Werten angestellt und Annotationsdaten mithilfe von Python-Skripten visualisiert (siehe Kapitel [Auswertung der automatisierten Annotationen](auswertung/einleitung)).

In einem [abschließenden Kapitel](reflexion-und-resümee/einleitung) werden die Ergebnisse der Fallstudie zusammengefasst und reflektiert, gefolgt von einem Ausblick auf weitere mögliche Einsatzbereiche der automatisierten Annotation von Filmen.


## Literatur

```{bibliography}
:filter: docname in docnames
:keyprefix: a-
```
[^1]: Weitere Informationen zum Konzept von Open Educational Resources finden sich auf <a href="https://open-educational-resources.de/" class="external-link" target="_blank">OERinfo</a>

# Technische Voraussetzungen

Die Fallstudie umfasst erklärende Texte, ausführbaren Code und Übungen zur Selbstüberprüfung. Der Code liegt in <a href="https://jupyter.org/"  class="external-link" target="_blank">*Jupyter Notebooks*</a> vor und kann einerseits hier im <a href="https://jupyterbook.org/" class="external-link" target="_blank">*Jupyter Book*</a> gelesen, andererseits mit dem Dienst <a href="https://colab.research.google.com/" class="external-link" target="_blank">*Colab*</a> oder lokal auf dem eigenen Computer ausgeführt werden. Diese drei Nutzungsszenarien nennen wir Nutzungs-Modi. 

```{admonition} "Jupyter Book" und "Jupyter Notebook" – was ist der Unterschied?
:class: hinweis
- Ein <a href="https://jupyter.org/"  class="external-link" target="_blank">***Jupyter Notebook***</a> ist eine interaktive Seite, die erklärenden Text mit ausführbarem Code und dessen Ergebnissen (z.B. Tabellen oder Grafiken) verbindet – zum Beispiel die Seite [Automatische Erkennung von Einstellungen mit *TransNetV2*](../annotation/einstellungen_notebook.ipynb). Solche Notebook-Seiten erkennen Sie in der Menüleiste links an der Rakete (🚀) im Titel.
- Ein <a href="https://jupyterbook.org/" class="external-link" target="_blank">***Jupyter Book***</a> enthält reine Textseiten und Seiten mit Jupyter Notebooks. Es hat die Form einer im Browser lesbaren Website – ist also einer Art Online-Buch. Diese gesamte Fallstudie mit all ihren Kapiteln und Unterkapiteln, die Sie gerade lesen, *ist* ein solches *Jupyter Book*.
```

## Nutzungs-Modi
- Im **"Book-Only Mode"** lesen Sie in Ihrem Internet-Browser unser *Jupyter Book* und haben eingeschränkte Möglichkeiten zu interagieren, etwa mit Visualisierungen. Sie können den Code und seine bereits erzeugten Ausgaben zwar sehen, ihn aber nicht selbst ausführen. Dieser Modus erfordert keine Programmierkenntnisse und keine Erfahrungen im Umgang mit der interaktiven Programmierumgebung *Jupyter Notebook*.
- Im **"Cloud Mode"** können Sie darüber hinaus die in diesem *Jupyter Book* enthaltenen *Jupyter Notebooks* über den webbasierten Dienst <a href="https://colab.research.google.com/" class="external-link" target="_blank">*Colab*</a> von Google aktiv ausführen, den Code verändern und ggf. auch für eigene Forschungsfragen adaptieren. Unterkapitel dieser Fallstudie, die in Form von *Jupyter Notebooks* vorliegen und die Sie entsprechend im *Cloud Mode* ausführen können, weisen oben rechts eine Rakete (🚀) auf. Klicken Sie auf die Rakete und öffnen Sie das *Jupyter Notebook* auf *Colab*. Um ein *Jupyter Notebook* in *Colab* auszuführen, benötigen Sie einen Google-Account. Wenn Sie bei ihrem Account eine institutionelle E-Mail-Adresse angegeben haben, kann es zu Problemen beim Login kommen. Sie müssen dann ein neues Browser-Fenster öffnen und auf einen privaten Google-Account wechseln. 
- Im **"Local Mode"** laden Sie das "Jupyter Notebook" auf Ihren eigenen Computer und führen es dort in einer entsprechenden Umgebung aus (z.B. im <a href="https://www.anaconda.com/products/navigator" class="external-link" target="_blank">Anaconda Navigator</a>). Hier haben Sie ebenfalls die Möglichkeit, den Code aktiv auszuführen, ihn zu verändern und ggf. auch für eigene Forschungsfragen zu adaptieren. Dabei können Sie auch Daten nutzen, die Sie lokal auf Ihrem Computer vorhalten. Zum Herunterladen des Notebooks klicken Sie oben rechts in der Menüleiste auf das Download-Symbol ↓ und wählen Sie „.ipynb“. Abhängig von Browser und Betriebssystem müssen Sie die Datei mit Rechtsklick auf „.ipynb“ ggf. manuell herunterladen.

```{admonition} Wie führe ich den Code in einem *Jupyter Notebook* aus?
:class: tip
Der Code eines *Jupyter Notebooks* ist in einzelne **Code-Zellen** unterteilt, die Sie nacheinander von oben nach unten ausführen. Eine einzelne Zelle starten Sie, indem Sie links neben der Zelle auf das dreieckige **"Play"-Symbol** (▶) klicken. In *Colab* wird dieses Symbol erst sichtbar, wenn Sie die Maus über die Zelle bewegen (oder die Zelle anklicken). Alternativ führen Sie die gerade ausgewählte Zelle mit der Tastenkombination **Umschalt + Eingabe** (`Shift` + `Enter`) aus.
```

Bitte beachten Sie auch die Informationen zum Ausführen der *Jupyter Notebooks* zur Einstellungs- und Figurenerkennung im Kapitel zu [Technischen Grundlagen](../annotation/technik.md) bezüglich der [verwendeten Hardware](../annotation/technik.md#verwendete-hardware) und spezifischen Einstellungen in [Google Colab](../annotation/technik.md#ausfuhrungsmodi).

```{admonition} Hinweis
:class: hinweis
Für den besten Lernerfolg empfehlen wir, die *Jupyter Notebooks* in einer entsprechenden Umgebung zu öffnen und die einzelnen Codeblöcke nacheinander auszuführen.
```

Weitere Hinweise zur Arbeit mit *Jupyter Book*, *Jupyter Notebooks* und zur Installation von Anaconda für die Nutzung im *Local Mode* vermitteln folgende Tutorials:

`````{admonition} Tutorials
:class: seealso
- <a href="https://digital-history-berlin.github.io/Python-fuer-Historiker-innen/ch00-preface/04-nutzung.html" class="external-link" target="_blank">Tutorial zur Arbeit mit Jupyter Books</a>
- <a href="https://www.elab2go.de/demo-py1/jupyter-notebooks.php#1WasisteinJupyterNotebook" class="external-link" target="_blank">Tutorial zur Arbeit mit Jupyter Notebooks</a> 
- <a href="https://www.elab2go.de/demo-py1/installation-python-anaconda.php" class="external-link" target="_blank">Tutorial zur Installation und Nutzung von Anaconda</a>
`````

## Verwendung des Annotationstools VIAN

Für die Überprüfung der Annotationsergebnisse und und für die weitere Arbeit mit automatisiert erstellen Annotationen an konkreten Filmen wird in der OER das Analysetool VIAN verwendet. Eine Anleitung zur Installation und Hinweise zur Handhabung von VIAN finden Sie im Kapitel zu [technischen Grundlagen](../annotation/technik.md#vian-installation-und-verwendung). In der OER wird VIAN im [Kapitel 4.7](../annotation/einstellung_datensichtung.md) und [Kapitel 4.10](../annotation/figuren_datensichtung.md) zur Sichtung und Überprüfung der automatisiert erstellten Annotationsdaten verwendet. Weitere Informationen bietet die <a href="https://www.vian.app" class="external-link" target="_blank">VIAN Projektseite</a>, auf der <a href="https://github.com/Movie-Analytics/VIAN/releases" class="external-link" target="_blank">VIAN GitHub-Seite</a> können die aktuellsten Installationsdateien für verschiedene Betriebssysteme heruntergeladen werden.
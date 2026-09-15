(annotation:einleitung)=
# Automatisierte Annotation von Filmen

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

Die vorliegende Fallstudie befasst sich mit Workflows zur automatisierten Filmannotation. Am Beispiel der Filme Konrad Wolfs werden exemplarisch die Möglichkeiten der automatisierten Einstellungs- und Figurenerkennung dargestellt. In den folgenden Abschnitten stehen folgende Lernziele im Mittelpunkt:

```{include} ../einstieg/lernziele.md
:start-after: "<!-- START: Annotation -->"
:end-before: "<!-- END: Annotation -->"
```

Wir befinden uns damit beim 3. Schritt unserer Fallstudie, bei dem die automatisierte Annotation von Filmen praktisch umgesetzt wird. Zu Beginn des Kapitels stellen wir die Entwicklung des angewendeten Workflows dar, gehen auf die verwendeten Modelle ein und erklären die notwendigen technischen Voraussetzungen und Grundlagen. Mithilfe von Jupyter Notebooks wird schließlich die Erkennung von Einstellungen und die Erkennung von Figuren anhand von Trailern zu Filmen Konrad Wolfs durchgeführt. Die erzeugten Annotationsdaten werden mit dem Filmanalysetool VIAN gesichtet und überprüft.


```{figure} ../assets/annotation/Grafik_Schritte_3.png
---
align: center
width: 100%
name: grafik_schritte_3
alt: Grafik mit Darstellung der Schritte der OER. Der 3. Schritt ist farblich hervorgehoben.
---
Schritt 3: Automatisierte Annotation von Filmen
```


```{admonition} Bearbeitungszeit
:class: zeitinfo
Die geschätzte Bearbeitungszeit dieser Lerneinheit beträgt ca. **xx** Minuten. Dies schließt die gekennzeichneten Übungsaufgaben, deren Bearbeitungsdauer individuell variiert, aus.

Die geschätzte Bearbeitungsdauer **inklusive** der einzelnen Übungsaufgaben beträgt ca. **xx** Minuten.

Bitte beachten Sie: Die tatsächliche Bearbeitungsdauer kann je nach Ihren Vorkenntnissen unterschiedlich ausfallen. Die angegebene Zeitangabe dient lediglich als Orientierungshilfe.
```


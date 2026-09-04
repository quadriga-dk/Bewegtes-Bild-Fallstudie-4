# Grundlagen Computer Vision
In vorigen Kapitel wurde deutlich, dass für die automatisierte Annotation von Filmen der Einsatz von Techniken zur Computer Vision notwendig ist. Doch was ist mit "Computer Vision" eigentlich gemeint?
Computer Vision oder auch 'maschinelles Sehen' ist ein Teilgebiet der Künstlichen Intelligenz (KI). Visuelle Quellen wie Bilder oder Videos werden durch Computer bzw. Maschinen verarbeitet und analysiert. Lutz Priese beschreibt Computer Vision folgendermaßen:
>Computer Vision, auch maschinelles Sehen genannt, umfasst verschiedene Methoden zur Erfassung, Verarbeitung, Analyse und Interpretation von Bildern. Es ist ein Teilgebiet der Computervisualistik, die darüber hinaus Computergrafik und Visualisierung komplexer Daten beinhaltet. {cite}`ba-Priese_2015`

Mit dem Bereich der Visualisierung von Daten haben wir uns in der <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-2/auswertung/toc.html" class="external-link" target="_blank">Fallstudie zu studentischen Filmen</a> auseinandergesetzt. Die Computergrafik beschäftigt sich mit der Erzeugung von Bildern, Animationen oder Filmen mithilfe von Rechnern. Computer Vision geht nun den umgekehrten Weg: 

>In computer vision, we are trying to do the inverse, i.e., to describe the world that we see in one or more images and to reconstruct its properties, such as shape, illumination, and color distributions. {cite}`ba-Szeliski_2022`

Richard Szeliski führt auch verschiedene Bereiche in der Industrie an, bei denen heute Computer Vision zum Einsatz kommt, wie z.B. Optical Charakter Recognition (OCR), Bezahlvorgänge im voll automatisierten Geschäften, bei der Auswertung medizinischer Bildgebung (wie Röntgenbildern), beim autonomen Fahren, der Erstellung von 3D Modellen oder in der Biometrie und bei der Erkennung von Fingerabdrücken. Aber auch auf der Ebene der Konsument:innen ist Computer Vision zu finden, z.B. beim 'Stitching', also dem Zusammenfügen von sich überlappender Fotoaufnahmen, bei der Bildstabilisierung bei Videoaufnahmen oder der visuellen Authentifizierung, indem etwa der Computer oder das Handy durch den Blick in eine Kamera entsperrt werden.

Wie kann nun Computer Vision im Bereich der Filmanalyse und Filmannotation angewendet werden? Filme stellen letztlich eine große, strukturierte Menge visueller Daten dar. Videodateien setzten sich aus einer Abfolge einzelner digitaler Bilder, also 'Frames' zusammen, die aus einzelnen Pixeln bestehen. Die in diesen Bildern enthaltenen Informationen wie Helligkeit, Farbe oder auch Formen lassen sich mit numerischen Werten in verschiedenen Formaten beschreiben. Diese Werte können mit Techniken der Computer Vision extrahiert, verarbeitet und analysiert werden. Muster können so erkannt werden und durch Abgleich mit Referenzwerten mit anderen Mustern verglichen werden. Als Ausgabe erhält man z.B. Wahrscheinlichkeitswerte, in wieweit Muster in einem Bild mit vorgegebenen Vergleichsmustern übereinstimmen. Dies ist nur mithilfe von Algorithmen und Modellen möglich, die elementarer Bestandteil von Computer Vision sind und auf die wir im [folgenden Abschnitt](../vision/begriffe.md) noch genauer eingehen werden.

In diesem Kontext ist es wichtig zu beachten, dass Computer Vision, also 'maschinelles Sehen' nicht mit dem menschlichen Sehen gleichgesetzt werden kann. Die visuelle Welt ist viel zu komplex strukturiert, als dass sie ein Computer so differenziert wahrnehmen könnte wie ein Mensch. Letztlich wird von Menschen festgelegt, welche Merkmale oder Muster genau durch Computer Vision annotiert, also "gesehen" bzw. durch die Umsetzung in numerische Werte erfasst werden sollen.

Arnold Taylor und Lauren Tilton unterscheiden zwischen "seeing" als physikalischen Prozess der Wahrnehmung von Licht durch die geöffneten Augen und "looking", also einem intentionalen Prozess der aktiven Suche in der Wahrnehmung, einer Entscheidung, was wir sehen wollen. "Viewing" bedeutet für sie schließlich die Verknüpfung von Seeing und Looking in der Analyse digitaler Bilder {cite}`ba-Arnold_Tilton_2023`. Und dieses "Viewing" ist immer auch mit kulturellen und sozialen Normen verbunden, die z.B. beeinflussen, was im 'seeing' und 'looking' wahrgenommen wird.

>Designed with the intention to mimic the human eye and neural processes, computer vision algorithms look for certain features by following processes for calculating pixels to recognize patterns. Computer vision "sees" through numeracy and "looks" based on the assigned numerical patterns. Therefore, computer vision enables identification of practices of looking in visual materials and algorithmically creates practices of looking. Computer vision encodes social, cultural, historical, and political values algorithmically. {cite}`ba-Arnold_Tilton_2023`

Diese Einschreibung von Werten in Techniken der Computer Vision sollte bei deren Anwendung fur filmanalytische Zwecke wie der automatisierten Annotation von Filmen immer beachtet und reflektiert werden. Dazu gehört auch wenn immer möglich Informationen darüber einzubeziehen, in welchen Kontexten die verwendeten Algorithmen oder Modelle ursprünglich entstanden sind (z.B. Militär, Überwachung etc.). Auf dieses Thema werden wir [folgeden Abschnitt](../vision/begriffe.md) nochmals zu sprechen kommen.






## Literatur
```{bibliography}
:filter: docname in docnames
:keyprefix: ba-
```
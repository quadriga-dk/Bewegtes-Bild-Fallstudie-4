# Zentrale Begriffe und Konzepte
Nachdem im vorigen Abschnitt auf die Grundlagen von Computer Vision eingegangen wurde, sollen im Folgenden einige bereits erwähnte Begriffe und Konzepte genauer geklärt werden.

## Algorithmus
Algorithmen wurden als grundlegend wichtig für Prozesse der Computer Vision beschrieben. Unter einem Algorithmus versteht man dabei zunächst die genaue Beschreibung einzelner aufeinanderfolgender Schritte zur Bearbeitung einer Aufgabe. Thomas Corman et al. definieren den Begriff somit folgendermaßen:

> Ein Algorithmus ist grob gesprochen eine wohldefinierte Rechenvorschrift, die einen Wert oder eine Menge von Werten als Eingabe verwendet und in endlicher Zeit einen Wert oder eine Menge von Werten als Ausgabe erzeugt. Ein Algorithmus ist also eine Folge von Rechenschritten, die die Eingabe in die Ausgabe umwandelt. {cite}`bb-Cormen_Leiserson_Rivest_Stein_2025`

Wichtig ist dabei eine genaue Beschreibung der Abfolge der einzelnen Schritte. Bei Corman et al. klingt dies sehr mathematisch und v.a. auf die Verarbeitung durch Computer bezogen. Thomas Scherer weist jedoch darauf hin, dass Algorithmen nicht unbedingt computerbasiert sein müssen. sondern lediglich die Ausführung eines Sets an Anweisungen {cite}`bb-Scherer_2025`. Er bezieht sich dabei auf Jamie 'Skye' Bianco, der einen Vergleich von Algorithmus mit einem Backrezept anstellt:

>An algorithm, in itself, is not computational. It is a set of modular or autonomous instructions – in execution – for the doing or making of something, which includes necessary elements, constraints and procedure, taken together dynamically. Often when definitions of algorithms are offered to a non-technical audience, the algorithm cooks up through the metaphor of the recipe and its relation to baking. The list of ingredients corresponds to input, a data set and/or variables, and the step-bystep instructions for mixing, blending, sifting, blanching and heating food ingredients corresponds to the procedural, embedded, nested, iterative and return commands composed through code. And just as the recipe for pumpkin bread is not the baked pumpkin bread, the code itself is not algorithmic until it is run. {cite}`bb-Bianco_2018`

Solche Algorithmen können z.B. durch sogenannten 'Pseudocode' beschrieben werden, also einer Mischung von Elementen der natürlichen Sprache mit Elementen aus Programmiersprachen. Solch ein Pseudocode kann selbst nicht ausgeführt werden, er gibt aber die einzelnen Schritte es Algorithmus genau wieder und kann ggf. in eine Programmiersprache übersetzt werden.

Wichtig ist, dass Algorithmen - auch sehr komplexe - insgesamt transparent sind und prinzipiell jeder Schritt reproduzierbar ist. Im Grunde könnten die einzelnen Schritte und Anweisungen nicht nur durch Maschinen, sondern auch durch Menschen ausgeführt werden.

## Modell
Ein Modell hingegen wird anhand von Trainingsdaten mithilfe von Algorithmen "geschult". Ziel ist es dabei, nach der Eingabe von Daten durch die Anwendung eines Modells eine bestimmte Ausgabe zu erhalten, z.B. Vorhersagen zu treffen oder Muster zu erkennen. So kann etwa durch die Anwendung eines Modells bei der Eingabe eines Bildes ein Wahrscheinlichkeitswert ausgegeben werden, in wieweit ein darauf abgebildetes Gesicht einem Gesicht aus einem Referenzbild entspricht.

Ein Modell kann somit als eine Art Werkzeug gesehen werden, das mit Algorithmen in einem Trainingsprozess entstanden ist. Algorithmen und Modelle sind also nicht identisch, sondern Algorithmen sind Bestandteile von Modellen, die eine bestimmte Aufgabe auf einen Datensatz anwenden können. Für komplexere Aufgaben werden häufig verschiedene Modelle kombiniert, um dadurch völlig neue Funktionen zu erlangen.

## Machine Learning
Wie oben erwähnt sollen Modelle darauf 'trainiert' werden, bestimmte Aufgaben zuverlässig zu erfüllen. Hierfür ist Machine Learning von Bedeutung. Auf der Grundlage von vorhandenen annotierten Datensätzen können bestimmte Muster 'erlernt' werden. Thomas Cormen et al, schreibt hierzu:

>Maschinelles Lernen kann als Technologie angesehen werden, mit der algorithmische Aufgaben ausgeführt werden können, ohne explizit einen Algorithmus zu entwerfen. Stattdessen werden beim maschinellen Lernen aus Daten Muster abgeleitet und auf diese Weise Lösungen gelernt. Auf den ersten Blick könnte man daher meinen, dass das maschinelle Lernen, indem es den Prozess des Algorithmenentwurfs automatisiert, das Studium von Algorithmen überflüssig macht. Doch tatsächlich ist das Gegenteil der Fall. Maschinelles Lernen ist selbst eine Sammlung von Algorithmen, nur dass ein anderer Name verwendet wird. Außerdem sieht es im Moment danach aus, dass die Erfolge des maschinellen Lernens vor allem für Probleme zu verzeichnen sind, für die wir Menschen nicht wirklich verstehen, was der richtige Algorithmus ist. Als Beispiele hierfür seien das maschinelle Sehen (Computer Vision) und das maschinelle Übersetzen genannt. {cite}`bb-Cormen_Leiserson_Rivest_Stein_2025`

Hier wird also Computer Vision explizit als ein Feld des maschinellen Lernens genannt. Für das maschinelle Erlernen von Einstellungsgrößen müsste z.B. ein Datensatz erstellt werden, in dem die einzelnen Einstellungsgrößen wie Close Up oder Totale annotiert sind und der als Grundlage für den Lernprozess dienen kann. Als wichtige erste Quellen für das Training von Computer Vision nennt Daniel Chávez Heras Bildersammlungen im Internet wie ImageNet oder Flickr {cite}`bb-Chávez_Heras_2024`. Diese wurden von Nutzer:innen in Form von Crowdsourcing mit Labeln annotiert und können somit für Machine Learning verwendet werden.

Wichtig ist hierbei zu beachten, dass die Datensätze, die für maschinelles Lernen verwendet werden, von Menschen erstellt und annotiert wurden. Der kulturelle Hintergrund der Annotierenden, wie z.B. bestimmte Sprachmuster, Wertvorstellungen und Beurteilungen sind in diese Annotationen eingeschrieben - und damit auch in das durch maschinelles Lernen erzeugte Modell. Die erzeugten Modelle sind also in sich niemals 'objektiv' oder 'neutal'.

## Deep Learning
Deep Learning stellt einen Teilbereich des Machine Learning dar. Es beruht auf sogenannten künstlichen neuronalen Netzen, die verschiedene Ebenen und Tiefen aufweisen können. Vorbild waren ursprünglich die neuronalen Verknüpfungen im menschlichen Gehirn, Deep Learning hat sich aber in seiner Entwicklung immer mehr von diesem Vorbild entfernt und heute nur noch wenig damit zu tun. Ian Goodfellow et al. beschreibt Deep Learning folgendermaßen:

>This solution is to allow computers to learn from experience and understand the world in terms of a hierarchy of concepts, with each concept deﬁned through its relation to simpler concepts. By gathering knowledge from experience, this approach avoids the need for human operators to formally specify all the knowledge that the computer needs. The hierarchy of concepts enables the computer to learn complicated concepts by building them out of simpler ones. If we draw a graph showing how these concepts are built on top of each other, the graph is deep, with many layers. For this reason, we call this approach to AI deep learning. {cite}`bb-Goodfellow_Bengio_Courville_2016`

Taylor Arnold und Lauren Tilton erklären dies anhand eines Beispiels aus der Bildverarbeitung: Es werden immer größere 'Fenster' eines Objekts betrachtet, bis hin zum gesamten Bild. Auf der ersten Verarbeitungsebene eines neuronalen Netzes werden kleinste, benachbarte Bildbereiche erfasst und in Zahlen etwa für Farbe und Schattierung übersetzt; der nächstgrößere 'Blick' richtet sich auf Texturen wie Gras oder Kanten einzelner Objekte. Auf einer weiteren Ebene werden kleinere Objekte wie Nasen und dann größere Objekte wie ein Gesicht erkannt und schließlich ganze Objekte in ihrem Kontext. Jede Ebene baut also auf den Merkmalen der vorherigen auf {cite}`bb-Arnold_Tilton_2020`.

Merkmale werden hier also selbständig aus Rohdaten gelernt, der Mensch gibt nicht mehr vor, welche Merkmale erfasst werden sollen. Daraus ergibt sich, dass es für Menschen meist nicht mehr nachvollziehbar ist, wie ein Modell mittels Deep Learning überhaupt entstanden ist. Taylor Arnold und Lauren Tilton schreiben hierzu: "Unfortunately, the layered nature also comes at the cost of interpretability. It is notoriously difficult, if not outright impossible, to comprehend how neural networks achieve their amazing predictive results." {cite}`bb-Arnold_Tilton_2020`

## Schwellenwert
Wie bereits ausgeführt wurde geben Modelle bestimmte Werte aus, die angeben, mit welcher Wahrscheinlichkeit ein bestimmtes Muster oder ein Merkmal erkannt wurde. Dieser 'Confidence Score' liegt in der Regel bei Werten zwischen 0 und 1. Je höher der Wert, desto wahrscheinlicher ist es für ein Modell, dass ein Merkmal erkannt wurde.

In diesem Kontext ist die Festlegung eines Schwellenwertes relevant, um aus den Confidence Score Werten konkrete Annotationen zu erzeugen. Wird ein bestimmter Schwellenwert überschritten, wird ein Merkmal oder ein Objekt als erkannt eingestuft. Ein Modell kann z.B. für die Erkennung eines Gesichts einen Wert von 0,73 ausgeben. Bei einem Schwellenwert von 0,50 ist die Erkennung positiv, bei einem Schwellenwert von 0,80 wäre dies nicht der Fall. Der Schwellenwert überführt damit eine Ausgabe eines Modells in eine konkrete Annotation.

Die Festlegung von Schwellenwerten ist dabei Teil des Forschungsprozesses, da dieser maßgeblich beeinflussen kann, wie viele und welche Treffer sich bei einem Erkennungsprozess ergeben. Wie und warum welche Schwellenwerte festgelegt wurden, muss daher thematisiert und offengelegt werden.

## Embeddings
Mithilfe von Embeddings können beim Machine Learning und bei Modellen komplexe Muster und Beziehungen in Daten gelernt und erkannt werden. Hierfür werden Merkmale und semantische Eigenschaften von Objekten z.B. in Bildern durch neuronale Netze in numerische Werte übersetzt: "An embedding applies a selection of lower-level transformations from a neural network to an object of interest, the output of which can be viewed as a sequence of numeric values." {cite}`bb-Arnold_Tilton_2020` Dies erfolgt in Form von mathematischen Vektoren in einem mehrdimensionalen Raum, von denen man sich vorstellen kann, dass sie in bestimmte Richtungen deuten.

Solche Embeddings werden nun für viele Objekte erstellt und können miteinander verglichen werden. Objekte mit ähnlichen Merkmalen oder semantischen Eigenschaften werden auch ähnliche numerische Werte aufweisen, die Vektorpfeile deuten also gleichsam in eine ähnliche Richtung. Ähnlichkeiten können also festgestellt werden, ohne das vorab ein manuelles Annotieren von Datensätzen oder ein neues Training eines Modells notwendig wäre.


## Literatur
```{bibliography}
:filter: docname in docnames
:keyprefix: bb-
```
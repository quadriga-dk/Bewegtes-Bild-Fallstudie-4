# Technische Grundlagen

<iframe
  src="../_static/html/character_network_gravis.html"
  width="100%"
  height="800"
  style="border:0;">
</iframe>

Dieser Abschnitt stellt technische Grundlagen vor, die für das Verständnis und die Ausführung der Schritte des Workflows hilfreich sind. Dazu gehören die Qualität des Materials, die Bedeutung der Hardware, die Arbeit mit der Cloud-Umgebung *Google Colab*, die Einstellungsmöglichkeiten in den Jupyter Notebooks und die Verwendung der Annotationssoftware *VIAN*. Nach der Klärung der technischen Grundlagen können sich die folgenden Kapitel auf die Annotationsverfahren selbst konzentrieren.

## Qualität des Materials

Die Qualität des zu analysierenden Materials kann die Qualität der Ergebnisse erheblich beeinflussen.

Bei Videomaterial ist zunächst die Bildqualität zu nennen. Für die *face detection* und die *face recognition*  ist weniger die nominelle Videoauflösung entscheidend als vielmehr die tatsächlich verfügbaren Bildinformationen zum zu erkennenden Gesicht. Sehr kleine, unscharfe oder verdeckte Gesichter lassen sich schwieriger zuverlässig erkennen oder einer Person zuordnen. Eine höhere Ausgangsauflösung liefert zwar ggf. mehr verwertbare Details, garantiert aber nicht automatisch bessere Erkennungsergebnisse, da viele Machine-Learning-Modelle Eingabebilder intern auf eine feste Größe skalieren. Höher aufgelöstes Videomaterial kann zudem mehr Rechenaufwand bei der Verarbeitung verursachen.

Ein weiterer Faktor ist die Qualität der Digitalisierung und der Kompression. Bei der Kompression wird die Dateigröße durch die Umwandlung in ein anderes Format oder durch das Entfernen von Informationen verringert. Eine starke Kompression kann das Bild durch digitale Artefakte verzerren und dadurch die Erkennungsprozesse erschweren. In diesem Vergleich sind die durch Kompression entstandenen digitalen Artefakte gut erkennbar:

https://commons.wikimedia.org/wiki/File:Compression-artifacts.jpg
[wie setzten wir am besten die cc attribution um? evtl: Beispiel für durch Kompression entstehende Artefakte (T-tus, <a href="https://creativecommons.org/licenses/by/2.0/deed.en" class="external-link" target="_blank">CC BX 2.0 Generic</a>, Quelle: <a href="https://commons.wikimedia.org/wiki/File:Compression-artifacts.jpg" class="external-link" target="_blank">https://commons.wikimedia.org/wiki/File:Compression-artifacts.jpg</a>)]

Weitere relevante Faktoren sind Bildrauschen, Bewegungsunschärfe und Beleuchtung. Eine Vorverarbeitung, etwa durch Rauschreduktion oder Kontrastanpassung, kann in einzelnen Fällen helfen, aber auch neue Artefakte erzeugen. Deshalb sollte sie vorab am konkreten Material geprüft werden. Manche Schwierigkeiten sind dem Material selbst inhärent und lassen sich nicht beheben, ohne dessen künstlerischen Charakter zu verändern. So können sehr kurze Jump Cuts oder lange, graduelle Übergänge bei der Einstellungserkennung übersehen werden. Bei der Gesichtsanalyse können ungünstige Beleuchtung, starke Kopfbewegungen, Verdeckungen oder sehr kleine Gesichter die Analyse erschweren.

Ähnliche Faktoren gelten auch für die Audiospur. Ist diese stark komprimiert oder kommen künstlerische Effekte wie Verfremdungen der Stimme zum Einsatz, kann das die automatische Transkription erschweren.

## Verwendete Hardware

Wie im vorherigen Abschnitt erwähnt, kann die verfügbare Computerhardware die Ausführung von Machine-Learning-Modellen wesentlich beeinflussen. Für die Anwendung von Machine-Learning-Modellen sind diese Hardware-Komponenten besonders relevant:

- **CPU (Central Processing Unit):** Die CPU ist der allgemeine Prozessor des Computers. Sie führt Programmcode aus, steuert die Arbeit der anderen Komponenten und übernimmt viele unterschiedliche Aufgaben. Moderne CPUs besitzen mehrere Prozessorkerne und können manche Aufgaben gleichzeitig bearbeiten. Die meisten Machine-Learning-Modelle lassen sich auf einer CPU ausführen. Bei rechenintensiven neuronalen Netzen kann die Verarbeitung jedoch länger dauern, da die CPU nicht auf die gleichzeitige Ausführung mehrerer dabei anfallenden gleichartigen Rechenoperationen spezialisiert ist.

- **GPU (Graphics Processing Unit):** Die GPU ist der Grafikprozessor, der häufig auf einer Grafikkarte sitzt. Sie wurde ursprünglich vor allem für die schnelle Darstellung von Bildern entwickelt und kann viele ähnliche Rechenoperationen gleichzeitig ausführen. Das passt zu bestimmten Aufgaben von Machine-Learning-Modellen, bei denen große Mengen an Zahlen miteinander verrechnet werden. Daher kann eine GPU solche Analysen deutlich beschleunigen. Sie hilft aber nur, wenn das Modell und die verwendete Programmbibliothek Ausführung durch die GPU unterstützen und dafür eingerichtet sind. Eine GPU hat außerdem einen eigenen Arbeitsspeicher, den Videos und Modelle während der Berechnung mitbenutzen.

- **RAM (Random Access Memory):** Der RAM ist der Arbeitsspeicher des Computers. Er hält vorübergehend die Daten bereit, die gerade gebraucht werden, z.B. den laufenden Programmcode, geladene Videodaten, einzelne Frames und Zwischenergebnisse. Ein komprimiertes Video benötigt auf der Festplatte wenig Platz, kann während der Analyse im Arbeitsspeicher aber deutlich mehr Speicher belegen, weil die Bilder dafür dekodiert und verarbeitet werden. Je mehr oder höher aufgelöste Frames gleichzeitig bearbeitet werden, desto größer kann der Bedarf an Arbeitsspeicher sein. Ist zu wenig RAM verfügbar, muss der Computer Daten auslagern, wodurch die Bearbeitung langsamer wird, oder die Analyse bricht mit einem Speicherfehler ab.

Die Jupyter Notebooks können auch ohne GPU auf einer CPU ausgeführt werden. Als grobe Orientierung für die lokale Ausführung eignet sich ein aktueller Mehrkernprozessor, etwa ein Apple-Chip ab M1 oder eine vergleichbare CPU. Für umfangreichere Videos ist zusätzlicher Arbeitsspeicher hilfreich; 16 GB RAM sind ein sinnvoller Richtwert, aber keine geprüfte Mindestanforderung. Der tatsächliche Bedarf hängt vom Verfahren, der Videolänge und der Auflösung ab. Testen Sie den Workflow daher zuerst mit einem kurzen Video.

Für eine GPU-Beschleunigung über **CUDA** wird eine kompatible NVIDIA-Grafikkarte benötigt. CUDA ist eine vom GPU-Hersteller NVIDIA entwickelte Plattform, über die Programme Berechnungen auf NVIDIA-GPUs ausführen können. Die Grafikkarte allein reicht nicht aus: Auch Treiber, Programmbibliothek und CUDA-Version müssen zueinander passen. Eine GPU eines anderen Herstellers kann gegebenenfalls über eine andere technische Schnittstelle unterstützt werden, jedoch nicht über CUDA. Eine Übersicht unterstützter NVIDIA-GPUs bietet die <a href="https://developer.nvidia.com/cuda-gpus" class="external-link" target="_blank">NVIDIA CUDA-GPU-Liste</a>; ergänzend gibt es eine <a href="https://de.wikipedia.org/wiki/CUDA" class="external-link" target="_blank">Übersicht zu CUDA auf Wikipediae</a>.

Die Jupyter Notebooks in dieser OER prüfen, welche Hardware zur Verfügung steht und wählen automatisch die passende Ausführungsvariante aus. Kontrollieren Sie die Ausgabe an der entsprechenden Stelle des Notebooks. z.B. nach dem Codeblock zur Vorbereitung des verwendeten Modells, um zu sehen, ob eine CPU oder eine GPU für die Ausführung verwendet wird. 

## Google Colab

Als offenes Format können Jupyter Notebooks in vielen Umgebungen ausgeführt oder eingebunden werden. Als Alternative zur lokalen Ausführung bieten sich Cloud-Umgebungen an, in denen das Jupyter Notebook auf einem externen Server ausgeführt wird. Somit wird keine leistungsstarke Hardware auf dem eigenen Computer benötigt. Eine solche Umgebung ist *Google Colab*, in der die Jupyter Notebooks aus der OER heraus auf unterschiedlichen CPUs und GPUs ausgeführt werden können.

Dieses Kapitel ... **[Verlinkung auf allgemeines OER Kapitel]**.

Eine wichtige Ergänzung im Rahmen dieser Fallstudie ist, dass in *Google Colab* neben CPUs auch GPUs verwendet werden können. Das kann die Ausführung der hier vorgestellten Verfahren erheblich beschleunigen.

Um in Colab eine GPU auszuwählen, öffnen Sie im Menü **Laufzeit** den Punkt **Laufzeittyp ändern** (*Runtime → Change runtime type*). Wählen Sie im sich öffnenden Fenster **T4 GPU** aus und klicken Sie auf **Speichern** (*Save*). Je nach Verfügbarkeit und Colab-Konto wird möglicherweise eine andere GPU angeboten oder die Auswahl ist vorübergehend nicht möglich. Verbinden Sie sich anschließend mit der Laufzeit. Prüfen Sie in der Notebook-Ausgabe, welche Hardware tatsächlich verwendet wird. 
**[Hier fehlen noch Bilder und ich muss die deutschen Begriffe überprüfen]**

## Einstellungsmöglichkeiten in den Notebooks

Die Notebooks enthalten Einstellungsmöglichkeiten, mit denen sich der jeweilige Workflow anpassen lässt. Diese werden im Code als **Variablen** gespeichert. Eine Variable ist ein benannter Platzhalter für einen Wert, den das Programm später verwendet.

**[Winter]Hier gibt es ein bisschen wiederholung, da Parameter und Schwellwerte bereits zuvor eingeführt wurden. -> nochmal durchdenken, an welcher Stelle diese Infos am sinnvollsten eingeführt werden, ansonsten Verweis mit Link**

- **Variablen:** Eine Variable speichert einen Wert unter einem Namen, damit der Code ihn später verwenden kann. So kann eine Variable beispielsweise den Pfad zu einem Ordner enthalten.
- **Parameter:** Parameter sind Variablen, mit denen grundlegende Einstellungen des Workflows festgelegt werden. Dazu gehören zum Beispiel die Ordner für Eingabedateien und Exporte.
- **Schwellenwerte:** Ein Schwellenwert legt fest, ab welchem berechneten Wert ein Ergebnis als Treffer gilt. Bei einer Einstellungsübergangserkennung werden zum Beispiel nur Übergänge berücksichtigt, deren Wahrscheinlichkeit mindestens den festgelegten Schwellwert erreicht. Ein höherer Wert führt tendenziell zu weniger, aber sichereren Treffern. Ein niedrigerer Wert kann mehr Treffer, aber auch mehr Fehlalarme erzeugen.
- **Ordnerstruktur:** In den Notebooks wird festgelegt, aus welchem Eingabeordner die zu analysierenden Dateien gelesen und in welchem Exportordner die Ergebnisse gespeichert werden. Die genaue Ordnerstruktur und die dazugehörigen Einstellungen werden im jeweiligen Notebook erläutert.
- **Testdateien:** Für die erste Ausführung der Jupyter Notebooks können bereitgestellte Testdateien verwendet werden. Alternativ lassen sich eigene Dateien verwenden. Welche Testdateien zur Verfügung stehen wird im jeweiligen Notebook erklärt.

## VIAN: Installation und Verwendung

Im vorigen Abschnitt wurde Annotationsprogramm *VIAN* kurz angesprochen. Nun wird seine Verwendung im Detail erläutert, angefangen mit der Installation.

Zum Zeitpunkt des Verfassens dieser OER kann die aktuelle VIAN-Version über das <a href="https://github.com/Movie-Analytics/VIAN/releases" class="external-link" target="_blank">GitHub-Repositorium des Projekts</a> heruntergeladen werden. Es stehen Versionen zur Installation für macOS und Windows zur Verfügung.

Auf der Startseite von VIAN können bestehende Projekte geöffnet, importiert oder neu erstellt werden. Wenn Sie VIAN zum ersten Mal öffnen, werden noch keine bestehenden Projekte angezeigt. Um ein neues Projekt zu erstellen, öffnen Sie zunächst über die Schaltfläche `Video öffnen` ein Video.

```{figure} ../assets/annotation/VIAN_landingPage.png
---
align: center
width: 100%
name: VIAN_landingPage
alt: Das Startmenü von VIAN.
---
Das Startmenü von VIAN.
```

Anschließend gelangen Sie zum Hauptfenster von VIAN, in dem die in unserem Workflow automatisiert erstellten Annotationen gesichtet werden können. Diese Annotationsdaten müssen zunächst importiert werden. Wählen Sie dazu in der linken Seitenleiste den Menüpunkt `Daten importieren`. Anschließend können Sie zwischen den Dateiformaten `.eaf` und `.tsv` wählen. 

Wie wir im folgenden Kapitel genauer darstellen werden, wird nach den Ausführen des Jupyter Notebooks eine `ELAN-Datei` mit der Dateiendung `.eaf` im Export-Ordner generiert, die für den Import der Annotationsergebnisse in VIAN gedacht ist. Klicken sie also auf "ELAN-Annotationsergebnisse importieren" und wählen sie die erzeugte `.eaf`-Datei am entsprechenden Export-Speicherort aus. Der Import wird dann ausgeführt.

```{figure} ../assets/annotation/VIAN_ImportMenu.png
---
align: center
width: 100%
name: VIAN_ImportMenu
alt: Das Importmenü von VIAN.
---
Das Importmenü von VIAN.
```

**[Winter] Ab hier können die Nutzer:innen nicht mehr selbstständig folgen. Ist das so intendiert? Sollten wir einen Hinweis hinzufüfgen?**

Nach dem Import erscheinen die Annotationen als einzelne Spuren unter der Zeitleiste am unteren Rand des Hauptfensters. Wird das Video abgespielt, bewegt sich auch der rote Positionsanzeiger in der Zeitleiste. Sie können den Anzeiger außerdem mit der Maus verschieben oder auf die Zeitleiste Klicken, um zur entsprechenden Stelle im Video zu gelangen.

```{figure} ../assets/annotation/VIAN_postImport.png
---
align: center
width: 100%
name: VIAN_postImport
alt: Das Hauptfenster von VIAN nach dem Import von Annotationen.
---
Das Hauptfenster von VIAN nach dem Import von Annotationen.
```

Über den Reiter `Segmentierung` können Sie außerdem zu einer bestimmten Annotation springen. Klicken Sie dazu zuerst auf den Reiter `Segmentierung`, wählen Sie eine Annotationsspur aus und klicken Sie anschließend auf eine der Annotationen. [**Anm: besprechen, ob die Erklärung der Navigation mit Segmentierung notwendig ist, evtl. eher zoom in /out**]

```{figure} ../assets/annotation/VIAN_Segmentation.png
---
align: center
width: 100%
name: VIAN_Segmentation
alt: Das Segmentierungsmenü von VIAN.
---
Das Segmentierungsmenü von VIAN.
```

Diese VIAN-Funktionen sind ausreichend, um die Ergebnisse der automatisierten Annotation im Rahmen dieser OER zu sichten und zu überprüfen. VIAN bietet darüber hinaus weitere Funktionen, über die Sie sich in der offiziellen Dokumentation informieren können.
**[Hier später Link hinzufügen]**

Nach der Klärung dieser technischen Grundlagen folgt im nächsten Abschnitt die Vorstellung des Verfahrens zur Einstellungserkennung.

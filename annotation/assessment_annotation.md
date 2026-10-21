# 🏆Selbsttest: Wissen und Praxis

````{admonition} Wie nutze ich den Selbsttest?
:class: hinweis, dropdown
Diese Übungsaufgaben dienen Ihrer Selbsteinschätzung und helfen Ihnen, das im Kapitel Gelernte zu reflektieren.

Sie können die Fragen in beliebiger Reihenfolge bearbeiten und die Beantwortung auch mehrfach versuchen.

**So funktioniert es:**
- Wählen Sie bei jeder Frage die Antwort(en) aus, die Sie für richtig halten
- Lesen Sie das Feedback zu den einzelnen Antwortoptionen sorgfältig durch
- Die Erklärungen helfen Ihnen, Ihr Verständnis zu vertiefen – auch bei korrekten Antworten

Es erfolgt keine Bewertung oder Speicherung Ihrer Ergebnisse. Nutzen Sie dieses Assessment, um Wissenslücken zu identifizieren und gegebenenfalls die entsprechenden Abschnitte des Kapitels nochmals zu bearbeiten.

**Geschätzte Zeit**: XX Minuten

Viel Erfolg!
````

### Frage 1

**Ein Team möchte die Dauer einzelner Einstellungen in Filmen über Stadtverkehr bestimmen. Zur Auswahl stehen ein Verfahren für Einstellungsübergänge und ein Verfahren zur Erkennung sichtbarer Fahrzeuge. Welcher Ansatz passt am besten?**

[ ] Fahrzeugerkennung verwenden und jeden Wechsel des erkannten Fahrzeugtyps als Einstellungsgrenze behandeln.

    -- × Nicht korrekt. Ein Fahrzeugwechsel kann innerhalb einer Einstellung auftreten; umgekehrt kann ein Schnitt denselben Fahrzeugtyp zeigen. Die Erkennung von Gegenständen liefert daher nicht unmittelbar die benötigten Einstellungsgrenzen.
[x] Ein Modell für Einstellungsübergänge wie TransNetV2 einsetzen und aus den erkannten Grenzen mithilfe der Bildrate die Dauern bestimmen.

    -- ✓ Richtig! Die Aufgabe erfordert eine zeitliche Segmentierung. Das vorgestellte Modell berücksichtigt Bildfolgen und Veränderungen über mehrere Frames; die anschließende Aufbereitung überführt die Grenzen in Zeitangaben.
[ ] Das Verfahren mit der größeren Zahl ausgegebener Markierungen wählen und jede Markierung als neue Einstellung zählen.

    -- × Nicht korrekt. Die Menge der Ausgaben sagt nicht, ob sie Einstellungswechsel beschreiben. Außerdem können Markierungen fehlerhaft sein. Zunächst muss die Erkennungsaufgabe zum Untersuchungsziel passen.
[ ] Ein Modell zur Zuordnung von Gesichtern einsetzen, weil ein Wechsel der sichtbaren Person dieselbe zeitliche Gliederung liefert wie ein Schnitt.

    -- × Nicht korrekt. Personen können sich innerhalb einer Einstellung abwechseln oder über einen Schnitt hinweg sichtbar bleiben. Figurenpräsenz und Einstellungsgrenzen sind unterschiedliche Informationen.

### Frage 2

**Ein Projekt sucht in einem Spielfilm über eine Bergrettung drei vorher festgelegte Figuren. Welche Zusammenstellung unterstützt die Aufgabe am unmittelbarsten?**

[ ] Eine Gesichtslokalisierung genügt, wenn der erkannte Gesichtsrahmen anschließend mit dem Namen der wichtigsten Figur beschriftet wird.

    -- × Nicht korrekt. Der Rahmen zeigt, wo ein Gesicht liegt. Er liefert noch keine begründete Zuordnung zu einer der gesuchten Figuren.
[ ] Eine Gruppierung aller ähnlich aussehenden Gesichter genügt, weil die Gruppen ihre Figurennamen bereits aus dem Film erhalten.

    -- × Nicht korrekt. Eine explorative Gruppierung kann ähnliche Gesichter zusammenfassen, liefert aber nicht von sich aus die gewünschten Namen. Das Kapitel beschreibt dies als zusätzlichen Aufwand gegenüber dem referenzbasierten Vorgehen.
[x] Ein Verfahren zur Gesichtslokalisierung und zur Erstellung vergleichbarer Gesichtsrepräsentationen mit geeigneten Referenzbildern der drei Figuren kombinieren.

    -- ✓ Richtig! Nach der Lokalisierung und Aufbereitung werden Embeddings erzeugt und mit den vorbereiteten Vergleichs-Embeddings abgeglichen. Ein Paket wie InsightFace bündelt dafür mehrere spezialisierte Komponenten, ohne ihre unterschiedlichen Aufgaben aufzuheben.
[ ] Das Modell zur Einstellungserkennung unverändert verwenden und die gefundenen Einstellungen nacheinander den drei Figuren zuordnen.

    -- × Nicht korrekt. Eine zeitliche Segmentierung enthält keine Identitätszuordnung. Die Einstellungsdaten können später mit Figurenannotationen verbunden werden, ersetzen diese aber nicht.

### Frage 3

**Die Eingabevideos liegen bereits vor. Ein Team möchte das Notebook zur Einstellungserkennung in einer frischen Sitzung ausführen. Welche Reihenfolge beschreibt die Abhängigkeiten sinnvoll?**

[x] Parameter festlegen und benötigte Bibliotheken installieren beziehungsweise importieren; das vortrainierte Modell vorbereiten; Videos und Metadaten erfassen; Vorhersagen erzeugen, aufbereiten und exportieren.

    -- ✓ Richtig! Spätere Schritte bauen auf früheren Vorbereitungen auf. Das Modell wird für die Anwendung bereitgestellt; Metadaten wie die Bildrate werden für die zeitliche Aufbereitung benötigt.
[ ] Zuerst Ergebnisse exportieren, damit ihre Dateipfade feststehen; anschließend das Modell laden und die Ergebnisdateien als Videometadaten einlesen.

    -- × Nicht korrekt. Exportpfade können früh festgelegt werden, aber Ergebnisdaten existieren erst nach der Analyse und Aufbereitung. Sie sind nicht mit den technischen Eigenschaften der Eingabevideos gleichzusetzen.
[ ] Zuerst das Modell mit den neuen Videos trainieren; danach Bibliotheken importieren und die Schwellenwerte aus den fertigen Exportdateien bestimmen.

    -- × Nicht korrekt. Die Notebooks wenden vortrainierte Modelle an. Sie setzen weder ein neues Training voraus noch können Bibliotheksfunktionen vor ihrer Bereitstellung verwendet werden. Schwellenwerte müssen bei der Erzeugung konkreter Treffer berücksichtigt werden.
[ ] Bibliotheken installieren und unmittelbar die Exportzelle ausführen, weil Installation und Import zugleich alle Analyseschritte erledigen.

    -- × Nicht korrekt. Die Installation stellt Software bereit; ein Import macht sie in der Sitzung verfügbar. Beides erzeugt noch keine videobezogenen Annotationen.


### Frage 4

**Ein Team vergleicht mehrere vortrainierte Verfahren für ein neues Filmkorpus. Welche Entscheidungen sind sachgerecht?**

[x] Prüfen, ob die vorgesehene Erkennungsaufgabe sowie die benötigten Eingaben und Ausgaben zum eigenen Vorhaben passen.

    -- ✓ Richtig! Ein passendes Modell muss die benötigten Merkmale verarbeiten und Ergebnisse liefern, die sich im geplanten Workflow nutzen lassen.
[ ] Die meistzitierte Lösung bevorzugen und die Prüfung am eigenen Filmmaterial durch die hohe Zitierzahl ersetzen.

    -- × Nicht korrekt. Verbreitung kann eine begründete Vorauswahl unterstützen und Vergleiche erleichtern. Sie belegt aber nicht die Eignung für jedes Material und ersetzt keine Ergebnisprüfung.
[x] Neben dem Modell auch die Python-Implementierung, ihre Abhängigkeiten und Hinweise auf technische Probleme prüfen.

    -- ✓ Richtig! Ein Modell und eine Bibliothek zu seiner Verwendung sind nicht dasselbe. Auch eine inoffizielle Implementierung kann brauchbar sein, muss aber auf ihre konkrete Nutzbarkeit geprüft werden.
[ ] Eine Bibliothek mit gemeinsamer Schnittstelle für Gesichtslokalisierung und Identitätsvergleich ablehnen, weil darin keine getrennten Erkennungsaufgaben mehr stattfinden können.

    -- × Nicht korrekt. Eine gemeinsame Schnittstelle kann mehrere spezialisierte Modelle bündeln. Das vereinfacht die Anwendung, ohne die Aufgaben von Gesichtslokalisierung und Repräsentation beziehungsweise Zuordnung gleichzusetzen.
[x] Genauigkeit und Verarbeitungsgeschwindigkeit am vorgesehenen Material und mit der verfügbaren Hardware berücksichtigen.

    -- ✓ Richtig! Die Gesichtsanalyse im Kapitel vergleicht solche Eigenschaften und nutzt unterschiedliche Ausführungsvarianten. Ein Verfahren muss sowohl fachlich als auch praktisch zum Projekt passen.

### Frage 5

**Für einen Film über eine Theatergruppe soll die Figur „Nora“ erkannt werden. Welche Vorbereitungen passen zum referenzbasierten Verfahren des Notebooks?**

[x] Geeignete Aufnahmen aus mehreren Perspektiven und Situationen auswählen, auf denen jeweils nur Noras Gesicht für die Erkennung verfügbar ist.

    -- ✓ Richtig! Unterschiedliche geeignete Ansichten können die Vergleichsgrundlage verbessern. Die eindeutige Zuordnung pro Referenzbild verhindert, dass Gesichter verschiedener Personen vermischt werden.
[ ] Ein Gruppenbild unverändert als Referenz verwenden und die richtige Person allein durch den Dateinamen festlegen.

    -- × Nicht korrekt. Der Name sagt dem Verfahren nicht, welches von mehreren Gesichtern gemeint ist. Das Bild muss für diesen Zweck eindeutig vorbereitet werden, etwa durch einen Zuschnitt oder das Abdecken anderer Gesichter.
[x] Die Dateien beispielsweise als `Nora01.png` und `Nora02.png` benennen, damit die vorgesehene Namensauswertung beide Bilder derselben Figur zuordnet.

    -- ✓ Richtig! Der Code entfernt die letzten beiden Zeichen des Namens vor der Dateiendung. Diese Benennung ist eine Eingabekonvention, die bei der Anpassung des Skripts berücksichtigt werden muss, kein beliebiger Fallstudienname.
[ ] Zusätzliche Bilder nur dann verwenden, wenn das Erkennungsmodell anschließend vollständig neu trainiert wird.

    -- × Nicht korrekt. Das Notebook erzeugt mit einem vorhandenen Modell Vergleichs-Embeddings und fasst geeignete Referenzen pro Figur zusammen. Dies ist kein vollständiges Neutraining des Modells.
[x] Die Rückmeldungen zur Referenzerstellung kontrollieren und Bilder ohne eindeutig erfasstes Gesicht ersetzen oder überarbeiten.

    -- ✓ Richtig! Ungeeignete Referenzbilder liefern keine verlässliche Grundlage. Die Prüfung der tatsächlich erzeugten Vergleichs-Embeddings gehört zur Vorbereitung, nicht erst zur späteren Ergebnisinterpretation.

### Frage 6

**Nach einer erfolgreichen Ausführung liegen Einzelbildtreffer, zusammengefasste Figurenintervalle, Analysemetadaten und eine EAF-Datei vor. Welche Aussagen sind richtig?**

[ ] Der höchste Vorhersagewert in den Analysemetadaten gibt den Anteil aller korrekt erkannten Ereignisse im Film an.

    -- × Nicht korrekt. Ein maximaler Ausgabewert beschreibt die Werte des Modells, nicht den Vergleich aller Annotationen mit dem tatsächlichen Film. Die Einführung zur Einstellungserkennung stellt ausdrücklich klar, dass minimale und maximale Vorhersagewerte keine Genauigkeitsmessung sind.
[x] Einzelbildtreffer und zusammengefasste Intervalle beantworten unterschiedliche Fragen: Die einen zeigen konkrete Treffer, die anderen deren zeitliche Zusammenführung.

    -- ✓ Richtig! Beim Zusammenfügen werden zeitliche Abstände und Toleranzen berücksichtigt. Ein resultierendes Intervall ist deshalb nicht einfach eine Liste unabhängig bestätigter Einzelbilder.
[x] Die EAF-Datei kann helfen, die zeitlichen Annotationen gemeinsam mit dem passenden Video zu sichten und zu korrigieren.

    -- ✓ Richtig! Der Export überführt die Ergebnisse in eine für Annotationsprogramme geeignete zeitliche Form. Eine erfolgreiche Dateiübernahme ersetzt jedoch nicht die Sichtprüfung.
[ ] Eine fehlerfreie Programmausführung bestätigt zugleich, dass die markierten Einstellungsgrenzen und Figuren sachlich richtig sind.

    -- × Nicht korrekt. Technische Ausführbarkeit und inhaltliche Erkennungsqualität sind unterschiedliche Kriterien. Ein lauffähiger Prozess kann gültig formatierte, aber fehlerhafte Annotationen exportieren.
[x] Eine auf ganze Einstellungen erweiterte Figurenannotation darf nicht ohne Weiteres als sekundengenaue, durchgehende Sichtbarkeit interpretiert werden.

    -- ✓ Richtig! Die zusätzlichen einstellungsbezogenen Spuren übernehmen die vollständigen Einstellungen, die sich mit Figurenintervallen überschneiden. Das ist eine andere zeitliche Aussage als ein direkter Treffer in einem einzelnen Frame.


### Frage 7

**Für einen Test wurden bereits folgende Werte ermittelt. „Gesichtswert“ bezeichnet den Wert der Gesichtslokalisierung, „Ähnlichkeit“ den besten Vergleichswert mit den ausgewählten Figuren.**

| Bild | Gesichtswert | Ähnlichkeit |
| --- | --- | --- |
| A | 0,86 | 0,54 |
| B | 0,72 | 0,82 |
| C | 0,92 | 0,76 |

Zunächst gelten eine Gesichtsgrenze von 0,80 und eine Zuordnungsgrenze von 0,60. Ein Wert wird angenommen, wenn er die jeweilige Grenze erreicht oder übersteigt. Dann wird ausschließlich die Gesichtsgrenze auf 0,70 gesenkt. Die Tabelle bleibt unverändert. Welche Aussage stimmt?

[ ] Zunächst werden A und C zugeordnet; danach zusätzlich B, weil für die Zuordnung der höhere der beiden Werte genügt.

    -- × Nicht korrekt. Beide Prüfungen erfüllen unterschiedliche Voraussetzungen. A scheitert an der Zuordnungsgrenze, obwohl sein Gesichtswert hoch genug ist.
[x] Zunächst wird nur C zugeordnet; nach der Änderung werden B und C zugeordnet.

    -- ✓ Richtig! A scheitert weiterhin an der Ähnlichkeit von 0,54. B scheitert zuerst an der Gesichtsgrenze von 0,80, besteht aber die abgesenkte Grenze von 0,70 und die unveränderte Zuordnungsgrenze. C erfüllt beide Voraussetzungen in beiden Varianten.
[ ] Zunächst wird nur C zugeordnet; nach der Änderung werden A, B und C zugeordnet, weil die erste Grenze auch die zweite ersetzt.

    -- × Nicht korrekt. Das Senken der Gesichtsgrenze hebt die Prüfung der Figurenzuordnung nicht auf. A bleibt wegen seines zu geringen Ähnlichkeitswerts ausgeschlossen.
[ ] Die Zuordnung bleibt unverändert, weil allein die Ähnlichkeit entscheidet und die Gesichtsgrenze nur die spätere Darstellung beeinflusst.

    -- × Nicht korrekt. Eine nicht angenommene Gesichtsdetektion wird nicht einfach aufgrund eines guten Identitätsvergleichs zum regulären Treffer. Beide Schwellenwerte wirken an unterschiedlichen Stellen des Verfahrens.

### Frage 8

**Das Team hat eigene Videos bereits lokal im Ordner `eigene_videos` abgelegt. Ergebnisse sollen nach `ergebnisse_projekt`. Die Testdateien sollen nicht zusätzlich heruntergeladen werden. Welcher Parameterblock passt dazu?**

Option A:

```python
VIDEO_PATH = "eigene_videos"
EXPORT_PATH = "ergebnisse_projekt"
DOWNLOAD_TESTFILES = False
```

Option B:

```python
VIDEO_PATH = "ergebnisse_projekt"
EXPORT_PATH = "eigene_videos"
DOWNLOAD_TESTFILES = False
```

Option C:

```python
VIDEO_PATH = "eigene_videos"
EXPORT_PATH = "ergebnisse_projekt"
DOWNLOAD_TESTFILES = True
```

Option D:

```python
VIDEO_PATH = "eigene_videos"
EXPORT_PATH = "ergebnisse_projekt"
THRESHOLD = 0.0
```

[x] Option A

    -- ✓ Richtig! Eingabe- und Ausgabeordner werden passend zugeordnet; der Testdownload wird ausgeschaltet. Die eigenen Dateien müssen tatsächlich im eingestellten Eingabeordner liegen. Die Parameterzelle und die darauf aufbauenden Verarbeitungsschritte müssen mit den neuen Einstellungen ausgeführt werden.
[ ] Option B

    -- × Nicht korrekt. Die beiden Ordnerrollen sind vertauscht. Das Skript würde seine Eingaben am vorgesehenen Ausgabeort suchen und Ergebnisse am vorgesehenen Eingabeort ablegen.
[ ] Option C

    -- × Nicht korrekt. Die Pfade passen, der Testdownload bleibt jedoch eingeschaltet. Das erfüllt die Anforderung nicht, ausschließlich die bereitliegenden eigenen Videos ohne zusätzlichen Testdownload zu verwenden.
[ ] Option D

    -- × Nicht korrekt. Ein Schwellenwert steuert die Trefferentscheidung, nicht den Download. Ohne Änderung der Download-Einstellung ist die Anforderung nicht erfüllt; außerdem ist die Grenze 0,0 nicht durch das Projektziel begründet.

### Frage 9

**Zwei eigene Videos mit jeweils anderen Hauptfiguren sollen im unveränderten Figurennotebook verarbeitet werden. Welche Ablage passt zu dessen Einleseverfahren?**

[ ] Beide Videos direkt in den Eingabeordner legen und alle Referenzbilder in einem gemeinsamen Unterordner sammeln.

    -- × Nicht korrekt. Das Figurennotebook durchsucht die direkten Unterordner als Untersuchungseinheiten. Es verknüpft nicht automatisch Videos auf der obersten Ebene mit einem getrennten gemeinsamen Referenzordner.
[ ] Alle Videos und Bilder gemeinsam in einen Unterordner legen, weil die unterschiedlichen Dateiendungen eine vollständige Zuordnung sicherstellen.

    -- × Nicht korrekt. Der Code unterstützt dort nur ein Video pro Unterordner. Die Dateiendung erklärt zudem nicht, welche Referenzbilder zu welchem Video gehören.
[x] Für jedes Video einen direkten Unterordner anlegen und darin das Video, seine Referenzbilder und gegebenenfalls seine passende Einstellungs-CSV gemeinsam ablegen.

    -- ✓ Richtig! So entspricht jede Eingabeeinheit dem Einleseverfahren. Die Referenzen und optionalen Einstellungsdaten sind dem jeweiligen Video zugeordnet.
[ ] Für jede Figur einen eigenen Unterordner anlegen und ihre Videos nochmals in tieferen Unterordnern ablegen.

    -- × Nicht korrekt. Das unveränderte Notebook sucht nicht beliebig tief nach solchen Einheiten. Die beschriebene Organisation folgt außerdem Figuren statt der vorgesehenen Einheit „ein Video mit seinen Referenzen“.

### Frage 10

**Bei einem Film über eine Musikschule vermisst ein Team kurze Auftritte in den Einzelbildtreffern. Die zeitlichen Intervalle wirken dagegen sehr geschlossen, weil eine große Lückentoleranz gewählt wurde. Welche Anpassung geht am gezieltesten auf beide Beobachtungen ein?**

[ ] Die Lückentoleranz weiter erhöhen und die Bildauswahl unverändert lassen, damit mehr Einzelbilder tatsächlich erkannt werden.

    -- × Nicht korrekt. Eine größere Toleranz verbindet vorhandene Treffer über größere Lücken. Sie führt die Gesichtsanalyse nicht auf zuvor ausgelassenen Bildern aus und erzeugt daher keine zusätzlichen direkten Einzelbildbelege.
[x] Weniger Bilder überspringen und die Lückentoleranz gesondert prüfen, damit kurze Auftritte eher analysiert und unbelegte Zwischenräume nicht vorschnell überbrückt werden.

    -- ✓ Richtig! `SKIP_FRAMES` verändert, welche Bilder analysiert werden. `TOLERANCE_FRAMES` steuert dagegen die zeitliche Zusammenführung vorhandener Treffer. Die Einstellungen müssen nach ihrer unterschiedlichen Wirkung beurteilt werden.
[ ] Nur die Lückentoleranz senken; das macht die Bildauswahl dichter und behebt damit beide Probleme zugleich.

    -- × Nicht korrekt. Eine kleinere Toleranz kann Intervalle stärker aufteilen, analysiert aber keine zusätzlichen Frames. Für verpasste Kurzauftritte muss auch die Bildauswahl betrachtet werden.
[ ] Mehr Frames überspringen und zugleich die Figurenzuordnung strenger einstellen, um fehlende Kurzauftritte aus den längeren Intervallen abzuleiten.

    -- × Nicht korrekt. Weniger analysierte Bilder und eine strengere Annahmeregel liefern nicht die fehlenden Bildbelege. Lange Intervalle erlauben keine nachträgliche Rekonstruktion ausgelassener Erkennungen.

### Frage 11

**Ein Team ändert den Schwellenwert für Einstellungsübergänge in der Parameterzelle des Notebooks. Es führt danach nur die Exportzelle aus. Die Dateien enthalten dieselben Einstellungsgrenzen wie zuvor. Was ist die beste Erklärung und Reaktion?**

[ ] Der neue Wert wird erst berücksichtigt, wenn das Erkennungsmodell mit dem gesamten Film neu trainiert wurde.

    -- × Nicht korrekt. Die Anpassung der Treffergrenze erfordert kein neues Training. Entscheidend ist, dass die Verarbeitungsschritte mit der geänderten Einstellung tatsächlich ausgeführt werden.
[ ] Der Export bestimmt die Einstellungsgrenzen; deshalb müsste nur der Dateiname zusätzlich geändert werden.

    -- × Nicht korrekt. Das Umbenennen verändert weder Modellwerte noch Segmentgrenzen. Der Export schreibt bereits erzeugte Ergebnisse in Dateien.
[x] Bereits berechnete Segmentdaten werden erneut exportiert; die Parameterzelle und die davon abhängige Segmenterzeugung sowie Aufbereitung müssen erneut ausgeführt werden.

    -- ✓ Richtig! Das Bearbeiten einer Zelle ändert noch nicht den Zustand der laufenden Sitzung. Auch nach Ausführung der Parameterzelle entstehen neue Segmentdaten erst durch erneute Ausführung der darauf aufbauenden Verarbeitung. Ein neuer Export allein berechnet sie nicht neu.
[ ] Gleiche Grenzen zeigen, dass der neue Schwellenwert grundsätzlich wirkungslos ist und aus dem Skript entfernt werden kann.

    -- × Nicht korrekt. Hier wurde seine Anwendung auf die Daten gar nicht erneut ausgeführt. Selbst bei korrekter Neuberechnung könnten zwei Grenzen einmal dieselbe Segmentierung ergeben; daraus folgte ebenfalls keine allgemeine Wirkungslosigkeit.

### Frage 12

**Eine zwölf Sekunden lange Einstellung zeigt die Figur „Lea“ nur in einem kurzen Ausschnitt. Das Verfahren erzeugt dafür ein Figurenintervall von zwei Sekunden. In der zusätzlichen, auf Einstellungen erweiterten Spur ist jedoch die gesamte zwölfsekündige Einstellung markiert. Wie ist das zu verstehen?**

[ ] Die längere Markierung korrigiert automatisch die kürzere und bestätigt, dass Lea während aller zwölf Sekunden sichtbar war.

    -- × Nicht korrekt. Die zusätzliche Spur ist keine automatische Wahrheitsprüfung. Sie übernimmt die ganze Einstellung aufgrund einer Überschneidung mit einem Figurenintervall.
[ ] Der Widerspruch beweist, dass die Einstellungsgrenzen falsch sind; Figurenintervalle und Einstellungen müssen gleich lang sein.

    -- × Nicht korrekt. Eine Figur kann nur in einem Teil einer Einstellung sichtbar sein. Deshalb müssen Figurenauftritt und Einstellungsdauer nicht übereinstimmen.
[ ] Die zwei Sekunden können ignoriert werden, weil für die Berechnung exakter Leinwandzeit stets die längere der beiden Spuren maßgeblich ist.

    -- × Nicht korrekt. Diese Regel würde eine auf ganze Einstellungen ausgedehnte Markierung mit durchgehender Sichtbarkeit verwechseln. Für präzise Zeitangaben müssen die Erkennungs- und Zusammenführungsregeln berücksichtigt und die Ergebnisse überprüft werden.
[x] Die längere Markierung bedeutet, dass ein Figurenintervall diese Einstellung überschneidet; sie belegt keine durchgehende Sichtbarkeit.

    -- ✓ Richtig! Die beiden Spuren arbeiten auf unterschiedlichen zeitlichen Ebenen. Auch das kürzere Intervall muss geprüft werden, weil es aus Treffern unter Berücksichtigung der gewählten Bildauswahl und Lückentoleranz entsteht.

### Frage 13

**Ein eigenes Video hat 25 Frames pro Sekunde. Eine erkannte Einstellung beginnt bei Frame 100 und endet bei Frame 149. Beide Frames gehören zur Einstellung. Welche Umsetzung erhält bei einer Anpassung des Skripts die richtige Dauer?**

[x] `dauer = (149 - 100 + 1) / 25` ergibt 2,00 Sekunden.

    -- ✓ Richtig! Bei eingeschlossenem Start- und Endframe werden 50 Frames gezählt. Die Division durch die individuelle Bildrate überführt die Anzahl in eine Dauer. Das entspricht der Berechnung im Einstellungsskript.
[ ] `dauer = (149 - 100) / 25` ergibt 1,96 Sekunden und berücksichtigt beide Randframes bereits vollständig.

    -- × Nicht korrekt. Die Differenz allein zählt bei dieser Konvention einen Frame zu wenig. Genau deshalb ergänzt das Skript bei der Dauerberechnung eine Eins.
[ ] `dauer = (149 + 1) / 25` ergibt 6,00 Sekunden und ist die Dauer der Einstellung.

    -- × Nicht korrekt. Dieser Wert beschreibt die Position unmittelbar nach dem letzten Frame relativ zum Videobeginn. Für die Dauer muss auch die Startposition berücksichtigt werden.
[ ] `dauer = (149 - 100 + 1) / 30` ist vorzuziehen, damit Videos mit unterschiedlichen Bildraten vergleichbar werden.

    -- × Nicht korrekt. Eine erfundene einheitliche Bildrate verfälscht die Dauer. Vergleichbare Sekundenwerte entstehen gerade durch die Umrechnung mit der tatsächlichen Bildrate jedes Videos.



### Frage 14

**Ordnen Sie jeder Situation den unmittelbar beschriebenen Schritt zu. Jede Option darf höchstens einmal verwendet werden. Zwei Optionen bleiben übrig.**

Optionen:

- A: Detection — Gesichter im Bild lokalisieren.
- B: Alignment — ein erkanntes Gesicht für den Vergleich ausrichten und zuschneiden.
- C: Representation — ein Gesicht in eine numerische Merkmalsrepräsentation überführen.
- D: Recognition — die Repräsentation mit Vergleichsrepräsentationen abgleichen und gegebenenfalls einer Figur zuordnen.
- E: Zeitliche Zusammenführung — vorhandene Treffer zu längeren Intervallen verbinden.
- F: Einstellungserkennung — den Film anhand von Einstellungsübergängen gliedern.

Situationen:

1. In einem ausgewählten Frame wird ein Rahmen um ein Gesicht bestimmt, ohne ihm bereits einen Figurennamen zuzuweisen.
2. Der erkannte Gesichtsbereich wird vor der weiteren Verarbeitung begradigt.
3. Aus dem Gesicht entsteht eine Zahlenrepräsentation, die seine Merkmale für spätere Vergleiche beschreibt.
4. Diese Repräsentation wird mit den vorbereiteten Referenzen verglichen; bei hinreichender Ähnlichkeit wird der Name einer gesuchten Figur zugewiesen.

Ihre Zuordnung: 1 → ___ | 2 → ___ | 3 → ___ | 4 → ___

Lösungen und Rückmeldungen:

- 1 → A: ✓ Richtig! Der Gesichtsrahmen lokalisiert ein Gesicht. Seine Identität ist damit noch nicht bestimmt.
  - Bei anderer Zuordnung: × Nicht korrekt. Die Situation beschreibt noch keine Ausrichtung, Merkmalsdarstellung oder Identitätszuordnung. Zeitintervalle und Einstellungsgrenzen stehen ebenfalls nicht im Mittelpunkt.
- 2 → B: ✓ Richtig! Das Begradigen erhöht die Vergleichbarkeit des Gesichts für nachfolgende Schritte. Dass Bibliotheken dies intern erledigen können, ändert seine Funktion nicht.
  - Bei anderer Zuordnung: × Nicht korrekt. Das Gesicht ist schon gefunden; es wird jetzt geometrisch vorbereitet. Noch werden weder Vergleichsrepräsentationen abgeglichen noch zeitliche Daten zusammengeführt.
- 3 → C: ✓ Richtig! Die numerische Repräsentation ist das Embedding. Seine Erstellung ist von der späteren Zuordnung zu einer Figur zu unterscheiden.
  - Bei anderer Zuordnung: × Nicht korrekt. Eine Zahlenrepräsentation benennt noch keine Person und erzeugt keine zeitlichen Intervalle. Ihre Herstellung ist der spezifische Schritt Representation.
- 4 → D: ✓ Richtig! Der Vergleich mit den Referenzen ermöglicht eine Zuordnung. Der Schwellenwert entscheidet, ob die Ähnlichkeit dafür ausreicht.
  - Bei anderer Zuordnung: × Nicht korrekt. Lokalisierung, Ausrichtung und Repräsentation sind vorausgegangen. Beschrieben wird jetzt die Zuordnung anhand des Vergleichs, nicht eine Filmsegmentierung.
- E bleibt übrig: × Nicht korrekt. Keine Situation verbindet mehrere zeitlich verteilte Treffer zu einem Intervall. Dieser spätere Verarbeitungsschritt ist von den beschriebenen Schritten am Gesicht zu unterscheiden.
- F bleibt übrig: × Nicht korrekt. Keine Situation bestimmt Schnitte oder andere Einstellungsübergänge. Die Aussagen betreffen die Gesichtsanalyse.

### Frage 15

**Ordnen Sie jedem Anpassungsziel die unmittelbar passende Einstellung zu. Jede Option darf höchstens einmal verwendet werden. Zwei Optionen bleiben übrig. Die Zuordnung benennt die betroffene Stellschraube, nicht einen allgemein optimalen Zahlenwert.**

Optionen:

- A: `VIDEO_PATH` — Suchort der Eingabedateien.
- B: `EXPORT_PATH` — Speicherort der Ergebnisse.
- C: `FACE_DETECTION_THRESHOLD` — Annahmegrenze für ein erkanntes Gesicht.
- D: `CHARACTER_RECOGNITION_THRESHOLD` — Annahmegrenze für die Zuordnung zu einer Referenzfigur.
- E: `SKIP_FRAMES` — Zahl der zwischen zwei analysierten Bildern übersprungenen Frames.
- F: `TOLERANCE_FRAMES` — zusätzliche Lückentoleranz beim Verbinden vorhandener Treffer.

Anpassungsziele:

1. Dasselbe Video soll an mehr Bildpositionen analysiert werden, um kurze Auftritte besser zu erfassen.
2. Vorhandene Treffer einer Figur sollen über weniger große zusätzliche Lücken hinweg zu Intervallen verbunden werden.
3. Ein im Bild bereits angenommenes Gesicht soll nur bei stärkerer Ähnlichkeit zu einer Referenzfigur deren Namen erhalten.
4. Die eigenen Dateien liegen an einem anderen Ort; der Suchort soll angepasst werden, ohne die Erkennungsregeln zu verändern.

Ihre Zuordnung: 1 → ___ | 2 → ___ | 3 → ___ | 4 → ___

Lösungen und Rückmeldungen:

- 1 → E: ✓ Richtig! Ein geringerer Wert für `SKIP_FRAMES` führt zu einer dichteren Bildauswahl. Er ist mit höherem Analyseaufwand verbunden und muss zur benötigten zeitlichen Genauigkeit passen.
  - Bei anderer Zuordnung: × Nicht korrekt. Annahmegrenzen bewerten vorhandene Modellwerte, eine Lückentoleranz verbindet vorhandene Treffer und Pfade betreffen Dateiorte. Keine dieser anderen Einstellungen analysiert zusätzliche Bildpositionen.
- 2 → F: ✓ Richtig! Die zusätzliche Lückentoleranz steuert die Zusammenführung. Ein kleinerer Wert schränkt diese Überbrückung ein, ohne selbst neue Einzelbildtreffer zu erzeugen.
  - Bei anderer Zuordnung: × Nicht korrekt. Gefragt ist nach dem Verbinden bereits vorliegender Treffer, nicht nach ihrer Erkennung, der Bildauswahl oder einem Dateipfad.
- 3 → D: ✓ Richtig! Der Vergleich mit den Referenzen betrifft die Figurenzuordnung. Hier ist deren Schwellenwert betroffen, nicht die vorgelagerte Annahme eines Gesichts.
  - Bei anderer Zuordnung: × Nicht korrekt. Ein erkanntes Gesicht ist noch keine identifizierte Figur. Die anderen Optionen steuern entweder den ersten Erkennungsschritt, die zeitliche Verarbeitung oder die Dateiablage.
- 4 → A: ✓ Richtig! Der Eingabepfad legt fest, wo das Notebook nach Analysematerial sucht. Eine Änderung daran muss keine Änderung an den Schwellenwerten bedeuten.
  - Bei anderer Zuordnung: × Nicht korrekt. Der Exportpfad steuert die Ausgabe; Schwellenwerte und zeitliche Parameter beheben keinen falsch eingestellten Eingabeort.
- B bleibt übrig: × Nicht korrekt. Kein Ziel verlangt einen anderen Ergebnisordner. Ein geänderter Exportpfad würde insbesondere weder die Eingabesuche noch die Trefferverarbeitung verändern.
- C bleibt übrig: × Nicht korrekt. Kein Ziel verlangt eine andere Annahmegrenze für das Vorliegen eines Gesichts. Ziel 3 betrifft ausdrücklich ein bereits angenommenes Gesicht und dessen Identitätszuordnung.



### Frage 16: Wahr oder Falsch

**„Ein Modellpaket mit guter GPU-Leistung ist allein deshalb auch die zweckmäßigste Wahl für die Ausführung auf jedem Rechner ohne GPU.“**

[ ] Wahr

    -- × Nicht korrekt. Die Eignung umfasst auch die praktische Ausführung. Das Figurennotebook berücksichtigt die verfügbare Hardware und bereitet je nach Ausführungsvariante unterschiedliche Pakete vor. Gute GPU-Ergebnisse begründen keine pauschale Empfehlung für jede CPU-Umgebung.
[x] Falsch

    -- ✓ Richtig! Modellwahl, verfügbare Ausführungsumgebung und Laufzeit müssen zusammen betrachtet werden. Auch die tatsächlich verwendete Hardware sollte in der Ausgabe kontrolliert werden; eine Modellbezeichnung allein belegt keine Beschleunigung.


**„Wenn eine Figur im Bild ausschließlich von hinten sichtbar ist, beweist das Fehlen eines Gesichtstreffers nicht, dass die Figur abwesend ist.“**

[x] Wahr

    -- ✓ Richtig! Das beschriebene Verfahren erkennt Figuren anhand von Gesichtern. Ein nicht sichtbares Gesicht begrenzt daher die Erkennung, auch wenn ein Mensch die Figur im filmischen Zusammenhang erkennen kann.
[ ] Falsch

    -- × Nicht korrekt. Die Methode erfasst nicht jede Form von Figurenpräsenz. Eine fehlende Gesichtserkennung darf bei dieser Grundlage nicht unmittelbar als sichere Abwesenheit interpretiert werden.


**„Wenn ein niedrigerer Schwellenwert einen übersehenen Übergang in einem Film ergänzt, sollte derselbe Wert ungeprüft für die übrigen Filme des Korpus übernommen werden.“**

[ ] Wahr

    -- × Nicht korrekt. Eine Verbesserung an einer Stelle kann mit neuen Fehlmarkierungen an anderer Stelle einhergehen. Die Datensichtung zeigt, dass ein für einen Film geeigneter Wert bei anderem Material problematisch sein kann.
[x] Falsch

    -- ✓ Richtig! Änderungen müssen erneut am Material überprüft werden. Auch innerhalb eines Films sollte nicht nur die zuvor fehlerhafte Stelle, sondern die Wirkung auf weitere Annotationen betrachtet werden. Bei Vergleichen sind die Entscheidungen und relevante Inkonsistenzen offenzulegen beziehungsweise zu bereinigen.


**„Das Erstellen eines gemittelten Vergleichs-Embeddings aus mehreren geeigneten Referenzbildern ist im vorgestellten Notebook nicht dasselbe wie ein vollständiges Neutraining des Gesichtsanalysemodells.“**

[x] Wahr

    -- ✓ Richtig! Ein vorhandenes Modell erzeugt Repräsentationen aus den Bildern. Diese werden pro Figur zu einer Vergleichsgrundlage zusammengefasst. Dadurch wird die Referenzbasis angepasst, nicht das gesamte Modell neu geschult.
[ ] Falsch

    -- × Nicht korrekt. Jede Verarbeitung neuer Bilder als Training zu bezeichnen würde Anwendung und Schulung verwechseln. Hier werden mit dem bestehenden Modell neue Vergleichsrepräsentationen erstellt.


**„Beim erneuten Export mit denselben erzeugten Dateinamen können frühere Ergebnisse überschrieben werden; für einen verlässlichen Vergleich reicht es daher nicht, sich allein auf das wiederholte Ausführen der Exportzelle zu verlassen.“**

[x] Wahr

    -- ✓ Richtig! Die beschriebenen Exporte ersetzen vorhandene gleichnamige Dateien. Insbesondere die Figurenexporte unterscheiden nicht alle Parameterkombinationen im Dateinamen. Getrennte Ergebnisordner oder gesicherte Vergleichsstände und die zugehörigen Metadaten helfen, Läufe nachvollziehbar zu erhalten.
[ ] Falsch

    -- × Nicht korrekt. Ein erneuter Export legt nicht automatisch ein unveränderliches Archiv aller früheren Läufe an. Die Speicherung muss bei der Anpassung des Projekts bewusst berücksichtigt werden.


### Frage 17

**Szenario: Sie beraten ein Projekt, das eine eigene Sammlung von Filmen über Küstenorte annotieren möchte. Drei Arbeitsgruppen haben unterschiedliche Anforderungen und Probleme:**

- (a) Einstellungslängen vergleichen: Die erste Gruppe benötigt zeitliche Einstellungsdaten für mehrere eigene Videos. Die Dateien liegen verteilt in Unterordnern; zwei Videos tragen denselben Dateinamen. Bei einem ersten Test werden Übergänge zwischen ähnlichen Bildern übersehen. Ein niedrigerer Schwellenwert ergänzt diese Übergänge, erzeugt aber auch neue Markierungen bei starken Lichtänderungen innerhalb einer Einstellung.
- (b) Ausgewählte Figuren suchen: Die zweite Gruppe möchte drei vorher festgelegte Figuren in einem Film finden. Als Referenzen hat sie Gruppenbilder und mehrere unscharfe Aufnahmen vorbereitet. Im Analysevideo treten einige Figuren nur sehr kurz auf oder sind von hinten sichtbar. Aus Zeitgründen sollen viele Frames übersprungen werden.
- (c) Ergebnisse bewerten und vergleichen: Die dritte Gruppe sichtet die erzeugten EAF-Dateien. In der auf ganze Einstellungen erweiterten Figurenspur erscheinen längere Zeiträume als in den Figurenintervallen. Außerdem soll das Team verschiedene Parameterkombinationen vergleichen, exportiert bisher aber immer in denselben Ordner unter denselben Dateinamen.

Beschreiben Sie für jede Gruppe, welches Vorgehen Sie empfehlen. Begründen Sie Ihre Entscheidung anhand der Aufgabe, der benötigten Eingaben und der Aussagekraft der Ergebnisse — nicht allein anhand des Filmthemas.

Gehen Sie auf folgende Punkte ein:

1. Welche Modelle oder Verarbeitungsschritte passen zur jeweiligen Aufgabe?
2. Welche Anpassungen an Eingaben, Parametern oder Projektablage sind erforderlich?
3. Wie sollten Schwellenwerte und zeitliche Einstellungen geprüft werden?
4. Was muss bei der Sichtung am Video kontrolliert werden, und welche Aussagen lassen sich aus den Daten nicht ohne Weiteres ableiten?

<details>
<summary>Reflexionshinweise</summary>

#### Musterlösung

Die folgende Antwort zeigt einen geeigneten Lösungsweg. Andere Vorschläge sind möglich, wenn Aufgabe, Eingaben, Verarbeitung und Schlussfolgerungen zusammenpassen.

(a) Einstellungslängen vergleichen:

- Modellauswahl: Ein Verfahren für Einstellungsübergänge wie TransNetV2 passt zur Aufgabe. Aus den Grenzen werden mit der jeweiligen Bildrate Einstellungsdauern berechnet. Das Verfahren kann sowohl Übergänge übersehen als auch Veränderungen innerhalb einer Einstellung fälschlich markieren.
- Projektanpassung: Eingabe- und Exportpfad müssen auf die eigenen Dateien eingestellt werden. Bei bereits lokal vorhandenen eigenen Dateien kann der Testdownload ausgeschaltet werden. Das Einstellungsskript durchsucht auch Unterordner; die Videonamen müssen jedoch über diese Ordner hinweg eindeutig sein. Die doppelte Benennung sollte vor der Verarbeitung bereinigt werden.
- Schwellenwertprüfung: Der niedrigere Schwellenwert löst nicht alle Probleme zugleich. Die Gruppe sollte ergänzte Übergänge und neu entstandene Fehlmarkierungen am Film prüfen. Ein Wert kann für einen Film besser passen als für einen anderen. Parameterzelle und abhängige Verarbeitungsschritte müssen nach Änderungen erneut ausgeführt werden.
- Qualitätsbeurteilung: Die Grenzen müssen mit dem Material synchron verglichen und gegebenenfalls korrigiert werden. Für vergleichende Auswertungen sollte außerdem auf eine konsistente Behandlung etwa von Vor- und Abspann geachtet werden. Hohe Vorhersagewerte oder ein erfolgreicher Export allein belegen keine fehlerfreie Segmentierung.

(b) Ausgewählte Figuren suchen:

- Modellauswahl: Benötigt werden Gesichtslokalisierung, Aufbereitung der Gesichter, Embedding-Erstellung und Vergleich mit den Referenzen. Ein Modellpaket wie InsightFace kann die spezialisierten Komponenten bereitstellen. Seine praktische Ausführung muss zur verfügbaren Hardware passen.
- Referenzen und Ablage: Pro Video wird ein direkter Unterordner mit dem Video, den zugehörigen Referenzbildern und gegebenenfalls der passenden Einstellungs-CSV vorbereitet. Die Referenzen sollten jeweils genau ein gut erkennbares Gesicht der gemeinten Figur enthalten. Gruppenbilder können zugeschnitten werden; ungeeignete unscharfe Bilder sollten ersetzt werden. Mehrere geeignete Perspektiven und passende Dateinamen unterstützen die Erstellung der Vergleichs-Embeddings. Ihre Erzeugung ist keine vollständige Neuschulung des Modells.
- Schwellenwerte und Bildauswahl: Die Grenze für das Vorliegen eines Gesichts und die Grenze für die Figurenzuordnung müssen getrennt betrachtet werden. Ein Senken kann zusätzliche Treffer, aber auch Verwechslungen erzeugen. Wegen der kurzen Auftritte sollte geprüft werden, ob weniger Frames übersprungen werden müssen. Eine höhere Lückentoleranz ersetzt keine dichtere Bildanalyse.
- Grenzen und Prüfung: Ein Verfahren auf Gesichtsbasis kann die Figur nicht anhand eines unsichtbaren Gesichts erkennen. Fehlende Treffer bei Rückenansichten belegen daher keine Abwesenheit. Auch schlecht beleuchtete, verdeckte oder sehr kleine Gesichter und mögliche Verwechslungen sind bei der Sichtung zu berücksichtigen.

(c) Ergebnisse bewerten und vergleichen:

- Bedeutung der Spuren: Einzelbildtreffer, daraus zusammengeführte Intervalle und auf ganze Einstellungen erweiterte Spuren haben verschiedene zeitliche Bedeutungen. Die längere einstellungsbezogene Markierung entsteht durch eine Überschneidung und beweist keine durchgehende Sichtbarkeit während der ganzen Einstellung.
- Sichtung: Die Gruppe sollte die Annotationen am passenden Video prüfen und untersuchen, wie Bildauswahl, Lückentoleranz, Fehlzuordnungen und Einstellungsgrenzen die resultierenden Zeiträume beeinflussen. Eine Lücke ohne Treffer kann sowohl eine Abwesenheit als auch eine Erkennungsschwierigkeit oder eine ausgelassene Bildposition widerspiegeln.
- Vergleichsläufe: Vor neuen Exporten sollten vorhandene Ergebnisse gesichert oder getrennte Exportordner für die getesteten Kombinationen eingestellt werden. Die zugehörigen Parameter und Analysemetadaten müssen erhalten bleiben. Ein wiederholter Export unter denselben Namen kann ältere Ergebnisse überschreiben.
- Qualitätsurteil: Eine längere oder kürzere Trefferliste ist nicht für sich allein besser. Entscheidend ist, welche tatsächlichen Auftritte und Übergänge korrekt erfasst oder verpasst werden und ob die zeitliche Zusammenfassung zur beabsichtigten Auswertung passt.

#### Zentrale Erkenntnis

Ein geeigneter Annotations-Workflow verbindet passende Modelle mit eindeutigen Eingaben, wirksam angewendeten Parametern und einer nachvollziehbaren Ergebnisprüfung. Schwellenwerte, Bildauswahl und zeitliche Zusammenführung lösen unterschiedliche Aufgaben. Ihre Anpassung muss am Filmmaterial kontrolliert werden; weder hohe Modellwerte noch lange Annotationsintervalle oder erfolgreiche Exporte ersetzen diese Prüfung.

</details>

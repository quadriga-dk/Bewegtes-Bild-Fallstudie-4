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

**Ein Team untersucht digitalisierte Filme über Handwerksbetriebe. Ein Programm markiert Bilder, in denen vermutlich eine Werkzeugkiste vorkommt. Welche Beschreibung erklärt den Erkennungsprozess am besten?**

[ ] Das Programm übersetzt zunächst die Handlung des Films in eine Inhaltsbeschreibung und leitet daraus ab, welche Gegenstände im Bild sein müssen. 

    -- × Nicht korrekt. Die beschriebene visuelle Erkennung beruht auf der Verarbeitung von Bildinformationen. Eine aus der Handlung abgeleitete Erwartung ersetzt nicht die Erkennung von Merkmalen im Bild.

[x] Das Programm verarbeitet numerisch beschreibbare Bildmerkmale und ermittelt mit einem passenden Modell Hinweise auf das gesuchte Objekt. 

    -- ✓ Richtig! Informationen etwa zu Formen, Helligkeit und Farbe können als Zahlen verarbeitet werden. Die Erkennung beruht auf Mustern in diesen Daten und ist nicht mit einer menschlichen Wahrnehmung des gesamten Filmzusammenhangs gleichzusetzen.

[ ] Das Programm übernimmt die Bedeutung des Gegenstands aus seiner Objektbezeichnung; mit dem Namen „Werkzeugkiste“ ist damit auch seine Funktion in der Szene erfasst. 

    -- × Nicht korrekt. Eine Objektbezeichnung beschreibt eine ausgewählte Eigenschaft. Sie erklärt noch nicht, welche Rolle der Gegenstand im konkreten filmischen Zusammenhang spielt.

[ ] Das Programm erfasst zunächst alle Informationen des Bildes vollständig; das Forschungsteam wählt erst nachträglich aus, welche davon in die Annotation eingehen. 

    -- × Nicht korrekt. Die Auswahl von Aufgaben und verfügbaren Modellen begrenzt bereits, welche Informationen extrahiert werden. Auch eine umfangreiche Annotation bildet das Originalbild nicht vollständig ab.

### Frage 2

**Ein Team besitzt eine genaue Anleitung zur Verarbeitung von Filmbildern und ein bereits trainiertes Werkzeug zur Gesichtserkennung. Welche Unterscheidung ist sachgerecht?**

[ ] Die Anleitung ist das Modell; das trainierte Werkzeug ist der Algorithmus, weil es die Berechnung tatsächlich ausführt.  

    -- × Nicht korrekt. Hier werden die Begriffe vertauscht. Die genaue Abfolge von Verarbeitungsschritten beschreibt einen Algorithmus. Das trainierte Werkzeug wird als Modell angewendet, um aus Eingaben bestimmte Ausgaben zu erzeugen.

[ ] Beide Begriffe bezeichnen dieselbe Sache; der Unterschied besteht nur darin, ob die Verarbeitung schriftlich beschrieben oder ausgeführt wird.  

    -- × Nicht korrekt. Beschreibung und Ausführung sind nicht die entscheidende Unterscheidung. Ein Modell entsteht durch einen Trainingsprozess mithilfe von Algorithmen. Algorithmus und Modell hängen zusammen, sind aber nicht gleichbedeutend.

[x] Die Anleitung beschreibt einen Algorithmus; das trainierte Werkzeug ist ein Modell, dessen Entstehung und Anwendung auf Algorithmen beruhen.  

    -- ✓ Richtig! Ein Algorithmus legt Verarbeitungsschritte fest. Ein Modell wird mithilfe von Trainingsdaten und Algorithmen entwickelt und anschließend für eine bestimmte Erkennungsaufgabe eingesetzt.

[ ] Das trainierte Werkzeug ist erst dann ein Modell, wenn es bei jedem neuen Film erneut trainiert wird.  

    -- × Nicht korrekt. Ein bereits trainiertes Modell kann auf neue Eingaben angewendet werden. Die Anwendung eines Modells muss von einem neuen Trainingsprozess unterschieden werden.


### Frage 3

**Ein Deep-Learning-Modell erkennt Gesichter in einem Film überzeugend. Eine Projektmitarbeiterin möchte daraus schließen, dass sich jede Entscheidung leicht in verständliche Regeln zerlegen lässt. Wie beurteilen Sie dies?**

[x] Die gute Erkennungsleistung allein belegt keine leicht verständliche Erklärung der einzelnen Entscheidungen.  

    -- ✓ Richtig! Deep Learning verarbeitet gelernte Merkmale über mehrere Ebenen. Gerade diese geschichtete Verarbeitung kann die Nachvollziehbarkeit erschweren, auch wenn das Modell gute Ergebnisse erzielt.

[ ] Die Schlussfolgerung ist berechtigt, weil jede Ebene einer vorher von Menschen formulierten Erkennungsregel entspricht.  

    -- × Nicht korrekt. Beim Deep Learning werden Merkmale aus Daten gelernt. Die Ebenen bestehen daher nicht einfach aus einer Sammlung von Menschen vorab formulierter Regeln für jede Entscheidung.

[ ] Die Schlussfolgerung ist berechtigt, wenn für alle Bilder derselbe Schwellenwert verwendet wird.  

    -- × Nicht korrekt. Ein einheitlicher Schwellenwert macht die Annahmeregel für Treffer nachvollziehbarer. Er erklärt aber nicht, wie das Modell intern zu seinen Ausgabewerten gelangt.

[ ] Die Ergebnisse sind wegen der schwierigen Erklärbarkeit für eine wissenschaftliche Untersuchung grundsätzlich unbrauchbar.  

    -- × Nicht korrekt. Begrenzte Nachvollziehbarkeit ist eine wichtige Einschränkung, aber kein pauschaler Ausschlussgrund. Die Eignung muss kritisch geprüft, die Ergebnisse müssen kontrolliert und das Vorgehen muss offengelegt werden.


### Frage 4

**Ein Team entwickelt mithilfe bereits annotierter Bilder ein Erkennungsmodell. Später setzt es dieses Modell auf einen neuen Film an und legt fest, welche Ausgabewerte als Treffer gelten. Welche Aussagen zu diesen Vorgängen sind richtig?**

[x] Das Ableiten von Mustern aus den annotierten Bildern gehört zum Machine Learning.  

    -- ✓ Richtig! Beim maschinellen Lernen werden Lösungen beziehungsweise Muster aus Daten gewonnen. Die annotierten Bilder dienen hier als Grundlage des Lernprozesses.

[ ] Wenn ein trainiertes Modell auf neue Filmbilder angewendet wird, ist dies bereits ein neuer Trainingsprozess, weil die Bilder vorher unbekannt waren.  

    -- × Nicht korrekt. Neue Eingaben machen eine Anwendung nicht automatisch zum Training. Ein trainiertes Modell kann unbekannte Bilder verarbeiten, ohne dabei neu geschult zu werden.

[x] Die Festlegung des Schwellenwertes ist eine zusätzliche Entscheidung darüber, welche Modellwerte in konkrete Treffer überführt werden.  

    -- ✓ Richtig! Das Modell erzeugt Werte, während der Schwellenwert die Annahme eines Treffers steuert. Diese Entscheidung beeinflusst die resultierenden Annotationen und muss begründet werden.

[ ] Menschliche Wertungen in den Trainingsannotationen verlieren ihren Einfluss, sobald die Verarbeitung nur noch mit Zahlen erfolgt.  

    -- × Nicht korrekt. Die numerische Verarbeitung entfernt nicht die Auswahlentscheidungen und Wertungen, die in den Trainingsdaten enthalten sind. Diese können die erlernten Muster und damit die Ergebnisse beeinflussen.

[x] Deep Learning gehört zum Machine Learning und kann Merkmale über mehrere aufeinander aufbauende Verarbeitungsebenen lernen.  

    -- ✓ Richtig! Deep Learning ist ein Teilbereich des maschinellen Lernens. Seine mehrschichtige Struktur ermöglicht die Verarbeitung zunehmend komplexer Merkmale, bedeutet aber nicht, dass menschliche Einflüsse verschwinden.


### Frage 5

**Ein Projekt möchte eine große Sammlung von Filmen über Wintersport erschließen. Welche Vorschläge beschreiben geeignete Beiträge von Computer Vision, ohne deren Aussagekraft zu überschätzen?**

[x] Wiederkehrende sichtbare Gegenstände mit einem geeigneten Modell erfassen und anhand der Annotationen nach Mustern in der Sammlung suchen.  

    -- ✓ Richtig! Objekterkennung kann die Untersuchung großer Bild- und Filmsammlungen unterstützen. Die Interpretation gefundener Muster bleibt ein weiterer Analyseschritt.

[ ] Ein gut funktionierendes Modell zur Objekterkennung zugleich zur Bestimmung von Einstellungsgrößen einsetzen, weil beide Aufgaben dieselben Filmbilder als Eingabe verwenden.  

    -- × Nicht korrekt. Gleiche Eingabebilder bedeuten nicht gleiche Erkennungsaufgaben. Ein Modell muss die benötigten Merkmale beziehungsweise Kategorien erfassen können. Das Kapitel beschreibt zudem Schwierigkeiten bei der automatisierten Bestimmung von Einstellungsgrößen.

[x] Einstellungsübergänge erfassen und daraus zeitliche Abschnitte sowie Angaben zur Schnittgestaltung gewinnen.  

    -- ✓ Richtig! Die Einstellungserkennung ist ein filmanalytischer Einsatzbereich. Die resultierende zeitliche Gliederung kann weitere Annotationen und Auswertungen unterstützen.

[x] Gesichter zunächst im Bild lokalisieren und sie in einem weiteren Schritt ausgewählten Personen zuordnen.  

    -- ✓ Richtig! Gesichtslokalisierung und Personenzuordnung erfüllen unterschiedliche Aufgaben. Ihre Kombination kann eine Figurenerkennung unterstützen.

[ ] Die vom Modell erkannte Gesichtsemotion als hinreichenden Beleg für die erzählerische Gefühlslage einer Figur übernehmen, sofern die Kategorie über mehrere Bilder hinweg gleich bleibt.  

    -- × Nicht korrekt. Wiederholte Ausgaben können auch wiederholte Fehlklassifikationen sein. Die im Kapitel behandelte Emotionserkennung ist fehleranfällig; außerdem ist eine Gesichtskategorie nicht schon eine vollständige Deutung der Figur im filmischen Zusammenhang.


### Frage 6

**Ein Team plant die automatisierte Annotation historischer Werbefilme. Welche Überlegungen sind für die Planung und Bewertung des Workflows sinnvoll?**

[ ] Eine Bearbeitung der Bildqualität erst nach der Erkennung durchführen, weil sie dann auch fehlende Treffer in den bereits ausgegebenen Annotationen ergänzen kann.  

    -- × Nicht korrekt. Eine nachträgliche Bildbearbeitung verändert nicht rückwirkend die bereits erzeugten Erkennungsergebnisse. Soll eine verbesserte Bildgrundlage die Erkennung beeinflussen, muss sie vor der entsprechenden Modellanwendung bereitstehen und anschließend ausgewertet werden.

[x] Prüfen, ob eine geringere Zahl analysierter Bilder die für die Forschungsfrage wichtigen Ereignisse noch ausreichend erfasst.  

    -- ✓ Richtig! Weniger Bilder können Rechenaufwand sparen. Ob die Reduktion vertretbar ist, hängt jedoch von der beabsichtigten Annotation und möglichen Informationsverlusten ab.

[x] Bei einem Bildausschnitt nicht nur die Entfernung störender Elemente, sondern auch den Verlust relevanter Bildinformationen berücksichtigen.  

    -- ✓ Richtig! Eine Region of Interest kann die Verarbeitung auf einen Bereich konzentrieren. Was außerhalb dieses Bereichs liegt, steht der Erkennung anschließend nicht mehr zur Verfügung.

[ ] Unterschiedliche Modelle vorrangig anhand der Anzahl ihrer Treffer vergleichen, weil ein umfangreicherer Datensatz eine vollständigere Erkennung belegt.  

    -- × Nicht korrekt. Mehr Treffer können sowohl zusätzliche richtige Erkennungen als auch zusätzliche Fehler enthalten. Die Anzahl allein belegt keine bessere oder vollständigere Annotation; Ergebnisse müssen am Material überprüft werden.

[x] Entstehungskontext und Trainingsmaterial des Modells bei der Beurteilung seiner Eignung für die historischen Filme einbeziehen.  

    -- ✓ Richtig! Ein Modell wurde möglicherweise für anderes Bildmaterial und andere Zwecke entwickelt. Diese Unterschiede können Erkennungsprobleme und systematische Verzerrungen verursachen.


### Frage 7

**Für drei mögliche Objekttreffer gibt ein Modell die Werte 0,62, 0,79 und 0,91 aus. Ein Treffer wird in diesem Beispiel angenommen, wenn sein Wert den Schwellenwert überschreitet. Das Team erhöht den Schwellenwert von 0,75 auf 0,85. Modell und Bilder bleiben unverändert. Was folgt daraus?**

[ ] Der Treffer mit 0,79 bleibt erhalten, weil er beim ersten Durchlauf bereits angenommen wurde.  

    -- × Nicht korrekt. Bei einer erneuten Anwendung der veränderten Annahmeregel muss auch dieser Wert am neuen Schwellenwert geprüft werden. Frühere Annahme garantiert keine weitere Annahme.

[ ] Die Werte steigen durch die strengere Einstellung; der Treffer mit 0,79 erhält nun einen höheren Modellwert.  

    -- × Nicht korrekt. Das Ändern der Annahmeregel erhöht nicht die hier unveränderten Modellausgaben. Es verändert, welche vorhandenen Werte als Treffer eingestuft werden.

[x] Es wird nur noch der Treffer mit 0,91 angenommen; ob er tatsächlich richtig ist, muss weiterhin überprüft werden.  

    -- ✓ Richtig! Bei 0,75 werden die Werte 0,79 und 0,91 angenommen, bei 0,85 nur 0,91. Der höhere Schwellenwert schränkt die Treffermenge ein, beweist aber nicht die sachliche Richtigkeit des verbleibenden Treffers.

[ ] Die Zahl der Treffer sinkt, und damit ist zugleich belegt, dass die Annotation insgesamt besser zur Forschungsfrage passt.  

    -- × Nicht korrekt. Eine kleinere Treffermenge ist keine ausreichende Qualitätsbegründung. Auch relevante richtige Erkennungen können ausgeschlossen werden. Die Eignung muss anhand des Materials und des Untersuchungsziels beurteilt werden.


### Frage 8

**In einem Film über einen Museumsumbau treten einige Personen nur kurz auf. Um Zeit zu sparen, möchte ein Team statt vieler aufeinanderfolgender Bilder nur alle zwanzig Sekunden ein Bild analysieren. Was ist die angemessenste Beurteilung?**

[ ] Das Vorgehen ist ausreichend, wenn die ausgewählten Bilder gleichmäßig über den Film verteilt sind; dann werden auch kurze Auftritte zuverlässig berücksichtigt.  

    -- × Nicht korrekt. Eine gleichmäßige Verteilung verhindert nicht, dass kurze Auftritte vollständig zwischen zwei analysierten Bildern liegen. Regelmäßigkeit und ausreichende zeitliche Erfassung sind unterschiedliche Fragen.

[x] Das Vorgehen kann Zeit sparen, muss aber auf mögliche verpasste Kurzauftritte geprüft und für die Forschungsfrage begründet werden.  

    -- ✓ Richtig! Die Reduktion analysierter Bilder verändert die Datengrundlage. Ob sie sinnvoll ist, hängt davon ab, welche Ereignisse erfasst werden sollen und ob die zeitlichen Abstände dafür geeignet sind.

[ ] Das Team kann verpasste Kurzauftritte ausgleichen, indem es den Schwellenwert für die verbleibenden Bilder senkt.  

    -- × Nicht korrekt. Ein niedrigerer Schwellenwert verändert die Bewertung vorhandener Modellausgaben. Er kann keine Bildinformationen erfassen, die dem Modell gar nicht vorgelegt wurden.

[ ] Das Vorgehen ist für jede filmanalytische Aufgabe ungeeignet, weil stets sämtliche Bilder eines Films analysiert werden müssen.  

    -- × Nicht korrekt. Das Kapitel lässt eine begründete Reduktion zu. Entscheidend ist nicht eine allgemeine Pflicht zur Vollerfassung, sondern die Passung zwischen Bildauswahl und Aufgabe.


### Frage 9

**In Aufnahmen einer Bühnenprobe stört eine eingeblendete Grafik am unteren Bildrand die Erkennung. Nach dem Abschneiden des gesamten unteren Bereichs treten weniger Fehlmarkierungen auf. Dort waren allerdings gelegentlich auch Gesichter sichtbar. Welche Schlussfolgerung ist am besten begründet?**

[x] Der Ausschnitt kann eine Störquelle reduzieren, zugleich aber richtige Erkennungen verhindern; beide Folgen müssen für die Aufgabe geprüft werden.  

    -- ✓ Richtig! Die Vorverarbeitung verändert, welche Informationen verfügbar sind. Weniger Fehlmarkierungen allein belegen keine bessere Gesamtannotation, wenn relevante Inhalte zugleich entfernt werden.

[ ] Die geringere Zahl von Fehlmarkierungen rechtfertigt den Ausschnitt bereits, weil er die Erkennung auf relevante Bildbereiche konzentriert.  

    -- × Nicht korrekt. Ob der gewählte Bereich alle benötigten Informationen enthält, muss geprüft werden. In diesem Szenario entfernt der Ausschnitt auch Inhalte, die für eine Gesichtserkennung relevant sein können.

[ ] Die abgeschnittenen Gesichter können durch eine großzügigere Annahme der verbliebenen Treffer rekonstruiert werden.  

    -- × Nicht korrekt. Die Annahmeregel verändert nicht den Bildausschnitt. Informationen außerhalb des analysierten Bereichs stehen dem Modell nicht zur Verfügung.

[ ] Die Auswirkungen des Ausschnitts betreffen nur die spätere Visualisierung, nicht die Erkennung selbst.  

    -- × Nicht korrekt. Hier wird der Ausschnitt vor der Erkennung verwendet. Damit verändert er bereits die Eingaben und kann die erzeugten Annotationen beeinflussen.


### Frage 10

**Ein Modell liefert bei aktuellen, gut beleuchteten Farbaufnahmen überzeugende Objektmarkierungen. Ein Archiv möchte es nun auf unscharfe Schwarz-Weiß-Aufnahmen von Theateraufführungen anwenden. Welche Entscheidung ist am besten begründet?**

[ ] Das Modell unverändert übernehmen und dieselben Modellwerte als Beleg für dieselbe Zuverlässigkeit auf beiden Materialarten verwenden.  

    -- × Nicht korrekt. Die Ausgabewerte ersetzen keine Prüfung am neuen Material. Unterschiede in Bildqualität, Farbgestaltung und Trainingsbezug können die tatsächliche Erkennung beeinflussen.

[ ] Das Modell ausschließen, weil ein außerhalb der Filmwissenschaft entwickeltes Modell grundsätzlich keine geeigneten Filmannotationen erzeugen kann.  

    -- × Nicht korrekt. Die Herkunft aus einem anderen Anwendungsbereich ist kein pauschaler Ausschlussgrund. Das Kapitel beschreibt gerade die Nutzung vorhandener Modelle für neue Aufgaben, verlangt aber eine kritische Eignungsprüfung.

[ ] Den Schwellenwert erhöhen und anschließend auf eine Prüfung verzichten, da die strengere Auswahl die Unterschiede zwischen den Materialarten ausgleicht.  

    -- × Nicht korrekt. Eine strengere Annahmeregel beseitigt nicht automatisch Schwierigkeiten aufgrund anderer Bildbedingungen oder unpassender erlernter Muster.

[x] Das Modell am vorgesehenen Material prüfen und dabei Bildbedingungen, Trainingsbezug und konkrete Fehler berücksichtigen, bevor über seinen Einsatz entschieden wird.  

    -- ✓ Richtig! Gute Ergebnisse in einem Kontext lassen sich nicht ungeprüft übertragen. Je nach Befund können eine andere Vorverarbeitung, andere Schwellenwerte oder ein alternatives Modell in Betracht kommen.


### Frage 11

**Ordnen Sie jeder Situation den unmittelbar beschriebenen Arbeitsschritt zu. Jede Option darf höchstens einmal verwendet werden. Zwei Optionen bleiben übrig.**

Optionen:

- A: Dateneingabe — Bilder aus der Videodatei als Untersuchungsgrundlage bereitstellen.
- B: Vorverarbeitung — die bereitgestellten Bilder technisch bearbeiten.
- C: Modellanwendung — ausgewählte Merkmale aus den Bildern ermitteln.
- D: Schwellenwertentscheidung — Modellwerte in angenommene oder verworfene Treffer überführen.
- E: Modellentwicklung durch Training — anhand eines Lerndatensatzes ein Modell schulen.
- F: Nachgelagerte Auswertung — bereits erzeugte Annotationen vergleichend untersuchen.

Situationen:

1. Aus den Videos werden Einzelbilder gewonnen, die anschließend untersucht werden sollen.
2. Die gewonnenen Bilder werden zugeschnitten, bevor die Erkennung beginnt.
3. Ein bereits trainiertes Werkzeug erzeugt für die vorbereiteten Bilder Werte zur gesuchten Eigenschaft.
4. Bei unveränderten Modellwerten wird die Grenze geändert, oberhalb der ein Treffer in die Ergebnisliste eingeht.

Lösungen: 1 → A | 2 → B | 3 → C | 4 → D

### Frage 12

**Ordnen Sie jeder Beschreibung den spezifischsten passenden Begriff zu. Jede Option darf höchstens einmal verwendet werden. Zwei Optionen bleiben übrig.**

Optionen:

- A: Algorithmus
- B: Modell
- C: Machine Learning
- D: Schwellenwert
- E: Embedding
- F: Distant Viewing

Beschreibungen:

1. Eine Verfahrensanweisung legt fest, in welcher Reihenfolge Eingaben bearbeitet und Ausgaben erzeugt werden.
2. Ein bereits geschultes Werkzeug wird auf neue Bilder angewendet, um Hinweise auf ein bestimmtes Merkmal zu liefern.
3. Aus vorhandenen Beispieldaten werden Muster gewonnen, die eine Erkennungsaufgabe ermöglichen sollen.
4. Für einen bereits ausgegebenen Wert wird festgelegt, ab welcher Grenze er als angenommener Treffer zählt.

Zuordnung: 1 → A | 2 → B | 3 → C | 4 → D


### Frage 13: Wahr oder Falsch

**„Wenn bei unveränderten Bildern und unverändertem Modell nur die Annahmegrenze geändert wird, wurde das Modell dadurch erneut trainiert.“**

[ ] Wahr  

    -- × Nicht korrekt. Die Änderung betrifft die Bewertung der vorhandenen Modellwerte. Neues Training würde einen Lernprozess beschreiben, nicht lediglich eine andere Annahmeregel.

[x] Falsch  

    -- ✓ Richtig! Schwellenwertentscheidung und Training sind unterschiedliche Vorgänge. Eine andere Grenze kann andere Annotationen erzeugen, ohne dass das Modell neue Muster lernt.


#### (a)

**„Wenn ein Verfahren die Position eines Gesichts korrekt markiert, ist damit auch die dargestellte Person eindeutig bestimmt.“**

[ ] Wahr  

    -- × Nicht korrekt. Ein Gesicht im Bild zu lokalisieren beantwortet noch nicht, wem es zugeordnet werden soll. Die Personenzuordnung erfüllt eine zusätzliche Aufgabe.

[x] Falsch  

    -- ✓ Richtig! Face Detection und Face Recognition unterscheiden sich: Der erste Schritt findet Gesichter, der zweite ordnet sie Personen zu. Deshalb können verschiedene Modelle kombiniert werden.


#### (b)

**„Wenn ein Deep-Learning-Modell seine Merkmale aus Daten lernt, können menschliche Auswahlentscheidungen und Wertungen dennoch seine Ergebnisse beeinflussen.“**

[x] Wahr  

    -- ✓ Richtig! Auch selbständig gelernte Merkmale beruhen auf ausgewählten Trainingsdaten und deren Beschaffenheit. Menschliche Perspektiven können über Auswahl und Annotation dieser Daten in das Modell eingehen.

[ ] Falsch  

    -- × Nicht korrekt. Das selbständige Lernen von Merkmalen bedeutet nicht, dass die Datengrundlage unabhängig von Menschen entstanden ist. Numerische Verarbeitung hebt diese Einflüsse nicht auf.


#### (c)

**„Einige nachgewiesene Fehlmarkierungen reichen für sich allein nicht aus, um eine automatisierte Annotation als wissenschaftlich unbrauchbar einzustufen.“**

[x] Wahr  

    -- ✓ Richtig! Fehler müssen untersucht und bei der Nutzung berücksichtigt werden. Dennoch können Annotationen für bestimmte Forschungsaufgaben nützlich sein. Entscheidend ist eine kritische Beurteilung der Ergebnisse und ihrer Eignung, nicht die bloße Feststellung, dass überhaupt Fehler vorkommen.

[ ] Falsch  

    -- × Nicht korrekt. Das Kapitel fordert keine pauschale Ablehnung aller nicht fehlerfreien Verfahren. Es verbindet den möglichen Nutzen mit Überprüfung und Transparenz über eingesetzte Modelle, Algorithmen und Schwellenwerte.


### Frage 14

**Szenario:** Sie beraten ein Projekt, das Filme über die Arbeit in öffentlichen Bibliotheken untersucht. Drei Teams berichten von unterschiedlichen Schwierigkeiten:

- (a) Kurze Auftritte fehlen: Ein Team möchte das Auftreten ausgewählter Personen untersuchen. Um die Verarbeitung zu beschleunigen, analysiert es nur alle dreißig Sekunden ein Bild. Bei einer Sichtung bemerkt es Personen, die jeweils nur wenige Sekunden sichtbar sind und in den Annotationen fehlen. Das Team schlägt vor, ausschließlich den Schwellenwert zu senken.
- (b) Historische Bilder werden falsch eingeordnet: Ein anderes Team nutzt ein vortrainiertes Modell zur Objekterkennung auf unscharfen Schwarz-Weiß-Aufnahmen. Es markiert einige alte Arbeitsgeräte als moderne Geräte. Das Team möchte deshalb alle Markierungen mit hohen Modellwerten ohne weitere Prüfung übernehmen.
- (c) Zwei Ergebnislisten widersprechen sich: Ein drittes Team verarbeitet dieselben Bilder mit demselben Modell und erhält dieselben Modellwerte. Mit dem Schwellenwert 0,55 entsteht eine längere Trefferliste als mit 0,85. Das Team vermutet, dass das Modell im zweiten Durchlauf dazugelernt habe und die kürzere Liste deshalb die bessere sei.

Beschreiben Sie für jede Situation, welche Erklärung und welches weitere Vorgehen Sie empfehlen würden. Begründen Sie Ihre Antwort anhand des Erkennungsprozesses und der Datengrundlage — nicht allein anhand des Filmthemas.

Gehen Sie dabei auf folgende Punkte ein:

1. Wo im Prozess liegt das jeweilige Problem: bei der Bildauswahl, bei der Eignung des Modells oder bei der Annahmeregel?
2. Welche Änderung oder Überprüfung wäre sinnvoll, und was könnte die vorgeschlagene Änderung allein nicht leisten?
3. Wie kann Computer Vision die Untersuchung trotz dieser Schwierigkeiten unterstützen?

Erläutern Sie zusätzlich für (c), warum die Änderung des Schwellenwertes nicht mit einem neuen Lernprozess gleichzusetzen ist. Unterscheiden Sie dabei das angewendete Modell von der Regel zur Annahme eines Treffers.

<details>
<summary>Reflexionshinweise</summary>

#### Musterlösung

Andere begründete Vorschläge sind möglich, wenn sie den jeweiligen Problembereich berücksichtigen und die Grenzen der Schlussfolgerungen deutlich machen.

(a) Kurze Auftritte fehlen:

- Erklärung: Die zeitlichen Abstände zwischen den analysierten Bildern sind möglicherweise zu groß. Ein kurzer Auftritt kann vollständig zwischen zwei ausgewählten Bildern liegen. Dann erhält das Modell keine Bildgrundlage für diesen Auftritt.
- Vorgehen: Das Team sollte prüfen, ob die Bildauswahl zum Ziel der Personenerfassung passt, und mehr Bilder in kürzeren Abständen analysieren. Außerdem muss es unterscheiden, ob ein Gesicht gar nicht gefunden oder ein gefundenes Gesicht keiner Person zugeordnet wurde.
- Grenze des Vorschlags: Ein niedrigerer Schwellenwert verändert die Annahme vorhandener Modellwerte. Er kann keine Person in einem Bild erfassen, das nicht analysiert wurde.
- Nutzen: Passende Modelle zur Gesichtslokalisierung und Personenzuordnung können die Erfassung unterstützen. Das gewählte zeitliche Raster und die Zuverlässigkeit der Erkennung müssen aber geprüft werden.

(b) Historische Bilder werden falsch eingeordnet:

- Erklärung: Bildqualität, Schwarz-Weiß-Gestaltung und Unterschiede zwischen Trainingsmaterial und Untersuchungsmaterial können die Erkennung erschweren. Die verfügbaren erlernten Muster passen möglicherweise nicht ausreichend zu den historischen Geräten.
- Vorgehen: Das Team sollte Markierungen am Originalmaterial überprüfen und nach Möglichkeit Informationen über Trainingsdaten und Entstehungskontext des Modells berücksichtigen. Es kann untersuchen, ob eine geeignete Vorverarbeitung oder ein alternatives Modell besser zum Material passt.
- Grenze des Vorschlags: Ein hoher Modellwert belegt nicht allein die sachliche Richtigkeit einer Gerätezuordnung. Auch eine strengere Treffergrenze beseitigt nicht automatisch unpassende erlernte Muster.
- Nutzen: Überprüfte Objektannotationen können helfen, wiederkehrende Gegenstände und mögliche Muster in einer größeren Sammlung zu finden. Ihre inhaltliche Bedeutung bleibt anschließend zu untersuchen.

(c) Zwei Ergebnislisten widersprechen sich:

- Erklärung: Die Modellwerte sind unverändert. Geändert wurde nur die Annahmegrenze. Bei 0,85 werden weniger vorhandene Werte als Treffer angenommen als bei 0,55. Unterschiedliche Listen sind deshalb kein Beleg für einen neuen Lernprozess.
- Begriffe: Das Modell ist das bereits trainierte Werkzeug, das Werte für die Bilder erzeugt. Der Schwellenwert ist eine zusätzliche Entscheidungsgrenze. Das Anwenden einer anderen Grenze ist nicht dasselbe wie Machine Learning, bei dem Muster aus Daten gelernt werden.
- Vorgehen: Das Team sollte zusätzliche und ausgeschlossene Treffer anhand des Films prüfen. Danach kann es begründen, welche Einstellung für seine Aufgabe geeignet ist. Modell und Schwellenwert sowie die Gründe für ihre Wahl sollten offengelegt werden.
- Grenze der Schlussfolgerung: Die kürzere Liste ist nicht allein wegen ihrer geringeren Länge besser. Sie kann Fehlmarkierungen reduzieren, aber auch relevante richtige Treffer ausschließen.
- Nutzen: Eine begründete Schwellenwertentscheidung macht die Erstellung der Annotationen nachvollziehbarer. Sie unterstützt die Erschließung des Materials, ersetzt jedoch keine Qualitätsprüfung.

#### Zentrale Erkenntnis

Bildauswahl, Modellanwendung und Schwellenwertentscheidung beeinflussen die Ergebnisse auf unterschiedliche Weise. Eine Änderung an einer Stelle behebt nicht automatisch Probleme an einer anderen. Computer Vision kann große Materialmengen erschließen und Muster sichtbar machen, wenn seine Ergebnisse überprüft, seine Grenzen berücksichtigt und die getroffenen Entscheidungen transparent gemacht werden.

</details>




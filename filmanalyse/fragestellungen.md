# Fragestellungen zur Fallstudie
Im diesem Kapitel sollen mögliche Fragestellung für unsere Fallstudie entwickelt werden. Im Zentrum der OER soll das Themenfeld der Workflows für die automatisierte Annotation von Filmen stehen. Die Voraussetzungen für die automatisierte Filmannotation, deren Möglichkeiten und Grenzen sollen dargestellt und reflektiert werden. Als Ausgangspunkt liegen hier zunächst zwei grundlegende Fragen vor:

- welche Annotationsdaten sollen automatisiert erhoben werden?
- wie können diese Annotationen automatisiert werden? Also welche Modelle und Algorithmen können für die automatisierte Annotation auf welche Weise verwendet werden?

Der zweiten Frage und der Frage, was Modelle, Algorithmen, Computer Vision und technische Voraussetzungen sind werden wir uns in einem **eigenen großen Kapitel** zuwenden. Dort werden wir auch darauf eingehen, welche Modelle überhaupt für filmwissenschaftliche Fragestellungen bzw. automatisierte Filmannotation in Frage kommen und warum wir uns letztlich in unserer Fallstudie für die Erkennung von Einstellungsübergängen bzw. Einstellungslängen und die Bestimmung des Auftretens von bestimmten Figuren in Filmen entschieden haben.

Als Untersuchungskorpus haben wir die Filme <a href="https://de.wikipedia.org/wiki/Konrad_Wolf" class="external-link" target="_blank">Konrad Wolfs</a> ausgewählt. Wir können dadurch die Filme eines Regisseurs und seinen filmischen Stil in den Mittelpunkt unserer Fallstudie stellen, wobei das Korpus mit 14 Spielfilmen dennoch überschaubar und auch (technisch) handhabbar bleibt. Dennoch weist sein Werk verschiedene Schaffensphasen und eine interessante Heterogenität auf: verschiedene Genres, Erzählweisen und Themen sind erkennbar. Nicht zuletzt liegen die Spielfilme Wolfs als DVD-Edition und damit in digitaler Form vor, was die Auswertung und Annotation mit computergestützten Verfahren ermöglicht, unseren Workflows also entgegen kommt.

Ansätze zur quantitativen Stilanalyse haben wir im vorigen Kapitel vorgestellt. Auch in unserer Fallstudie wollen wir in diese Richtung gehen und film-stilistische Fragen mithilfe von quantitativen (Annotations)daten und errechneten Größen angehen. Welche kommen nun hier bei der Erkennung von Einstellungswechseln in Frage?
- die Länge des gesamten Films
- die Anzahl der Einstellungen in einem Film
- die Länge der einzelnen Einstellungen in einem Film
- die Dauer der kürzesten und der längsten Einstellung in einem Film
- die durchschnittliche Einstellungslänge (Average Shot Length - ASL): Filmlänge geteilt durch die Anzahl der Einstellungen
- die mittlere Einstellungslänge (Median Shot Lenght - MSL): Der Wert, der genau in der Mitte aller Einstellungslängen liegt; dadurch werden Ausreißer nach unten und oben vermieden
- die Einstellungsdichte: Zahl der Einstellungswechsel in einem bestimmten Zeitraum

Anhand dieser Werte ist die Bearbeitung verschiedener Fragestellungen zu den Einstellungslängen bei den Filmen Konrad Wolfs möglich:
- wie unterscheidet sich die ASL und MSL bei den Filmen Konrad Wolfs
    + welche Gründe könnte es dafür geben
    + wie unterscheidet sich die MSL und ASL bei einzelnen Filmen
    + hängen Unterschiede mit Schaffensphasen oder Genres zusammen
- wie verändert sich die Schnittfrequenz im Laufe eines Films
    + an welcher Stelle sind warum Veränderungen erkennbar
    + gibt es einen Zusammenhang mit auftretenden Plot Points oder Konflikten in der Handlung
- sind wiederkehrende Muster von Einstellungslängen in verschiedenen Filmen Wolfs erkennbar

Die Annotationswerte zu den Einstellungslängen können also sowohl innerhalb eines Films untersucht als auch mit mehreren Filmen in Bezug gesetzt werden.

Als zweiten Workflow für die automatisierte Annotation werden wir das Auftreten von Figuren in einem Film in den Blick nehmen. Hier können folgende Werte interessant sein:
- welche Figur tritt an welcher Stelle des Films auf
- die Gesamtdauer der Leinwandpräsenz einer Figur
- wann ist eine Figur allein auf der Leinwand zu sehen
- wann tritt eine Figur zusammen mit einer anderen Figur oder anderen Figuren auf
    + wie lange treten Figuren gemeinsam auf

Anhand dieser Werte kann wiederum verschiedenen Fragen in Bezug auf einen oder mehrere Filme Konrad Wolfs nachgegangen werden:
- wie oft treten Figuren gemeinsam auf
    + handelt es sich um Protagonist:innen oder um Nebenfiguren
    + können aus dem gemeinsamen Auftreten Rückschlüsse hinsichtlich der Beziehung der Figuren zueinander gezogen werden
- wer hat die längste Leinwandzeit
    + handelt es sich dabei um Protagonist:innen
- wie verteilt sich das Auftreten von Figuren über die Dauer des Films
    + kann das Auftreten von Figuren mit Narrationsstrukturen oder Genres in Verbindung gebracht werden
- handelt es sich um 'Ensemblefilme' oder Filme mit einzelnen Protagonist:innen

Aus den möglichen Fragen wird bereits deutlich, dass hier an einigen Stellen die Annotationen zu Einstellungslängen und Figurenpräsenz miteinander in Beziehung gesetzt werden sollten - z.B. bei der Frage, ob Figuren in einer Einstellung oder Szene gemeinsam auftreten. Wichtige Vorüberlegungen beim Vorgehen sind dabei, für welche Figuren das Auftreten in einem Film überhaupt bestimmt werden soll. Wie wir im **Kapitel zu Computer Vision** und den von uns angewendeten Modellen noch zeigen werden, ist eine Bestimmung für alle Figuren eines Films technisch noch nicht möglich bzw. technisch zu aufwendig.

Abschließend zum Kapitel zu den möglichen Fragestellungen sei noch exemplarisch auf einige weitere interessante Größen und Fragen hingewiesen, auf die wir jedoch in der Fallstudie nicht weiter eingehen werden:
- welche Einstellungsgrößen treten auf
    + welche Anzahl der einzelnen Einstellungsgrößen liegen im Film vor
    + wie sind die Einstellungsgrößen im Verlauf des Films verteilt
    + wie verhalten sich Einstellungsgrößen und Einstellungslängen zueinander
- welche Kamerabewegungen werden eingesetzt
- von welcher Art sind die Einstellungsübergänge (harter Schnitt, Überblendung, Wischblende etc.)
- welche Objekte oder Handlungsweisen treten wiederholt in Filmen auf

Nicht alle der hier aufgeführten Fragen können in der Fallstudie behandelt werden. Es sollte deutlich geworden sein, dass schon mit den hier für die automatisierten Annotation angedachten Parameter Einstellungsübergänge und Auftreten von Figuren Annotationsdaten erhoben werden, die für die Bearbeitung unterschiedlichster Fragestellungen dienen können. Wir haben uns für diese beiden Parameter entschieden, da die Bestimmung der Einstellungslänge eine Grundlage für viele weitere Annotationen sein kann und die Figurenannotation in vielen verschiedenen Kontexten einsetzbar ist. Zudem sind beide Annotationsparamter auch technisch umsetzbar. Bei der Auswertung der erhobenen Annotationen werden wir in der Fallstudie explorativ vorgehen, also die Daten hinsichtlich möglicher auftretender Muster untersuchen. Dabei muss nicht immer gleich eine ganz konkrete Fragestellung im Mittelpunkt stehen.

Theoretische und technische Fragen zu Computer Vision, die eng mit der automatisierten Annotation zusammenhängen, werden wir im folgenden Kapitel angehen.
# Explorative Auswertung der Annotationen
In den vorigen Kapiteln wurden mit Jupyter Notebooks aus den automatisiert erhobenen Annotationsdaten zur Einstellungs- und Figurenerkennung verschiedene Visualisierungen erstellt. In diesem Kapitel sollen diese Visualisierungen nun näher betrachtet und mit ihnen die Annotationsdaten ausgewertet werden.

Dabei muss im Blick behalten werden, dass die Annotationsdaten und damit die hier in den Grafiken dargestellten Werte Fehler enthalten können. Schnelle Bewegungen können die [Erkennung von Einstellungsübergängen erschweren](../annotation/einstellung_datensichtung.md), schlecht erkennbare Gesichter [beeinträchtigen die Figurenerkennung](../annotation/figuren_datensichtung.md). Dennoch sind mit diesen nicht immer fehlerfreien Annotationsdaten mögliche Zusammenhänge, Tendenzen und Muster gut erkennbar. Sie können also durchaus die Grundlage für weitere Untersuchungen oder die Entwicklung von Fragestellungen bilden.

Die Auswertung der Annotationsdaten in diesen Kapitel kann aufgrund des begrenzten Umfangs der Fallstudie jedoch nicht in die Tiefe gehen. Wir werden die Ergebnisse explorativ betrachten und einige Beobachtungen festhalten. Mögliche Fragestellungen haben wir in einem [eigenen Kapitel](../filmanalyse/fragestellungen.md) entwickelt, im Fokus ist dabei eine quantitative Auswertung der Annotationsdaten. An mehreren Stellen der OER haben wir betont, dass eine Verbindung dieser quantitativen Auswertung mit qualitativen Herangehensweisen wichtig ist. Dies kann im Rahmen dieser Fallstudie ebenfalls nicht geleistet werden.

Im Folgenden werden wir uns nun zunächst mit den Ergebnissen der Einstellungsannotationen beschäftigen, daran anschließenden mit den Figurenannotationen.

## Visualisierung der Einstellungsdaten
Die hier präsentierte Visualisierung der Einstellungsannotationen zu den Filmen Konrad Wolfs ist nur eine Variante von vielen Möglichkeiten. Im [Kapitel zu möglichen Fragestellungen](../filmanalyse/fragestellungen.md) wurden mögliche quantitative Annotationsdaten vorgestellt. In die vorliegende grafische Darstellung wurden folgende auf filmischen Einstellungen beruhende Werte einbezogen: Die durchschnittliche (Average Shot Length / ASL) und mittlere Einstellungslänge (Median Shot Length / MSL) in Sekunden (errechnet aus den Daten zu den Einstellungslängen eines Films), die längste und sie kürzeste Einstellung eines Films in Sekunden, die Filmlaufzeit in Minuten und die Anzahl der Einstellungen in einem Film.

Diese Werte werden als Balkendiagramme in einzelnen Grafiken untereinander ausgegeben, die einzelnen annotierten Filme folgen nacheinander.

<iframe
  src="../_static/html/shot_meta.html"
  width="100%"
  height="800"
  style="border:0;">
</iframe>

Mit dem Scrollbalken am rechten Rand kann durch die Grafiken navigiert werden. Durch Bewegung des Mauszeigers über den Balken für den jeweiligen Film wird dessen Erscheinungsjahr und der dargestellte Wert mit der jeweiligen Maßeinheit angezeigt. Unter jedem Balkendiagramm kann die Art der Sortierung der Ergebnisse ausgewählt werden: nach Werten, alphabetisch oder chronologisch.

Starten wir mit der Sortierung nach Werten. Was lässt sich beobachten? *Sterne* weist sowohl bezüglich der ASL als auch der MSL die höchsten Werte auf. Auch bei der längsten Einstellung führt der Film die Grafik an. Bei der kürzesten Einstellung und der Filmlaufzeit befindet sich *Sterne* verglichen mit den restlichen Filmen im unteren Drittel.

Bei *Goya* fällt auf, dass die Anzahl der Einstellung am größten von allen Filmen ist und einen sehr hohen Wert besitzt. Zwar ist auch die Laufzeit die längste aller Filme, trotzdem sticht der Wert mit 1074 Einstellung deutlich aus den restlichen Filmen hervor. Dementsprechend sind auch die ASL und MSL Werte am geringsten, da sich dadurch mehr Einstellungen innerhalb der Laufzeit ergeben.

*Der geteilte Himmel* wurde bereits oft in unserer OER erwähnt und dessen Trailer in den Notbooks zur Einstellungs- und Figurenerkennung exemplarisch annotiert. Bei ASL und MSL und der Laufzeit liegt der Film hier im Mittelfeld aller Filme. Bei der längsten und bei der kürzesten Einstellung liegt *Der geteilte Himmmel* im unteren Bereich bezogen auf alle untersuchten Filme.

Geht man zur chronologischen Sortierung über wird erkennbar, dass die ASL und MSL mit steigenden Erscheinungsjahr immer kürzer werden. Hier heben sich *Sterne* und *Goya* ebenfalls ab:  *Sterne* mit vergleichsweise hohen Werten, *Goya* mit vergleichsweise niedrigen Werten.

**Screenshots einfügen**

An dieser Stelle wäre es sinnvoll, von der Betrachtung aller Filme wieder zurück zu einzelnen Filmen zu gehen, die sich in der Grafik mit markanten Werten abheben - wie z.B. *Sterne* oder *Goya*. Den Ursachen für diese auffälligen Werte sollte anhand einer genaueren Analyse der Filme und der Untersuchung des Produktionskontextes auf den Grund gegangen werden. Wo im Film ist etwa die längste Einstellung angesiedelt? Welche konkreten Muster der Abfolge von Einstellungslängen hat der Film vorzuweisen?

Hierfür können wiederum andere Visualisierungen mit den Annotationsdaten für einzelne Filme erstellt werden, etwa zur Einstellungsdichte in einem Film. Zudem würde es sich anbieten, hier wie schon bei der [Überprüfung der Einstellungserkennung](../annotation/einstellung_datensichtung.md) mit dem Annotationstool VIAN zu arbeiten. In dieses können die Annotationsdaten zur Einstellungserkennung eingelesen und mit dem konkret annotierten Film abgeglichen werden. Mit der Sichtung im VIAN könnten auch Ungenauigkeiten und Fehler in den Annotationsdaten erkannt werden.

## Visualisierung der Figurenpräsenz
Nach der Einstellungserkennung folgt nun die Visualisierung und Auswertung der Annotationsdaten aus der Figurenerkennung zu den Filmen *Sonnensucher*, *Der geteilte Himmel* und *Solo Sunny*. Unsere Auswahlkriterien und die Namen der zu erkennenden Figuren haben wir bereits im Kapitel zu den [Grundlagen zur Auswertung](../auswertung/grundlagen.md) dargelegt.

Wir beginnen mit der Grafik zur Visualisierung der Figurenpräsenz in den Filmen.

<iframe
  src="../_static/html/character_timeline_altair_v4.html"
  width="100%"
  height="500"
  style="border:0;">
</iframe>

Jeder Figur ist hier eine eigene Spur und eine eigene Farbe zugeordnet. Wurde eine Figur erkannt, wird dies durch einen Balken im Zeitverlauf angezeigt. Die Spuren der Figuren sind nach Gesamtdauer der Leinwandpräsenz einer Figur von oben nach unten angeordnet, die Figur mit der längsten Präsenz wird ganz oben angezeigt. Wird der Mauszeiger über einen Balken einer Figur platziert, werden die zum Balken gehörenden Werte angezeigt. Durch ein Dropdown-Menü am linken unteren Ende der Grafik kann zur Darstellung des jeweiligen Films im Diagramm gewechselt werden.

**evtl. Screenshot**

Bei *Der geteilte Himmel* fällt auf, dass Rita die präsenteste Figur mit der meisten Leinwandzeit ist, gefolgt von Manfred. Beide Figuren sind die Protagonist:innen des Films. Meternagel als wichtige Bezugsfigur für Rita ist häufig im Bild zu sehen, ebenso Wendland als politisch einflussreiche und wichtige Figur. Herr und Frau Herrfurth treten meist gemeinsam auf, ebenso wie Kuhl und Ermisch, die zusammen mit Meternagel arbeiten.

**evtl. Screenshot Sunny**

Wechselt man zur Visualisierung von *Solo Sunny* wird sofort deutlich, dass hier Sunny die dominierende Figur ist. Sie ist fast den gesamtem Film über präsent. Nach Sunny folgen mit deutlich weniger Auftritten im Bild Ralph und Harry, die nie zusammen im Bild zu sehen sind, aber wichtige Bezugspunkte zu Sunny bilden. Neben Harry tritt auch Christine allein zusammen mit Sunny im Bild auf, sie ist eine alte Freundin von ihr. Norbert, Hubert, Bernd und Benno sind als Musiker in Sunnys Band oft gemeinsam präsent.

**evtl. Screenshot Sonnensucher**

Bei *Sonnensucher* bietet sich wiederum ein anderes Bild. Hier scheint die Dauer des Auftretens der Figuren Beier, Lutz, Jupp und Sergej im Bild verteilt über den Film sehr ähnlich zu sein, auch wenn sie oft zu unterschiedlichen Zeitpunkten zu sehen sind. Hier kann also von einem Film mit mehreren, gemäß der des zeitlichen Auftretens im Film gleichberechtigten Protagonist:innen ausgegangen werden. Günter und Emmi sind als wichtige Nebenfiguren recht häufig präsent, Weirauch und Wera eher seltener.

Hier sind also deutliche Unterschiede in den Mustern des zeitlichen Auftretens von Figuren im Film zu erkennen, die vermutlich auch mit den behandelten Themen in den Filmen zusammenhängen. *Sonnensucher* ist eher ein Ensemblefilm, in dem DDR-Arbeiter:innen für den politisch wichtigen Uranabbau mit den sowjetischen Soldat:innen zusammenarbeiten müssen. In *Solo Sunny* sucht Sunny allein als kompromisslose Künstlerin ihren Weg im Leben und in der Gesellschaft.

Auch hier würde es sich wieder anbieten, an dieser Stelle zur genauen Analyse der einzelnen Filme zurückzukehren, indem etwa die Annotationsdaten zu den Figuren in VIAN eingelesen werden. Hier kann genauer betrachtet werden, welche Figuren wann aus welchen Gründen gemeinsam im Bild zu sehen sind. Auch Annotationsfehler werden dadurch sichtbar wie z.B. in *Solo Sunny*, bei dem der Bandleader Hubert am Ende fälschlicherweise im Bild der Szene erkannt wird, in der Sunny auf ihre möglicherweise neue Band trifft.


## Visualisierung der Figurenbeziehungen
Nun soll die Visualisierung zu den Figurenbeziehungen betrachtet werden. Zu sehen sind in der Grafik die Beziehungen der Figuren untereinander gemäß ihrer gemeinsamen Präsenz auf der Leinwand. Zusätzlich wird die Gesamtdauer der erkannten Präsenz einer Figur im Film durch die Größe des ihr zugeordneten Kreises angezeigt. Gemeinsam im Bild auftretende Figuren sind durch Striche miteinander verbunden, die Dicke der Striche zeigt die Höhe des Wertes des gemeinsamen Auftretens an. In der interaktiven Grafik kann auf die Figurenkreise geklickt und diese an andere Orte gezogen werden, dadurch können Verbindungen zwischen Figuren und Figurengruppen noch deutlicher werden.

<iframe
  src="../_static/html/character_network_gravis.html"
  width="100%"
  height="800"
  style="border:0;">
</iframe>

Die Anzeige der einzelnen Filme kann hier im Auswahlmenü am rechten Rand durch die Auswahlmenüs "Data Selection" -> "Graph" ausgewählt werden. Die Bedeutung der einzelnen Einstellungsmöglichkeiten im rechten Menü können hier nicht weiter besprochen werden, experimentieren Sie aber gerne mit verschiedenen Einstellungen. Mit einem Klick auf "Reset" können Sie jeweils zum Ausgangszustand der Visualisierung zurückkehren.

**Screenshot einfügen**

In *Der geteilte Himmel* hat Rita gefolgt von Manfred über den Film verteilt die längste Präsenz im Bild - der große Kreis ihrer Figur ist deutlich im Zentrum platziert. Nach dem Aufbau der Grafik werden die verschiedenen Sphären der Figurenkonstellation deutlich:

**Screenshot**

Im rechten Teil der Grafik sind mit Kuhl, Meternagel Schwarzenbach, Ermisch und Wendland die Figuren der Arbeitswelt im Form der Wagonfabrik und der Universität versammelt. Im linken Teil unten mit Herr und Frau Herrfurth und oben mit Martin der private Bereich Ritas und Manfreds.

**Screenshots**

Ein Klick auf Martin zeigt, dass er bei den erfassten Stellen des Auftretens nur mit Rita und Manfred zusammen zu sehen ist, Schwarzenbach hingegen nur mit Rita

**Screenshot**


Ein Blick auf die Grafik für die Figurenbeziehungen in *Solo Sunny* zeigt wiederum die Dominanz Sunnys in Bezug auf ihre Leinwandzeit. Ihr Figuren-Kreis ist mit Abstand der größte, als einzige Figur ist sie mit allen anderen erfassten Figuren verbunden.

**Screenshot**

Bei genauerer Betrachtung wird erkennbar, dass Ralph, Harry und Christine mit deutlich dickeren Verbindungsstrichen mit Sunny verbunden sind als die übrigen erfassten Figuren.
Christine und Harry sind dabei nur mit Sunny gleichzeitig im Bild und haben dadurch keine Verbindungslinien zu anderen Figuren.

**Screenshot Christine**

Als Aushilfsmusiker ist Ralph hingegen noch mit den Bandkollegen Bernd und Hubert gemeinsam im Bild zu sehen und daher durch eine Linie in der Grafik verbunden.

**Screenshot Ralph**


Bei *Sonnensucher* zeigt sich bei den Figuren Lutz, Jupp, Beier und Sergej eine besonders lange Präsenz im Bild, sie sind auch im Laufe des Films mit allen weiteren erfassten Figuren im Bild zu sehen bzw. sind in der Grafik mit allen anderen Figuren durch einen Verbindungsstrich in Beziehung gesetzt. 

**Screenshot**

Die Dicke der Verbindungsstriche als Indikator für die Dauer der gemeinsamen Leinwandpräsenz variiert dabei je nach Figur. Insgesamt ist das durch ein gemeinsames Auftreten im Bild entstehende Netz der Figuren untereinander hier wesentlich dichter gestrickt. Lediglich Günter wurde z.B. nicht zusammen mit Fedossjev und Wera erfasst, und Wera nicht zusammen mit Günter. Dies könnte für eine deutlich intensivere Interaktion aller Figuren miteinander sprechen als bei den bisher betrachteten Filmen.

**Screenshot Günter**

Auch hier sind die Visualisierungen mit Vorsicht zu behandeln und mit Bedacht zu interpretieren. Die Figurenerkennungen sind nicht unbedingt vollständig und nicht immer fehlerfrei. Dennoch werden wichtige Muster des gemeinsamen Auftretens von Figuren deutlich und können als Grundlage für Überlegungen bezüglich der Beziehung von Figuren untereinander dienen. Diese müssten wiederum an den konkreten Filmen untersucht und überprüft werden. Denn dass Figuren gemeinsam im Bild auftreten sagt noch nichts über die Art ihrer Beziehung untereinander aus. Letztlich muss auch hier der breitere Kontext in Form der Produktionsbedingungen und der politischen Lage zu Entstehungszeit des Films mit einbezogen werden.

Hier konnte anhand einiger exemplarischer Visualisierungen nur eine kurze, sehr oberflächliche Auswertung stattfinden. Es sollte aber deutlich geworden sein, dass die automatisiert erstellten Annotationen für die Bearbeitung einer Fragestellung durchaus nützlich sein können. Quantitative Auswertungen können Auffälligkeiten sichtbar machen, die dann hinsichtlich ihrer Ursachen genauer untersucht werden müssen. Im besten Fall können sich neue Fragestellungen ergeben oder auch bisherige Annahmen untermauert und besser erfassbar gemacht werden.



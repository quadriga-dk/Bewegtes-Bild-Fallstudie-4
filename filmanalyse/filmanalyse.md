
# Filmanalyse: Grundlagen und Herangehensweisen

Filmanalysen stellen eine der Grundkomponenten filmwissenschaftlicher Forschung dar. Seit einigen Jahren liegen immer mehr Filme und Materialien zu audiovisuellen Medien in digitaler Form vor. Die digitale Verfügbarkeit der Forschungsgegenstände ermöglicht neue Herangehensweisen an filmwissenschaftliche Fragestellungen - etwa mit Tools und Methoden der Digital Humanities (vgl. hierzu auch das Kapitel zu <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-2/einleitung/toc.html" class="external-link" target="_blank">Digital Humanities und Filmwissenschaft</a> in der Fallstudie zu "Studentische Filme an der Filmuniversität Babelsberg zur Wendezeit (1985-1999)"). In diesem Rahmen eröffnen sich auch für die filmanalytische Arbeit neue, interessante Perspektiven, etwa in Form von erweiterten Analysemöglichkeiten durch digitale Ansätze.

Digitale Tools bieten die Möglichkeit, Filmanalysen zu unterstützen: Aufwändige manuelle Prozesse können oft vereinfacht oder (teil)automatisiert werden. In dieser Fallstudie zu Workflows für die automatisierte Annotation von Filmen wollen wir diesem Potential digitaler Arbeitsweisen nachgehen. Annotationen stellen eine wichtige Grundlage für die fundierte Analyse von Filmen dar. Als exemplarisches Beispiel werden wir in dieser OER auf die Filme Konrad Wolfs eingehen, die Einstellungslängen der Filme automatisiert annotieren - ebenso wie das Auftreten bestimmter Figuren in einzelnen Filmen Wolfs.

````{margin} 
```{admonition} Hinweis
:class: hinweis
Weitere Informationen zum Themenfeld Filmanalyse finden sich bei der <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-1/Kapitel_I/weiterf%C3%BChrende_Informationen.html" class="external-link" target="_blank">Fallstudie I - Bewegtes Bild</a>. 
```
````


Doch zunächst muss geklärt werden, was mit "Filmanalyse" überhaupt gemeint ist. Es existiert keine allgemeingültige Definition von "Filmanalyse" oder eine standardisierte Vorgehensweise bei der filmanalytischen Arbeit. Vielmehr gibt es ganz unterschiedliche Formen von und Herangehensweise an Filmanalyse. Diese können hier nicht umfassend im Detail vorgestellt werden, weiterführende Informationen finden sich auch in der <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-1/Kapitel_I/weiterf%C3%BChrende_Informationen.html" class="external-link" target="_blank">Fallstudie I - Bewegtes Bild</a>.

Dennoch sollen hier einige filmanalytische Grundkomponenten kurz umrissen werden, die für die vorliegende Fallstudie wichtig sind. Hans J. Wulff beschreibt Filmanalyse folgendermaßen:
>"Filmanalyse" als die methodisch kontrollierte Beschäftigung mit dem einzelnen Film, mit einem spezifischen Phänomen der filmischen Struktur oder der Filmgeschichte spiegelt die Vielfalt dessen, was ein Film zur Konstitution seines Sinnpotenzials nutzt. Deshalb kann der gleiche Film zum Anlass ganz unterschiedlicher Analysen werden, die auf Hypothesen und Modellen unterschiedlicher Bezugswissenschaften aufbauen. {cite}`aa-Wulff_2011`

Nach Wulff kann es daher keine 'Rezeptbücher' für Filmanalyse geben. Die zu analysierendem Filme und die jeweils möglichen zugrundeliegenden Fragestellungen für die Analyse sind zu disparat, als dass eine standardisierte Vorgehensweise diesen gerecht werden könnte. Die Art der Analyse wird maßgeblich durch die konkreten Fragestellungen und den mit ihnen verbundenen theoretischen Annahmen bzw. filmtheoretischen Ansätzen bestimmt.

Um dennoch zumindest ansatzweise verschiedene Ausrichtungen abzustecken unterscheidet Wulff "grob zwischen drei verschiedenen Orientierungen des Interesses" {cite}`aa-Wulff_2011`, und zwar die Ausrichtung auf die:
- die Inhaltsstruktur
- die Textstruktur (im formalen Sinn)
- die Rezeption

In dieser OER wird vor allem die filmanaltische Ausrichtung auf die Textstruktur, also auf die formale Gestaltung der Filme im Mittelpunkt stehen. Wie wir noch zeigen werden sind insbesondere diese formalen Komponenten für eine automatisierte Annotation geeignet.

Auch Dietmar Kammerer stellt fest, dass die "Methoden, Verfahren und Techniken" bei der Filmanalyse nicht standardisierbar sind und es sich bei jeder Analyse um den "Vorgang der Umschrift oder Transkription" handelt {cite}`aa-Kammerer_2017`. Bestimmte Eigenschaften, formale Elemente und Strukturmerkmale von Filmen werden systematisch erfasst und in der Regel in schriftlicher Form festgehalten bzw. in diese 'übersetzt'. Dabei kann es nach Kammerer zu "zahlreichen Übersetzungsproblem[en] kommen, da bewegte Bilder und Töne sich niemals restlos im Medium der Schrift oder anderer grafischer Zeichensysteme wiedergeben lassen" {cite}`aa-Kammerer_2017`.

Für diese 'Übersetzung' werden je nach Fragestellung und Fokus der Analyse verschiedene Werkzeuge eingesetzt. Als traditionelle Hilfsmittel für diese Transkription im Rahmen der Filmanalyse nennt Patrick Vonderau das Einstellungsprotokoll und den Sequenzplan, ebenso wie Schneidetisch und Videorekorder {cite}`aa-Vonderau_2017`. Im Kontext der zunehmenden Digitalisierung seit den 1990er Jahren werden nun auch computergestützte Tools und filmanalytische Verfahren verwendet und deren Entwicklung vorangetrieben. Jan-Hendrik Bakels et al. stellen fest, dass "software-gestützte und algorithmische Methoden der Filmanalyse" die Möglichkeit bieten, "audiovisuelle Bilder empirisch zu 'vermessen'" {cite}`aa-Bakels_Grotkopp_Scherer_Stratil_2020`. Dabei müsse aber auch immer die Frage nach dem "explikativen Potential" dieser Vorgehensweise und auch deren Grenzen im Blick behalten werden. Diese Möglichkeiten und Grenzen des Vermessens und der quantitativen Auswertung von Filmen sollen auch in unserer OER ausgelotet werden.

Der Einsatz digitaler Tools und Methoden erhält vor allem mit den sich seit Beginn der 2000er-Jahre immer mehr etablierenden Digital Humanities eine neue Bedeutung. In diesem Rahmen werden "wissenschaftliche Praktiken wie Verdaten und Skalieren, Zitieren und Kontextualisieren, Messen und Abgleichen, Vernetzen und Kollaborieren" {cite}`aa-Vonderau_2017` immer prominenter. Nach Vonderau gebe es aber bisher nur wenig Berührungspunkte zwischen der Filmwissenschaft und den Digital Humanities und digitale Werkzeuge gehörten "bislang nicht zum Kanon neuer Forschungsfelder" {cite}`aa-Vonderau_2017`. Computergestützte Verfahren sieht er insgesamt nach wie vor als technische Hilfsmittel, für ihn ergäben sich dadurch aber kein anderer epistemischer Rahmen, keine neuen Gegenstände oder neue Fragestellungen.


````{margin} 
```{admonition} Hinweis
:class: hinweis
Weitere Informationen zur Annotation mit den Tools Advene und ELAN finden sich in der <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-1/Kapitel_II/toc_B.html" class="external-link" target="_blank">Fallstudie I - Bewegtes Bild</a>. 
```
````

Taylor Arnold und Lauren Tilton sprechen dagegen von einer 'A/V-Wende' die in den Digital Humanities in den letzten Jahren stattfände {cite}`aa-Arnold_Tilton_2022`. Die traditionell sehr textzentrierten Digital Humanities wenden sich nach ihnen immer mehr auch audiovisuellen Medien zu, was durch den immer besseren Zugang zu digitalen Quellen, immer leistungsfähigere Computer und die Fortschritte im Bereich der Computer Vision begünstigt wird. Immer mehr digitale Datenbanken, Sammlungen und Archive entstehen, die immer einfacher zugänglich sind. Es werden digitale Tools zur Annotation von audiovisuellen Medien entwickelt, wie etwa <a href="https://www.advene.org/" class="external-link" target="_blank">Advene</a>, <a href="https://archive.mpi.nl/tla/elan" class="external-link" target="_blank">ELAN</a>, die Tools des <a href="https://distantviewing.org/" class="external-link" target="_blank">Distant Viewing Lab</a> oder die Web-Plattform <a href="https://service.tib.eu/tibava/" class="external-link" target="_blank">TIB AV-Analytics</a>. In unserer Fallstudie werden wir mit dem Annotations-Tool <a href="https://github.com/Movie-Analytics/VIAN/releases" class="external-link" target="_blank">VIAN</a> arbeiten, auf das wir ein einem **eigenen Kapitel** noch genauer eingehen werden. Die mit diesen digitalen Tools erstellten Annotationsdaten machen als zusätzliche <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-2/recherche/metadaten.html" class="external-link" target="_blank">Metadaten</a> zum einen die audiovisuellen Inhalte dieser digitalen Ressourcen besser zugänglich und durchsuchbar, zum anderen werden die Annotationen für die Analyse von Filmen verwendet.

Doch was ist unter "Annotation" genau zu verstehen? Darauf wird im folgenden Kapitel genauer eingegangen.




## Literatur
```{bibliography}
:filter: docname in docnames
:keyprefix: aa-
```
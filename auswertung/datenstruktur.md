# Struktur der Auswertungsdaten

Für die Auswertung der Ergebnisse aus den Notebooks zur Erkennung von Einstellungen und Figuren werden deren Ausgabe-Dateien benötigt. Allerdings werden nicht alle darin enthaltene Daten für die Auswertung verwendet. Der folgende kurze Abschnitt gibt eine Übersicht über jene Werte, die tatsächlich in den Visualisierungen Anwendung finden. 

## Visualisierung der Einstellungserkennung
Für die Visualisierung der Einstellungserkennung werden sechs vergleichenden Balkendiagramme erstellt. Dabei wird ausschließlich die Datei `Filmname_shots_THRESHOLD_metadata.csv` verwendet. 

Daraus werden folgende Werte eingelesen:
- `title`: Filmtitel für die Beschriftung und alphabetische Sortierung.
- `release_year`: Erscheinungsjahr für die chronologische Sortierung und die Tooltips.
- `mean_duration_s`: Mittlere Einstellungslänge in Sekunden.
- `median_duration_s`: Mediane Einstellungslänge in Sekunden.
- `max_duration_s`: Dauer der längsten Einstellung in Sekunden.
- `min_duration_s`: Dauer der kürzesten Einstellung in Sekunden.
- `shot_count`: Anzahl der erkannten Einstellungen.
- `duration_hh_mm_ss`: Filmlaufzeit, die für die Visualisierung in Minuten umgerechnet wird.
- `video_name`: Dateiname des Videos, der zur eindeutigen Zuordnung beim Hervorheben der Balken verwendet wird.

## Visualisierung der Figurenerkennung
### Figurennetzwerk mit Gravis
Für die Erstellung des Figurennetzwerks werden drei Dateien verwendet.

**`Filmname_characters_metadata.csv`**
- `title`: Filmtitel für das Auswahlmenü.
- `frame_rate`: Bildrate des Films zur Berechnung der geschätzten Screentime.
- `skip_frames`: Anzahl übersprungener Frames zur Bestimmung des Zeitabstands zwischen untersuchten Frames.

**`Filmname_characters_frames.csv`**
- `char_name`: Name der erkannten Figur. Daraus werden die Knoten des Netzwerks gebildet und die Anzahl der Erkennungstreffer je Figur ermittelt.
- `time_s`: Zeitpunkt der Erkennung in Sekunden. Damit wird bestimmt, welche Figuren innerhalb desselben untersuchten Frames erkannt wurden und entsprechend miteinander verbunden werden.

**`Filmname_characters_annotations.csv`**
- `character`: Namen der annotierten Figuren. Diese werden bei der Vergabe der Figurenfarben berücksichtigt, damit Netzwerk und Zeitleiste dieselben Farben verwenden.

### Screentime-Zeitleiste

Für die Screentime-Zeitleiste werden zwei Dateien verwendet.

**`Filmname_characters_metadata.csv`**
- `title`: Filmtitel für das Auswahlmenü.
- `frame_rate`: Bildrate zur Berechnung der Dauer des letzten Frames eines annotierten Abschnitts.
- `frame_count`: Gesamtanzahl der Frames zur Bestimmung der vollständigen Filmlaufzeit.

**`Filmname_characters_annotations.csv`**
- `character`: Name der Figur für die Beschriftung und Farbcodierung.
- `start_s`: Beginn des annotierten Abschnitts in Sekunden.
- `end_s`: Zeitpunkt des letzten erkannten Frames in Sekunden.
- `start_hh_mm_ss`: Beginn des Abschnitts für die Tooltips.
- `end_hh_mm_ss`: Ende des Abschnitts für die Tooltips.

Aus Beginn und Ende wird unter Berücksichtigung der Dauer des letzten Frames die Screentime jedes Abschnitts berechnet. Die Figuren werden anhand ihrer aufsummierten annotierten Screentime sortiert.



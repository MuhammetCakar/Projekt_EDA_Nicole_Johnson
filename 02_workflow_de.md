# EDA: Wie und warum

> Deutsche Übersetzung von `02_workflow.md`. Das englische Original liegt im Hauptordner.

## Ziel

Die explorative Datenanalyse bringt den Kunden sofort einen Nutzen, denn sie zeigt, wie verschiedene Merkmale die Zielgröße beeinflussen (in diesem Fall die Hauspreise). Außerdem kannst du die Diagramme aus diesem Schritt in Präsentationen verwenden. Eine gute EDA ist die Grundlage für spätere Modellierung und hat direkten Einfluss auf die Qualität der Modelle, die später entstehen.

Ein bekannter Spruch in der Datenarbeit lautet **„Garbage in, garbage out“** („Müll rein, Müll raus“). Bevor du die Daten analysierst und Schlüsse ziehst, musst du sie also zuerst verstehen und so sauber wie möglich machen.

Datenbereinigung und Datenaufbereitung machen oft bis zu 70 % der Arbeit eines Data Scientists aus. Deine Aufgabe ist es hier, den Datensatz zu untersuchen und vorzubereiten. Dein Kunde möchte einen guten Überblick über die allgemeine Wohnsituation in Seattle und Umgebung bekommen und zusätzlich Empfehlungen, die auf seine Wünsche zugeschnitten sind.

![](https://thumbor.forbes.com/thumbor/711x302/https://blogs-images.forbes.com/gilpress/files/2016/03/Time-1200x511.jpg?width=960)

## Warum ist das wichtig?

„Garbage in, garbage out“ gilt nicht nur für das Modellieren, sondern auch für den Schritt, in dem du aus Daten Schlüsse und Erkenntnisse ziehst. Erkenntnisse aus falschen Daten sind nicht vertrauenswürdig. Und du möchtest, dass deine Analyse und deine Schlussfolgerung so **vertrauenswürdig** wie möglich sind.

## Allgemeine Vorgehensweise

- Data Science ist ein Prozess in Runden (iterativ): Man wiederholt und verbessert.
- Schreibe einen groben Entwurf bzw. eine To-do-Liste deines Plans mit Platzhaltern.
  - Mache nur einfache Diagramme. Investiere nur mehr Zeit in die Diagramme, die du am Ende wirklich behalten willst.
  - Die Hauptfragen sollten schon beantwortet sein → **POC** (Proof of Concept, „Machbarkeitsnachweis“)
  - Wiederholen: tiefer gehen, schöner machen, besser machen
  - Aufräumen: Lösche ruhig Dinge, die nicht mehr nützlich sind
  - Optional: Code in Funktionen verschieben

Die Arbeit hat ein **festes Zeitlimit**. Deshalb musst du anders an die Aufgabe herangehen: Arbeite in Runden (iterativ).

## Arbeitsablauf (Workflow)

Dies ist ein empfohlener Ablauf, besonders für alle, die gerade erst mit EDA anfangen.

### Die Daten verstehen

- Lade die Datei „King_County_House_prices_dataset.csv“ herunter und speichere sie in deinem Ordner `data`. Lade die Daten in einen pandas-DataFrame.
  *Hinweis: Alles, was du in den Ordner `data` legst, wird nicht auf GitHub hochgeladen, weil der Ordner in der Datei `.gitignore` steht.*
- Schau dir die beschreibende Statistik des Datensatzes an.
- Prüfe, ob Werte fehlen. Sind sie in bestimmten Spalten oder in bestimmten Zeilen gehäuft?
- Prüfe, welche Merkmale stetig (Zahlen mit vielen Werten) und welche kategorisch (Gruppen) sind.

#### Forschungsfragen und Hypothesen bilden

- *Forschungsfragen* sind Fragen, die entstehen, wenn man Vermutungen über die Wirklichkeit (die Daten) anstellt. Sie werden als Frage formuliert.
- *Hypothesen* sind Annahmen oder begründete Vermutungen über die Daten, die auf unserem Fachwissen beruhen. Du kannst eine Hypothese in der Form *„Wenn …, dann …“* oder *„Je mehr …, desto …“* formulieren. Eine Hypothese ist eine **messbare** Aussage, die du mit den Daten überprüfen kannst.
- Zu einer Forschungsfrage können mehrere Hypothesen gehören.

```text
+------------------------------------------------+-------------------------------------------------------------------+----------------------+
| Frage                                          | Hypothesen                                                        | Kennzahlen           |
+------------------------------------------------+-------------------------------------------------------------------+----------------------+
| Beeinflusst die Lage eines Hauses den Preis?   | 1. Je näher ein Haus am Stadtzentrum liegt, desto höher der Preis | - geografische Lage  |
|                                                +-------------------------------------------------------------------+----------------------+
|                                                | 2. Wenn ein Haus am Wasser liegt, dann ist der Preis höher        | - waterfront (ja/nein)|
+------------------------------------------------+-------------------------------------------------------------------+----------------------+
```

- Je konkreter deine Fragen und Hypothesen sind, desto einfacher und gezielter wird deine EDA. Mehr Beispiele findest du in diesem [Artikel](https://www.analyticsvidhya.com/blog/2020/11/an-efficient-way-of-performing-eda-hypothesis-generation/).
- Stelle dir Fragen zu den Daten, je mehr, desto besser. (Zum Beispiel: Erhöht eine größere Wohnfläche den Preis? Sind Häuser im Süden der Region teurer?) Stelle in diesem Schritt **mindestens 3 Fragen**.
- Denke an deinen Kunden und überlege dir ein paar Hypothesen, die zu „seinem“ Teil der Daten passen. Für manche Kunden sind nicht alle Daten wichtig. Wer zum Beispiel ein Haus im Stadtzentrum sucht, interessiert sich vielleicht nicht für die Vororte.

#### Die Daten erkunden

- Prüfe die Verteilungen der stetigen Merkmale, zum Beispiel mit einem Histogramm für jedes Merkmal.
- Prüfe die Verteilungen der kategorischen Merkmale mit Diagrammen oder Tabellen, die zählen, wie oft etwas vorkommt.
- Schau dir die Histogramme an und suche nach Hinweisen oder Mustern: Erkennst du Gruppen? Sind die Verteilungen schief? Gibt es Extremwerte oder Ausreißer? Wo liegt die Mitte der Daten? Musst du Daten entfernen?

#### Die Daten bereinigen

- Mit fehlenden Werten umgehen: entfernen (Zeilen oder Spalten) oder auffüllen
- Mit Extremwerten oder Ausreißern umgehen: Daten entfernen
- Daten umwandeln, wo es nötig ist, z. B. mit Logarithmus oder Wurzel, um ein Merkmal näher an eine Normalverteilung zu bringen, oder in Klassen einteilen (Binning)
- Wie viele Daten hast du weggeworfen? 😅

#### Zusammenhänge in den Daten

- Berechne die Korrelationsmatrix und stelle sie als Diagramm dar.
- Prüfe die Zusammenhänge zwischen den Werten aus deinen Hypothesen und der Zielgröße (Preis).
- Sind alle Ergebnisse so, wie du es erwartet hast, oder gibt es Überraschungen?
- Wenn es hilft, erstelle neue Merkmale, indem du vorhandene kombinierst. Beispiel: Aus Strecke und Zeit kannst du die Geschwindigkeit berechnen.

#### Deine Arbeit präsentieren

- Vergiss nicht, deine Arbeit zu dokumentieren. Benutze Markdown-Zellen im Notebook, um zu erklären, **was** du tust, **warum** du es tust, und um die Ergebnisse zu deuten.
- Zu jedem Diagramm gehört mindestens ein Satz, der sagt, was man darin sieht.
- Für deine Präsentation gibt es einen erwarteten Aufbau, der diesen Fragen folgt:
  - Wer bist du, wer ist dein Kunde?
  - Mit welchen Daten arbeitest du (Zeitraum, Ort, Größe)?
  - Überblick über die Daten
  - Vorstellung deiner 3 Haupthypothesen
  - Ergebnisse der Analyse deiner Hypothesen (mit Diagrammen bzw. Statistik)
  - Erkenntnisse und Empfehlungen für den Kunden
  - Mehr Tipps für [gute Data-Science-Präsentationen](https://www.dataknowsall.com/storytelling.html)

Mehr Informationen zum Bild unten findest du in der [EDA-Checkliste](https://github.com/neuefische/datascience-infographics/blob/main/EDA_Checklist.md).

![EDA-Checkliste](https://raw.githubusercontent.com/neuefische/datascience-infographics/main/images/EDA_Checklist.png)

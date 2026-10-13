# Erstes Projekt – Datenanalyse

> Deutsche Übersetzung von `01_assignment.md`. Das englische Original liegt im Hauptordner.

In diesem Projekt geht es um Techniken der explorativen Datenanalyse (EDA) und darum, die Ergebnisse einem Kunden zu präsentieren.

**Wenn du mit der Arbeit beginnst, folge bitte dem [Workflow](02_workflow.md). Er hilft dir, die Aufgaben erfolgreich zu lösen!**

## Die Daten

- Du benutzt die **King County Housing Data**. Dieser Datensatz enthält Informationen über Hausverkäufe in King County (USA).
- Die Daten findest du im Schema **eda** unserer Datenbank. Du kannst sie über DBeaver erreichen. Speichere die CSV-Datei bitte im Ordner **data**. Dort wird sie nicht auf GitHub hochgeladen.
- Schau dir den Datensatz in DBeaver an und finde einen **JOIN**, um die **2 Tabellen** zu verbinden.
- Die Beschreibung der Spaltennamen findest du in der Datei [`column_names.md`](column_names.md).
- Die Spaltennamen sind manchmal NICHT eindeutig:

> **Hinweis:** In der echten Arbeitswelt stößt du auf ähnliche Probleme. Normalerweise würdest du dann deine Auftraggeber nach mehr Informationen fragen. Hier nehmen wir an, dass die Person, die dir Auskunft geben könnte, die Firma verlassen hat. Du musst also selbst herausfinden und nachschlagen, was die Spaltennamen bedeuten könnten. (Google ist dein Freund ;)

## Die Aufgaben

1. Erstelle ein neues Repo mit dieser [Vorlage](https://github.com/neuefische/ds-eda-project-template).
2. Finde mit EDA bzw. statistischer Analyse **MINDESTENS 3 Erkenntnisse** über die gesamten Daten. **Eine davon soll geografisch sein.**
3. Entwickle außerdem **MINDESTENS 3 Empfehlungen** für deinen Kunden.

> **Hinweis:** Du kannst entweder die Sicht eines Käufers oder eines Verkäufers einnehmen. Wähle einen Kunden aus der Liste am Ende dieser Datei.

## Was du abgeben musst

0. Ein **neues Repository** aus der [Vorlage](https://github.com/neuefische/ds-eda-project-template).
1. Ein **gut dokumentiertes Jupyter Notebook** (ein Beispiel findest du [hier](https://www.kaggle.com/ekami66/detailed-exploratory-data-analysis-with-python)) mit deinem Code und Kommentaren, die ihn erklären. Es muss auf dein GitHub-Repository hochgeladen (gepusht) werden, damit dein Projekt abgegeben ist. Lade nicht die ganze Analyse hoch, nur den Teil, der wichtig ist! Du kannst mit dem [Start-Notebook](04_eda.ipynb) beginnen.
2. Eine **aktualisierte und ordentliche README.md** in deinem GitHub-Repository, die beschreibt, was im Repository zu finden ist. Diese Datei soll die Orientierung im Repository sein.
3. Eine **kurze Präsentation** (Keynote, PowerPoint, Google Slides oder Jupyter Slides) mit einem **groben Überblick** über deine Vorgehensweise und deine Empfehlungen für **Kunden ohne Technik-Wissen**. Die Präsentation dauert **10 Minuten**, danach gibt es **5 Minuten Diskussion**. Lade deine Folien zusätzlich als **PDF** auf GitHub hoch, damit dein Projekt vollständig ist. **Präsentiere nicht mit deinem Jupyter Notebook!**

## Die Kunden

- Wähle bitte einen Kunden aus.

> **Hinweis:** Diese Kunden sind erfunden (Ähnlichkeiten mit echten Personen sind reiner Zufall). Triff bitte Annahmen darüber, was sie auf deine Fragen antworten würden. (Zum Beispiel: Wie definierst du eine reiche Gegend? Etwa die Postleitzahlen mit den meisten Häusern in den oberen 10 %.) **Egal welche Annahmen du triffst: Schreibe sie ausdrücklich in deine Präsentation und in dein Notebook.**

| Name | Kunde | Eigenschaften |
|---|---|---|
| Thomas Hansen | Käufer | 5 Kinder, kein Geld, möchte eine nette (soziale) Gegend, Zeitpunkt?, Lage? |
| Charles Christensen | Verkäufer | Investiert mit hoher Rendite, überlegt Renovierung?, welche Gegend?, Zeitpunkt? |
| Bonnie Brown | Verkäuferin | Hat ein Haus und will bald umziehen (Zeitpunkt?), will aber hohen Gewinn in einer Mittelschicht-Gegend |
| Larry Sanders | Käufer | Am Wasser, begrenztes Budget, schöne, ruhige, aber zentrale Gegend ohne Kinder (hat selbst Kinder, will aber nicht, dass sie mit anderen Kindern spielen, wegen Keimen) |
| **Nicole Johnson** | **Käuferin** | **Lebendige, zentrale Gegend, mittlere Preisklasse, richtiger Zeitpunkt (innerhalb eines Jahres)** |
| Jennifer Montgomery | Käuferin | Hohes Budget, will angeben, Zeitpunkt innerhalb eines Monats, am Wasser, renoviert, hohe Bewertung, will innerhalb 1 Jahres weiterverkaufen |
| Bonnie Williams | Verkäuferin | Hat mehrere Häuser, einige in schlechten Gegenden, bereit, Mieter rauszuwerfen, Zeitpunkt?, hohe Rendite, offen für Renovierungen |
| William Rodriguez | Käufer | 2 Personen, Landhaus (bester Zeitpunkt & unrenoviert) und Stadthaus (schnell & zentrale Lage), will zwei Häuser |
| Erin Robinson | Käuferin | Investiert in arme Gegend, kaufen & verkaufen, Kosten zurück + kleiner Gewinn, sozial verantwortlich |
| Jacob Phillips | Käufer | Unbegrenztes Budget, 4+ Badezimmer oder kleineres Haus in der Nähe, großes Grundstück (Tennisplatz & Pool), Golf, historisch, nicht am Wasser |
| Zachary Brooks | Verkäufer | Investiert in historische Häuser, beste Gegenden, hohe Gewinne, bester Zeitpunkt innerhalb eines Jahres, renovieren? |
| Timothy Stevens | Verkäufer | Besitzt teure Häuser im Zentrum, muss sie loswerden, bester Zeitpunkt innerhalb eines Jahres, offen für Renovierung, wenn der Gewinn steigt |
| Amy Williams | Verkäuferin | Mafiosa, verkauft nach und nach mehrere zentrale Häuser (Top 10 %), braucht nach und nach durchschnittliche Häuser am Stadtrand, um sich vor dem FBI zu verstecken |

# Ein Zuhause für Nicole – EDA mit dem King-County-Datensatz

Projekt aus der Data-Science-Projektwoche bei neue fische.
Student: Muhammet Cakar

## Die Kundin

**Nicole Johnson** möchte ein Haus kaufen. Ihre Wünsche:
- eine lebendige, zentrale Gegend
- mittleren Preisklasse
- Kauf innerhalb eines Jahres

**Frage:** Wo findet Nicole ein zentrales Haus zu einen passenden Preis, und wann kauft sie am besten?

## Die Daten

- Rund 21.600 Hausverkäufe in King County (Region Seattle, USA)
- Zeitraum: Mai 2014 bis Mai 2015
- 21 Angaben pro Haus, z. B. Preis, Datum, Größe und Lage
- Bereinigung: keine Duplikate, ein Haus mit 33 Schlafzimmern entfernt (Tippfehler), Datum ins richtige Format gebracht

## Meine Annahmen

- **Zentral** = höchstens 10 km Luftlinie vom Stadtzentrum Seattle
- **Mittlere Preisklasse** = die mittlere Hälfte aller Preise (322.000 bis 645.000 Dollar)
- **Kauf in einem Jahr** = Prüfung, in welchem Monat die Preise am niedrigsten sind

## Drei Hypothesen und Ergebnisse

| Nr. | Hypothese | Ergebnis |
|---|---|---|
| 1 | Je näher am Zentrum, desto teurer ist ein Haus. | ✅ Bis 10 km: ca. 555.000 Dollar, weiter draußen: ca. 416.000 Dollar |
| 2 | Im Winter sind Häuser günstiger als im Sommer. | ✅ Winter: ca. 430.000 Dollar, Sommer: ca. 455.000 Dollar (auch pro m² günstiger) |
| 3 | Es gibt zentrale Häuser in Nicoles Preisklasse. | ✅ 2.990 von 5.629 zentralen Häusern passen (53 %) |

## 3 Highlights

1. Zentral wohnen kostet mehr.
2. Im Winter sind Häuser etwas günstiger (nur ein Jahr Daten, also ein Hinweis, keine Garantie).
3. Die passenden Häuser liegen nördlich und südlich der Innenstadt (geografische Erkenntnis).

## 3 Empfehlungen für Nicole

1. Gezielt in diesen Postleitzahlen suchen: 98103, 98115, 98117, 98118, 98144
2. Ein Budget von 322.000 bis 645.000 Dollar einplanen
3. Den Kauf für Dezember bis Februar planen, den April eher meiden

## Dateien im Projekt

| Datei | Inhalt |
|---|---|
| `04_eda_de.ipynb` | Die komplette Analyse (Notebook) |
| `03_fetching_the_data_eda.ipynb` | Daten aus der Datenbank laden |
| `Praesentation_Nicole_Johnson.pdf` | Die Präsentation für die Kundin |
| `column_names.md` | Erklärung der Spalten |
| `*_de.md` | Deutsche Übersetzungen der Aufgabe |

## So startest du das Projekt

1. Repository klonen
2. Virtuelle Umgebung anlegen und aktivieren
3. Pakete installieren: `pip install pandas matplotlib seaborn psycopg2-binary sqlalchemy python-dotenv ipykernel`
4. Eine `.env`-Datei mit den Zugangsdaten zur Datenbank anlegen (wird nicht hochgeladen)
5. Erst `03_fetching_the_data_eda.ipynb` ausführen, dann `04_eda_de.ipynb`

## Werkzeuge

Python, Pandas, Matplotlib, SQL (PostgreSQL), DBeaver, VS Code, Git und GitHub
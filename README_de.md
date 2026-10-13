# King County Housing EDA – Projektvorlage (deutsche Version)

> Dies ist die deutsche Übersetzung der Datei `README.md` aus der neue-fische-Vorlage. Das englische Original liegt im Hauptordner.

Dies ist die Startvorlage für das Projekt **Explorative Datenanalyse (EDA)**. Du arbeitest mit dem King-County-Datensatz (Hausverkäufe in und um Seattle, USA), findest heraus, was die Hauspreise beeinflusst, und machst aus deinen Ergebnissen Erkenntnisse und Empfehlungen für einen Kunden, den du selbst auswählst.

## Lernziele

Am Ende dieses Projekts solltest du Folgendes können:

- Dich mit Python mit einer PostgreSQL-Datenbank verbinden und die Ergebnisse einer Abfrage in einen pandas-DataFrame laden.
- Eine explorative Datenanalyse rund um klare Forschungsfragen und Hypothesen aufbauen.
- Einen echten Datensatz bereinigen und aufbereiten: fehlende Werte, Ausreißer und Umwandlungen von Spalten behandeln.
- Verteilungen und Zusammenhänge zwischen den Spalten und der Zielgröße (Preis) untersuchen.
- Deine Analyse in mindestens drei Erkenntnisse und drei kundenspezifische Empfehlungen übersetzen.
- Deine Arbeit einem Publikum ohne Technik-Wissen präsentieren.

## Lernpfad

Arbeite die Dateien der Reihe nach durch. Beginne mit der Aufgabenstellung, um das Ziel zu verstehen. Nutze den Workflow als Wegweiser. Hole dann die Daten und mache deine Analyse im EDA-Notebook.

> **Tipp:** Die Daten liegen im Schema **eda** der Datenbank und sind auf **zwei Tabellen** verteilt. Bevor du irgendetwas mit Code holst, verbinde dich mit DBeaver und erkunde dieses Schema: Schau dir beide Tabellen an, lies in den [**Spaltennamen**](column_names.md) nach, was jedes Feld bedeutet, und finde heraus, wie man die Tabellen verbindet. Wenn dein `JOIN` funktioniert, benutze ihn als Abfrage in [**03 – Daten holen**](03_fetching_the_data_eda.ipynb), um den verbundenen Datensatz in pandas zu laden.

| Datei / Ordner | Beschreibung |
|---|---|
| [**01 – Aufgabenstellung**](01_assignment.md) | Der Projektauftrag: Datensatz, Aufgaben, Abgaben und die Liste der Kunden zur Auswahl. |
| [**02 – Workflow**](02_workflow.md) | Ein empfohlener EDA-Ablauf: Daten verstehen und hinterfragen, bereinigen, Zusammenhänge finden, präsentieren. |
| [**03 – Daten holen**](03_fetching_the_data_eda.ipynb) | Mit psycopg2 und SQLAlchemy mit der PostgreSQL-Datenbank verbinden und die Daten in einen pandas-DataFrame holen. |
| [**04 – EDA**](04_eda.ipynb) | Start-Notebook für deine explorative Datenanalyse. |
| [**Spaltennamen**](column_names.md) | Datenwörterbuch: beschreibt jede Spalte im King-County-Datensatz. |

### Weitere Ordner und Dateien

| Datei / Ordner | Beschreibung |
|---|---|
| **data/** | Hier speicherst du die CSV-Datei mit dem Datensatz. Der Ordner selbst ist in Git, aber die Datendateien darin werden nicht hochgeladen. |
| **.env.example** | Vorlage für die Zugangsdaten zur Datenbank. Kopiere sie nach `.env` und trage deine Werte ein. |
| **pyproject.toml** | Projekt-Einstellungen und benötigte Pakete. |
| **uv.lock** | Datei, die die genauen Paket-Versionen festhält. |

## Einrichtung

> **Hinweis:** In allen Schritten ist Text in spitzen Klammern wie `<repo-name>` ein **Platzhalter**. Ersetze ihn, **inklusive** der Klammern `< >`, durch deinen eigenen Wert. Beispiel: `cd <repo-name>` wird zu `cd ds-eda-project-template`.

### 1. Repository aus der Vorlage erstellen

Klicke auf GitHub auf **Use this template**.

Beim Erstellen des Repositorys:

- Setze dich selbst als **Owner** (Besitzer)
- Wähle einen Namen für das Repository
- Schalte **Include all branches** aus
- Klicke auf **Create repository**

> **Wichtig:** Wenn ihr zu zweit oder in Gruppen arbeitet, macht diesen Schritt nur **eine Person**.

---

### 2. Mitarbeitende hinzufügen (nur bei Paaren/Gruppen)

Wenn du mit anderen zusammenarbeitest:

1. Öffne das Repository auf GitHub
2. Gehe zu **Settings → Collaborators**
3. Füge deine Teammitglieder als Collaborators hinzu
4. Teile den Link zum Repository mit deinem Team

Die Teammitglieder müssen die Einladung annehmen, bevor es weitergeht.

---

### 3. Repository klonen

Kopiere die SSH-Adresse über den Knopf **Code** auf GitHub und führe dann aus:

```bash
git clone <kopierte-ssh-adresse>
```

Die kopierte SSH-Adresse sieht so aus: `git@github.com:<dein-benutzername>/<repo-name>.git`.

---

### 4. In den Projektordner wechseln und Pakete installieren

Dieser Schritt installiert alle benötigten Pakete und legt eine virtuelle Umgebung im Ordner `.venv/` an.

```bash
cd <repo-name>
uv sync
```

> **Tipp:** Du brauchst ein Paket, das noch nicht installiert ist (zum Beispiel für Karten)? Füge es mit `uv add <paketname>` hinzu. Das aktualisiert `pyproject.toml` und `uv.lock` und installiert es in deine `.venv`. Committe beide Dateien. Teammitglieder führen nach dem Pull `uv sync` aus und haben dann dieselbe Umgebung.

---

### 5. Zugangsdaten zur Datenbank einrichten

Das Notebook zum Daten-Holen liest die Verbindungsdaten aus einer Datei namens `.env`. Kopiere die Vorlage und trage deine eigenen Werte ein:

```bash
cp .env.example .env
```

Öffne `.env` und ersetze die Platzhalter durch die Zugangsdaten für die King-County-Datenbank (dieselben, die du in DBeaver benutzt). Diese Werte werden in [**03 – Daten holen**](03_fetching_the_data_eda.ipynb) verwendet.

> **Achtung:** `.env` enthält Geheimnisse (Passwörter) und darf **niemals** committet werden. Sie steht bereits in `.gitignore`. Nur `.env.example` mit Platzhaltern gehört ins Repository.

---

### 6. Die Notebooks öffnen

> **Hinweis:** Öffne VS Code unbedingt im Hauptordner des Projekts. Nur dann erkennt VS Code automatisch die Umgebung, die `uv sync` angelegt hat.

Starte VS Code im Hauptordner des Projekts:

```bash
code .
```

Öffne dann ein Notebook und wähle als Kernel die Python-Umgebung, die `uv sync` angelegt hat.

## Quellen und weiterführende Links

- [**House Sales in King County – Datensatz**](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction): Der Original-Datensatz mit Spaltenbeschreibungen und Notebooks der Community.
- [**Pandas-Benutzerhandbuch**](https://pandas.pydata.org/docs/user_guide/index.html): Die offizielle Anleitung zur Datenbearbeitung mit pandas.
- [**Seaborn-Tutorial**](https://seaborn.pydata.org/tutorial.html): Statistische Diagramme mit Python.
- [**SQLAlchemy-Dokumentation**](https://docs.sqlalchemy.org/en/20/): Das Datenbank-Werkzeug, mit dem du PostgreSQL aus Python abfragst.
- [**Hypothesen für die EDA bilden**](https://www.analyticsvidhya.com/blog/2020/11/an-efficient-way-of-performing-eda-hypothesis-generation/): Wie man Forschungsfragen und Hypothesen formuliert, bevor man in die Daten einsteigt.
- [**EDA-Checkliste**](https://github.com/neuefische/datascience-infographics/blob/main/EDA_Checklist.md): Eine Checkliste, Phase für Phase, für eine explorative Analyse.
- [**Ausführliche EDA mit Python**](https://www.kaggle.com/code/ekami66/detailed-exploratory-data-analysis-with-python): Ein durchgearbeitetes Beispiel für ein gründliches EDA-Notebook mit echten Daten.
- [**Tipps für Data-Science-Präsentationen**](https://www.dataknowsall.com/storytelling.html): Storytelling-Techniken, um Ergebnisse einem Publikum ohne Technik-Wissen zu präsentieren.

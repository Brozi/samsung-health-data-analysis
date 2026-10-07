# Samsung Health Data Analysis

Projekt w formie notatnika Jupyter (`csv-project.ipynb`) do wczytania, wstępnego czyszczenia i analizy danych z pliku CSV wyeksportowanego z aplikacji Samsung Health — w szczególności danych dotyczących **poziomu stresu** w czasie.

## Co robi notebook?

Notebook wykonuje m.in.:

- wczytanie danych z pliku CSV do `pandas.DataFrame`,
- wybór interesujących kolumn (m.in. czasy pomiaru oraz `Max`, `Min`, `Score`),
- sprawdzenie zakresu wartości `Score`,
- obsługę braków danych:
  - wartości `NaN` w kolumnach liczbowych są wykrywane,
  - rekordy z brakami są odfiltrowywane (usuwane),
- konwersję kolumn z datami do typu `datetime`,
- sortowanie danych po czasie rozpoczęcia pomiaru,
- wizualizacje:
  - wykres `Score` w całym zakresie czasowym,
  - wykresy w wybranych przedziałach dat (przybliżenia / „zoom”),
  - wykrywanie i podgląd zakresów z brakującymi danymi,
  - **średnia krocząca** (rolling mean) dla `Score` (w notebooku ustawione jako okno 365).

## Struktura repozytorium

- `csv-project.ipynb` — główny notatnik z analizą.
- `data/` — katalog na plik CSV z danymi wejściowymi.
- `README.md` — opis projektu.

## Wymagania

Notebook używa Pythona oraz bibliotek:

- `pandas`
- `matplotlib`

(Notebook importuje też `math` i `datetime`.)

## Jak uruchomić

1. Sklonuj repozytorium:
   ```bash
   git clone https://github.com/Brozi/ked-project-csv.git
   cd ked-project-csv
   ```

2. Umieść plik z danymi w katalogu `data/` (lub dostosuj ścieżkę w notebooku).
   Domyślna ścieżka w notatniku:
   - `data/samsung-health-stress-data.csv`

3. Uruchom Jupyter Notebook / Jupyter Lab:
   ```bash
   jupyter lab
   ```
   albo:
   ```bash
   jupyter notebook
   ```

4. Otwórz `csv-project.ipynb` i uruchom komórki.

## Dane wejściowe (format)

Notebook zakłada, że plik CSV zawiera kolumny odpowiadające m.in.:

- `Start time`
- `Update time`
- `Create time`
- `End time`
- `Max`
- `Min`
- `Score`

Jeżeli Twój eksport ma inne nazwy/układ kolumn, dostosuj parametry `read_csv(...)` w notebooku (np. `usecols`, `names`).

## Wyniki

Wynikiem są wydruki kontrolne w konsoli (np. podgląd końcowych rekordów, zakres wartości, rekordy z brakami) oraz wykresy pokazujące zmianę poziomu stresu (`Score`) w czasie, w tym wygładzony trend (średnia krocząca).

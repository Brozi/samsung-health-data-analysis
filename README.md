# Samsung Health Data Analysis

A Jupyter Notebook project for loading, cleaning, exploring, and visualizing stress data exported from Samsung Health as a CSV file.

This project demonstrates a practical data-analysis workflow using **Python**, **pandas**, and **Matplotlib**—from raw exported data to time-based insights and visualizations.

## Project Highlights

- Imports Samsung Health CSV data into a `pandas.DataFrame`
- Selects and inspects relevant measurement fields, including:
  - Measurement timestamps
  - `Max`
  - `Min`
  - `Score`
- Checks the range and basic quality of `Score` values
- Detects missing values in numeric columns
- Removes incomplete records where required for the analysis
- Converts timestamp columns to `datetime`
- Sorts measurements chronologically
- Visualizes stress-score trends over time
- Creates focused date-range views for closer inspection
- Identifies periods with missing measurements
- Calculates a rolling mean to smooth the `Score` time series

## Repository Contents

- `csv-project.ipynb` — the main analysis notebook
- `data/` — directory for the input CSV file
- `README.md` — project documentation

## Technologies

- Python
- Jupyter Notebook / JupyterLab
- pandas
- Matplotlib

The notebook also uses Python's built-in `math` and `datetime` modules.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Brozi/samsung-health-data-analysis.git
cd samsung-health-data-analysis
```

### 2. Add the input data

Place your Samsung Health export in the `data/` directory. The notebook expects the following default path:

```text
data/samsung-health-stress-data.csv
```

If your file has a different name or location, update the path in `csv-project.ipynb`.

### 3. Launch Jupyter

```bash
jupyter lab
```

Alternatively:

```bash
jupyter notebook
```

### 4. Run the notebook

Open `csv-project.ipynb` and execute the cells from top to bottom.

## Expected Input Format

The CSV file should contain columns corresponding to the following fields:

- `Start time`
- `Update time`
- `Create time`
- `End time`
- `Max`
- `Min`
- `Score`

Samsung Health exports may differ depending on the application version or export settings. If your file uses different column names or an alternate structure, adjust the `pandas.read_csv(...)` configuration in the notebook, including options such as `usecols` or `names`.

## Output

The notebook produces:

- Data-inspection output, including sample records and value ranges
- Missing-data diagnostics
- Time-series charts of stress `Score`
- Date-range visualizations for detailed exploration
- A rolling-average trend line for identifying longer-term patterns

## Why This Project

This project showcases core data-analysis skills in a realistic, personal-data context:

- Working with semi-structured exported data
- Cleaning and validating raw datasets
- Handling missing values
- Transforming date and time fields
- Creating clear, purposeful visualizations
- Using rolling statistics to reveal trends in noisy time-series data

# 📊 E-commerce Big Data Analysis with PySpark

This repository contains practice projects focused on large-scale data processing and analytical reporting using tools like PySpark, DuckDB, and Quarto.
Each project explores realistic e-commerce scenarios and produces polished business reports (HTML/PDF).

## 🚀 Features
- PySpark for distributed large-scale data analysis
- DuckDB for fast, in-process, column-store analytics
- Quarto for reproducible, professional-grade reporting
- Custom Quarto theme inspired by Arrakis Night (PyCharm)

## 🔄 Workflow

1. Generate a large synthetic e-commerce dataset using
./data/generate_bigdata.py.
2. Explore and analyze the dataset in the notebooks in ./scripts/.
3. Render the final business reports (HTML/PDF) via Quarto.
4. View rendered reports in ./docs or directly through GitHub Pages.

## 📁 Reports

Currently available:
- PySpark E-commerce Business Report
> https://dfeyerabend.github.io/ecommerce_pyspark_project/E-commerce_pyspark_report.html

---

## 🌳 Project Structure
A quick overview of the repository layout and where each component lives:

```text
pyspark_analyse/
├─ data/
│  └─ generate_bigdata.py       # Script to generate the big data CSV (not tracked in git due to size)
├─ docs/
│  └─ E-commerce_pyspark_report.html    # Rendered HTML report (published via GitHub Pages)
├─ scripts/
│  ├─ E-commerce_pyspark_report.ipynb   # Main analysis & reporting notebook
├─ themes/
│  ├─ plot_arrakis_night_style.py        # Custom plotting style helper
│  └─ quarto_arrakis-night.scss          # Custom Quarto theme (Arrakis Night based)
├─ requirements.txt                      # Python dependencies for analysis
└─ README.md                             # This file
```

---

## 📈 Data Generation

- The dataset used in this project is **synthetic** and generated locally. The raw CSV (~345 MB) is **not committed to the repository** to keep the repo size reasonable.
- Instead, you should generate your own dataset before running the analysis.

To generate (or regenerate) the data:

1. Make sure your Python environment is activated.
2. Run the generator script:

```bash
python .\data\generate_bigdata.py
```

- This will create (or overwrite) `data/ecommerce_5m.csv` with a large number of simulated e-commerce transactions (~345 MB by default).

---

## 🔧 Installation & Environment Setup

- Python dependencies for the analysis are listed in `requirements.txt`:
- Install them into your environment, for example with `pip`:

```bash
pip install -r requirements.txt
```

> Note: This project assumes you have a working local PySpark setup. Depending on your platform, you may need to install Java and/or configure Spark separately.

---

## 📈 Quarto Report Generation

The final HTML report is rendered with **[Quarto](https://quarto.org/)** from the notebook `scripts/E-commerce_pyspark_report.ipynb`.

### 1. Install Quarto

Quarto is not installed via `requirements.txt`; you need to install it separately.

On Windows, download the installer from the official website or use `winget`:

```bash
winget install quarto.quarto
```

(Alternatively, see https://quarto.org/docs/get-started/ for OS-specific instructions.)

### 2. Render the Report

Once Quarto is installed and your Python environment is set up **and the data has been generated**:

```bash
quarto render .\scripts\E-commerce_pyspark_report.ipynb --to html --output-dir docs
```

This will:

- Execute the notebook
- Apply the custom `quarto_arrakis-night.scss` theme
- Write/update `docs/E-commerce_pyspark_report.html` (used by GitHub Pages)
- Store supporting assets in `scripts/E-commerce_business_report_files/`

---

## 🌙 Custom Theme (Arrakis Night)

The visual style of the report is based on the **Arrakis Night** theme from PyCharm, adapted for Quarto:

- `themes/quarto_arrakis-night.scss` defines the Quarto page theme (colors, typography, code blocks, etc.).
- `themes/plot_arrakis_night_style.py` provides a Python helper to align Matplotlib plots with the same visual style.

---

## How to Use This Project

If you want to reproduce or modify the analysis:

1. Clone this repo.
2. Create and activate a Python virtual environment.
3. Install Python dependencies: `pip install -r requirements.txt`.
4. Generate the dataset: `python .\data\generate_bigdata.py`
5. Install Quarto and render the report: `quarto render .\scripts\E-commerce_pyspark_report.ipynb --to html --output-dir docs`.

Feel free to adapt the data generation, analysis logic, or theming for your own experiments or reports.

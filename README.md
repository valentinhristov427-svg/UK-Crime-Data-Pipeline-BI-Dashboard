# UK Crime Data Pipeline & BI Dashboard

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Power BI](https://img.shields.io/badge/Power_BI-Desktop-F2C811?style=flat&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Pandas](https://img.shields.io/badge/Data_Processing-Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

An end-to-end ETL analytics pipeline and interactive Power BI dashboard analyzing 36 months of street-level crime data across four UK police forces (Metropolitan, West Midlands, Northumbria, and Surrey). The project integrates ONS population estimates, Index of Multiple Deprivation (IMD), and geospatial boundary datasets to perform population-weighted regression and evaluate systemic crime drivers.

---

## Repository Structure

```text
.
├── Cleaned Data/                     # Processed, aggregated outputs for BI consumption
│   ├── force_crime-type_month_grain.csv
│   ├── lad_crime_summary.csv
│   ├── lad_crime-type_month_grain.csv
│   ├── lad_rate_slopes.csv
│   └── lsoa_crime-type_month_grain.csv
├── Deliverables/                     # Final presentation, reports, and Power BI report
│   ├── Dashboard Overview Document.pdf
│   ├── Police Dashboard Valentin.pbix
│   └── Presentation Powerpoint.pdf
├── Original Data/                    # Raw inputs and enrichment sources
│   ├── Enrichment Datasets/          # ONS population, IMD deprivation, and boundary mappings
│   └── Full June 2023 - May 2026 Police datasets/ # 36 months of raw police force CSVs
│       ├── 2023-06/                  # Metropolitan, Northumbria, Surrey, West Midlands
│       ├── ...
│       └── 2026-05/
├── Dashboard Page 1.png              # Executive Overview screenshot
├── Dashboard Page 2.png              # Geographic & Temporal Trends screenshot
├── Dashboard Page 3.png              # Deprivation Regression & Outlier Analysis screenshot
├── Data Cleaning Documentation.pdf   # Technical ETL methodology and data dictionary
├── Data Cleaning Notebook.ipynb      # Jupyter Notebook executing the complete Python ETL pipeline
└── README.md                         # Project documentation
```

---

## Key Features & Analytical Insights

* **End-to-End Python ETL Pipeline:** Cleaned, transformed, and aggregated 36 months (June 2023 – May 2026) of raw police data across multiple granularities (LSOA, Local Authority District, and Police Force levels) via `Data Cleaning Notebook.ipynb`.
* **Multi-Source Data Integration:** Combined police records with ONS population benchmarks, Local Authority District (LAD) boundaries, and Index of Multiple Deprivation (IMD) metrics.
* **Population-Weighted Regression:** Applied weighted statistical models to quantify the relationship between local deprivation levels and crime rates per capita.
* **Key Analytical Findings:**
  * **Seasonal Cycles:** Identified recurring summer spikes across violent and public order offenses.
  * **Regional Divergence:** Discovered a Metropolitan-specific rise in violent crimes contrasting against broader downward trends across Northumbria, Surrey, and West Midlands.
  * **Footfall Anomaly Detection:** Highlighted significant borough-level outliers where high crime per resident ratio was heavily skewed by non-residential footfall (commuters and tourists).
* **3-Page Interactive Power BI Dashboard:** Built a dynamic report leveraging advanced DAX for custom measure calculations, dynamic trend mapping, and multi-level drill-throughs.

---

## Dashboard Preview

### Page 1: Executive Overview
![Dashboard Page 1](Dashboard%20Page%201.png)

### Page 2: Geographic & Temporal Analysis
![Dashboard Page 2](Dashboard%20Page%202.png)

### Page 3: Deprivation & Statistical Drivers
![Dashboard Page 3](Dashboard%20Page%203.png)

---

## Quick Start Guide

### Prerequisites
* **Python 3.10+** & **Jupyter Notebook** (or JupyterLab / VS Code Notebook Extension)
* **Python Packages:** `pandas`, `numpy`, `scipy`, `matplotlib`
* **Power BI Desktop** (to open and interact with `.pbix` files)

### Pipeline & Dashboard Execution

1. **Clone the Repository**
   ```bash
   git clone [https://github.com/your-username/uk-crime-pipeline-dashboard.git](https://github.com/your-username/uk-crime-pipeline-dashboard.git)
   cd uk-crime-pipeline-dashboard
   ```

2. **Run the ETL Pipeline**
   Open and execute `Data Cleaning Notebook.ipynb` in Jupyter to process raw files from `Original Data/` and reproduce the output files in `Cleaned Data/`:
   ```bash
   jupyter notebook "Data Cleaning Notebook.ipynb"
   ```

3. **Open the Power BI Report**
   Navigate to `Deliverables/Police Dashboard Valentin.pbix` and open it in Power BI Desktop to interact with the visual dashboard and DAX metrics.

4. **Review Technical Documentation**
   Consult `Data Cleaning Documentation.pdf` for a detailed breakdown of mapping logic, schema definitions, and cleaning routines.

---

## Tech Stack

* **Python & Jupyter** - Data Extraction, Transformation, Aggregation & Regression Analysis
* **Pandas & NumPy** - Data Wrangling & Multi-Grain Aggregations
* **Power BI & DAX** - Interactive Visualizations & Dynamic Business Intelligence Metrics

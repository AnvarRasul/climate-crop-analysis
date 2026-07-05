# Climate Change Impact on Agriculture — Data Analysis & GIS

A complete end-to-end data analysis pipeline examining the relationship 
between climate change and agricultural crop yields across 10 countries 
spanning 35 years (1990–2024).

---

## Project Overview

This project was built to demonstrate a full data analyst and GIS analyst 
workflow — from raw data loading and cleaning, through statistical testing, 
to spatial visualization and database storage.

**Dataset:** Climate Change Impact on Agriculture (Kaggle)  
**Records:** 10,000 rows × 15 features  
**Countries:** Argentina, Australia, Brazil, Canada, China, France, 
India, Nigeria, Russia, USA  
**Period:** 1990–2024  

---

## Key Questions Answered

- Which climate factor most strongly predicts crop yield?
- Do adaptation strategies significantly improve yield outcomes?
- How does irrigation access affect yield in Central Asia-relevant crops?
- How is agricultural economic impact distributed geographically?
- Which temperature zones dominate the major agricultural countries?

---

## Project Structure
climate-crop-analysis/
├── data/
│   └── climate_change_impact_on_agriculture_2024.csv
├── notebooks/
│   ├── 01_eda_cleaning.ipynb          # Data exploration & feature engineering
│   ├── 02_statistical_analysis.ipynb  # Correlation, t-tests, p-values
│   ├── 03_visualization.ipynb         # 6 professional charts
│   └── 04_gis_mapping.ipynb           # 3 world maps + PostGIS pipeline
├── outputs/
│   ├── charts/                        # PNG exports from notebook 3
│   └── maps/                          # PNG exports from notebook 4
├── .env                               # Database credentials (not pushed)
├── .gitignore
├── requirements.txt
└── README.md

---

## Notebooks

### 01 — EDA & Cleaning
- Missing value report with percentage breakdown
- Feature engineering: Decade, Yield_Category, High_Stress flag, 
  Temperature Zone, Water Score
- Dataset written to PostgreSQL for persistent storage

### 02 — Statistical Analysis
- Pearson correlation between 5 climate factors and crop yield
- T-test: adapted vs non-adapted farms
- T-test: high vs low irrigation access (Central Asia crops)
- Written thesis-style conclusions for each finding

### 03 — Visualization
- Boxplot: yield distribution by crop type
- Scatter: temperature vs yield with regression line
- Line chart: yield trends by decade per crop
- Bar chart: adaptation strategy effectiveness
- Heatmap: climate factors correlation matrix
- Combined distribution charts

### 04 — GIS Mapping
- Choropleth map: average crop yield by country
- Bubble map: agricultural economic impact by country
- Categorical map: temperature zones by country
- Spatial data written to PostGIS and verified

---

## Key Statistical Findings

| Factor | Correlation with Yield | Significant |
|--------|----------------------|-------------|
| Temperature | r = 0.26 | Yes (p < 0.001) |
| Precipitation | r = 0.03 | Yes (p < 0.01) |
| CO2 Emissions | r = -0.09 | Yes (p < 0.001) |
| Soil Health | r = -0.01 | No |
| Extreme Weather | r = -0.01 | No |

Temperature is the only climate factor with meaningful (though weak) 
correlation with crop yield. No single factor dominates — agricultural 
productivity is driven by multivariate interactions.

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.13 | Core language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib + Seaborn | Visualization |
| SciPy | Statistical testing |
| GeoPandas | Spatial data handling |
| PostgreSQL + PostGIS | Spatial database |
| SQLAlchemy | Database connection |
| python-dotenv | Credential management |

---

## Setup & Usage

```bash
# Clone the repository
git clone https://github.com/AnvarRasul/climate-crop-analysis.git
cd climate-crop-analysis

# Install dependencies
pip install -r requirements.txt

# Create .env file with your database credentials
echo "DATABASE_URL=postgresql://user:password@localhost:5432/data_analysis" > .env

# Launch Jupyter
jupyter lab
```

Run notebooks in order: 01 → 02 → 03 → 04

---

## Author

**Anvar Rasul**  
GIS Specialist & Remote Sensing Data Analyst  
Master's student in Remote Sensing and GIS — Beihang University, Beijing  
GitHub: github.com/AnvarRasul
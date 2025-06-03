# 🌊 Global Fisheries Production Dataset (1950–2024)

This repository documents the cleaning and preparation of a historical fisheries production dataset, covering over a century of global data by country and species.

---

## 📦 Dataset Overview

- **Source**: Internal Fisheries Production Database (1950–2024)
- **Format**: Excel/CSV
- **Original Dimensions**: ~28,000+ rows, 150+ columns
- **Structure**:
  - **Country Name**
  - **Species Name**
  - **Continent**
  - **Unit (Tonnes - Lives Weight)**
  - **Year-by-Year Production Data**

---

## 🧹 Data Cleaning Summary

### Issues Identified:
1. **Wide Format**:
   - Years (1950–2024) stored as column names.
   - Converted to long format using `pd.melt()`.

2. **Missing Continent Information**:
   - Some entries lacked continent names due to legacy country names (e.g., USSR).
   - USSR did not map to modern continent categories.

3. **Legacy Data (USSR)**:
   - USSR data was moved to a separate DataFrame (`df_ussr`) and excluded from the main dataset (`df_long_cleaned`) to maintain geographic consistency.
   - Saved separately for potential historical analysis.

---

### Cleaning Steps:
- Renamed and standardized column names
- Melted wide data into long format
- Removed or separated special cases (USSR)
- Checked for:
  - Missing values
  - Unexpected country names
  - Data type mismatches

---

## 📁 Repository Structure


📦 fisheries-cleaning-project/
├── data/
│ ├── raw/ # Original dataset
│ ├── processed/
│ │ ├── df_long_cleaned.csv # Cleaned dataset (no USSR)
│ │ └── df_ussr.csv # USSR data only
├── notebooks/
│ └── data_cleaning.ipynb # All cleaning steps in Python
├── README.md # This file



---

## 📊 Next Steps

- [ ] Conduct Exploratory Data Analysis (EDA)
- [ ] Visualize production trends by continent and species
- [ ] Model forecasting trends or sustainability patterns
- [ ] Share findings in an interactive dashboard (optional)

---

## 🤝 Credits

Created by tojangeng262, a fisheries graduate transitioning into data analytics.

This project is part of a professional data portfolio aimed at showcasing real-world data wrangling skills using Python, pandas, and GitHub best practices.

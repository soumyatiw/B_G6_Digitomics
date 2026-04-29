# Digitomics

## Overview
Digitomics is a data-driven project that analyzes how students' digital behavior impacts their academic performance, mental wellbeing, and financial decisions.

With the rise of social media, short-form content, and online learning, this project explores whether digital consumption is helping or harming students.

---

## Problem Statement
Understanding and quantifying the impact of digital consumption on students' academic performance, mental health, and behavioral outcomes.

---

## Objectives
- Analyze relationship between digital usage and productivity
- Study impact of social media and short videos on attention span
- Evaluate effects of late-night usage on mental health
- Identify patterns leading to digital addiction
- Understand influence of ads on impulsive spending

---

## Dataset
The dataset contains student-level data including:
- Demographics (age, gender, country)
- Digital behavior (screen time, sessions, content type)
- Academic metrics (study hours, productivity, attendance)
- Mental health indicators (stress, anxiety, depression)
- Financial behavior (spending, impulse purchases)

**Raw file:** `data/raw/student_digital_behaviour_data.csv`  
**Processed file:** `data/processed/cleaned_data.csv` (~100,000 rows after sampling)

### Dataset Link
[Kaggle – Student Social Media Impact Dataset](https://www.kaggle.com/datasets/nitikachandel95/student-social-media-impact-dataset/data)

---

## Repository Structure

```
B_G6_Digitomics/
├── data/
│   ├── raw/                        # Original dataset (CSV)
│   └── processed/                  # Cleaned output (cleaned_data.csv)
├── docs/
│   └── data_dictionary.md          # Column-level data documentation
├── notebooks/
│   ├── 01_extraction.ipynb         # Data loading & sampling
│   ├── 02_cleaning.ipynb           # Null handling, encoding, Winsorization
│   ├── 03_eda.ipynb                # Exploratory Data Analysis
│   ├── 04_statistical_analysis.ipynb # Correlation, hypothesis testing
│   └── 05_final_load_prep.ipynb    # Feature engineering & export
├── scripts/
│   └── etl_pipeline.py             # Standalone ETL script (auto-detects raw file)
├── tableau/
│   ├── dashboard_link.md           # Tableau Public link
│   └── screenshots/                # Dashboard preview images (3 pages)
├── reports/
│   ├── DIGITOMICS_Report.pdf       # Full project report
│   └── Digitomics_G6_presentation.pdf # Presentation slides
├── DVA-focused-Portfolio/
│   └── Portfolio.md                # Team member portfolio links
├── DVA-oriented-Resume/            # Team member resumes (PDF)
├── requirement.txt                 # Python dependencies
└── README.md
```

---

## Notebook Pipeline

| Step | Notebook | Description |
|------|----------|-------------|
| 1 | `01_extraction.ipynb` | Auto-detects raw file, samples up to 100k rows |
| 2 | `02_cleaning.ipynb` | Null handling, sentinel replacement, IQR Winsorization, binary encoding |
| 3 | `03_eda.ipynb` | Exploratory analysis, distribution plots, correlation heatmaps |
| 4 | `04_statistical_analysis.ipynb` | Statistical tests, scatter & box plots, behavioral pattern analysis |
| 5 | `05_final_load_prep.ipynb` | Feature engineering, risk segmentation, export to `cleaned_data.csv` |

A standalone `scripts/etl_pipeline.py` replicates the full extraction → cleaning → load flow and can be run independently.

---

## Key Engineered Features

| Feature | Description | Formula / Logic |
|---------|-------------|-----------------|
| **Brain Rot Level** | Categorical tier | `Low` (≤15) / `Medium` (≤30) / `High` (>30) |
| **Academic Risk Score** | Risk of academic failure | `(100 - attendance) × 0.4 + (10 - motivation) × 2.5 + addiction × 0.5 + brain_rot × 0.3` |

---

## Analysis & Visualizations
- Correlation heatmaps
- Scatter plots (usage vs productivity)
- Box plots (stress vs usage)
- Behavioral pattern analysis
- Risk segmentation

---

## Tableau Dashboard

**[View Live Dashboard on Tableau Public](https://public.tableau.com/app/profile/soumya.tiwari2918/viz/DVA_project_17772624361540/DashboardPage1)**

Dashboard preview screenshots are available in `tableau/screenshots/`:
- `dashboard_page1.png`
- `dashboard_page2.png`
- `dashboard_page3.png`

---

## Reports & Deliverables

| File | Description |
|------|-------------|
| `reports/DIGITOMICS_Report.pdf` | Full written project report |
| `reports/Digitomics_G6_presentation.pdf` | Final presentation slides |

---

## Tech Stack
- Python (Pandas, NumPy, SciPy)
- Matplotlib / Seaborn
- Jupyter Notebook
- Tableau Public (Dashboard & Visualization)

---

## Expected Insights
- Students with higher social media use and late-night activity tend to have lower productivity
- Stress and Sleep shares negative correlation.
- Cyberbullying and Adult content exposure is most prominent at the age of 16 to 18.
- Higher attendance rate will decrease the time spent on educational content. 


## Team
- Soumya Tiwari 
- Abhijeet Dey
- Chirag Lalwani
- Divyanshu Singh
- Kshitiz Surana
- Yachna

# ⚡ Power Outage Risk Analysis

An end-to-end analytics project that combines **EIA-861 utility reliability data** with **NOAA storm event records** to identify outage risk patterns across U.S. utilities and create **state-level risk rankings**.

This project analyzes reliability metrics such as **SAIDI** and **SAIFI**, compares outage performance against storm exposure, and highlights states where outage outcomes appear worse than weather severity alone would suggest.

---

## 📌 Project Summary

Power outages are not driven by weather alone. Utility characteristics, infrastructure exposure, and reliability performance also matter.

In this project, I merged large-scale utility reliability data with storm event records for **3,000+ U.S. utilities** and built a workflow to:

- clean and combine outage + storm datasets
- calculate outage-related risk signals
- rank utilities and states based on reliability performance
- compare storm severity with outage duration/frequency
- generate dashboard-ready outputs for interactive analysis

The workflow was automated from **data preparation to dashboard output generation**, reducing repeated manual work to a **single script run**.

---

## 🎯 Business / Analytical Objective

The goal of this project is to answer questions such as:

- Which states show higher outage risk based on utility reliability metrics?
- Are some states underperforming even after accounting for storm exposure?
- Which utilities or regions appear more vulnerable to service disruption?
- How can outage reliability and storm event data be combined into a practical risk view for analysis and dashboarding?

This type of analysis can support:
- infrastructure planning
- utility risk monitoring
- resilience analysis
- operational reporting
- geographic prioritization for further investigation

---

## 🗂️ Dataset

### Source Files
- **EIA-861** utility reliability data
- **NOAA Storm Events** data
- Combined / prepared dataset used in this project

### Dataset Link
[Google Drive Dataset Link](https://drive.google.com/file/d/1ppvx0fkmi1QdsbZOnhZ-LAEc-BPF52DS/view?usp=drive_link)

### Main Data Elements Used
- Utility name / utility number
- State
- Ownership
- NERC region
- County coverage
- SAIDI
- SAIFI
- CAIDI
- Event type
- Storm timing fields
- Magnitude
- Property damage
- Crop damage
- Injury / death fields
- Regional grid indicators

### Notes
- The cleaned dashboard dataset keeps only the **50 U.S. states**.
- The workflow prepares a dashboard-friendly dataset in both **CSV** and **Parquet** formats.

---

## 🛠️ Tech Stack

- **Python**
- **Pandas**
- **NumPy**
- **Plotly**
- **Matplotlib**
- **Scikit-learn**
- **Jupyter Notebook**
- **EIA-861**
- **NOAA Storm Events**

---

## 🔄 Project Workflow

### 1. Data Integration
- Combined utility reliability data with storm event data
- Standardized columns and filtered relevant records
- Retained dashboard-ready fields for analysis

### 2. Data Cleaning & Transformation
- removed unnecessary columns
- handled missing values
- optimized large-file processing
- created cleaned outputs for downstream visuals and analysis

### 3. Risk Scoring
- ranked utilities using outage reliability metrics
- used **SAIDI** and **SAIFI** percentile-based scoring
- created a **composite outage risk score**
- assigned utilities into **High Risk / Medium Risk / Low Risk** groups

### 4. State-Level Analysis
- aggregated utility and storm measures by state
- compared outage performance across geographies
- identified states with elevated outage risk

### 5. Dashboard Output
- generated dashboard-ready files
- supported interactive views for:
  - reliability trends
  - risk categories
  - state comparison
  - top utilities by risk score
  - outage vs storm relationship

### 6. Optional Predictive Modeling
The notebook also includes an extended modeling section to classify high-risk utilities using:
- Logistic Regression
- Random Forest
- Extra Trees

This adds a stronger portfolio angle by showing not only descriptive analysis, but also utility-level risk prediction.

---

## 📊 Key Metrics

### Reliability Metrics
- **SAIDI** – System Average Interruption Duration Index
- **SAIFI** – System Average Interruption Frequency Index
- **CAIDI** – Customer Average Interruption Duration Index

### Storm / Impact Metrics
- Event type
- Event magnitude
- Property damage
- Crop damage
- Injuries / deaths
- Monthly storm activity patterns

### Derived Metrics
- percentile-based SAIDI rank
- percentile-based SAIFI rank
- composite outage risk score
- risk category labels
- state-level high-risk counts

---

## 📈 Key Analysis Outputs

Based on the project scope, the analysis highlights:

- utility-level reliability differences across U.S. states
- state-level risk ranking using SAIDI and SAIFI thresholds
- comparison of storm severity versus outage performance
- identification of states where outage outcomes appear worse than expected from weather exposure alone
- automated dashboard dataset creation for repeatable analysis

> In the project summary, this analysis highlighted **4 states** where outage performance appeared worse than storm exposure alone would suggest.

---

## 🧠 Repository Structure

Use this structure for a clean and recruiter-friendly repository:

```text
power-outage-risk-analysis/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── raw/
│   │   └── merged_utility_storm_2024.csv
│   ├── processed/
│   │   ├── dashboard_clean_dataset.csv
│   │   └── dashboard_clean_dataset.parquet
│   └── external/
│       └── dataset_link.txt
│
├── notebooks/
│   └── Power Outage Risk Analysis.ipynb
│
├── src/
│   ├── data_cleaning.py
│   ├── risk_scoring.py
│   ├── dashboard_prep.py
│   └── modeling.py
│
├── dashboards/
│   ├── screenshots/
│   │   ├── dashboard-overview.png
│   │   ├── state-risk-map.png
│   │   ├── saidi-saifi-scatter.png
│   │   └── top-utilities-table.png
│   └── exported_html/
│
├── outputs/
│   ├── project_scope_and_class_balance.csv
│   ├── model_comparison_all.csv
│   ├── incremental_value_test.csv
│   ├── best_model_test_predictions.csv
│   ├── utility_level_modeling_dataset.csv
│   ├── error_summary.csv
│   ├── false_positives.csv
│   ├── false_negatives.csv
│   ├── error_group_characteristics.csv
│   ├── state_risk_breakdown.csv
│   ├── top_feature_importance.csv
│   └── sensitivity_check_top10_vs_top20.csv
│
└── assets/
    └── banner/
```

---

## 🖼️ Dashboard Screenshots

**Yes — you should absolutely upload dashboard screenshots.**  
That will make your repository much more attractive to recruiters.

### Best screenshots to include
Upload 3–5 strong visuals such as:

1. **Dashboard overview**
2. **State risk choropleth map**
3. **SAIDI vs SAIFI scatter plot**
4. **Risk category distribution chart**
5. **Top utilities by risk score table**

### Where to keep them
Store them here:

```text
dashboards/screenshots/
```

### How to display them in README

```md
## Dashboard Preview

### Overview
![Dashboard Overview](dashboards/screenshots/dashboard-overview.png)

### State Risk Map
![State Risk Map](dashboards/screenshots/state-risk-map.png)

### SAIDI vs SAIFI
![SAIDI vs SAIFI Scatter](dashboards/screenshots/saidi-saifi-scatter.png)
```

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/power-outage-risk-analysis.git
cd power-outage-risk-analysis
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Add the Dataset
Place the merged dataset inside:

```text
data/raw/
```

Example:
```text
data/raw/merged_utility_storm_2024.csv
```

### 4. Run the Notebook
Open the notebook in Jupyter or Google Colab:

```text
notebooks/Power Outage Risk Analysis.ipynb
```

### 5. Generate Outputs
The notebook produces cleaned datasets and analysis outputs such as:
- dashboard-ready CSV / Parquet files
- risk breakdown summaries
- model comparison files
- feature importance outputs
- dashboard-ready analysis tables

---

## 📌 Recommended Files to Add to the Repo

To make this repository look complete, include:

- `README.md`
- `requirements.txt`
- notebook file
- cleaned sample output files
- screenshot images
- a short `data_dictionary.md` file
- an optional `project_report.pdf`

---

## ✅ Why This Project Stands Out

This project demonstrates:

- large-scale data integration
- reliability + weather data analysis
- domain-relevant KPI interpretation
- risk scoring logic
- state-level geographic analysis
- dashboard preparation
- automation of repetitive analysis steps
- clear business-facing presentation

It is not just an exploratory notebook — it is a portfolio-ready analytics project with practical reporting value.

---

## 🔮 Future Improvements

Possible next steps for this project:

- deploy an interactive dashboard as a public web app
- add a formal data dictionary
- compare outage risk by utility ownership type
- incorporate population / customer counts for normalized impact views
- add time-series outage seasonality analysis
- expand modeling evaluation and explainability

---

## 👤 Author

**Sejal Khade**  
Data Analyst | SQL | Python | Power BI | Tableau  
Open to U.S. Data Analyst opportunities

---

## ⭐ Recruiter Note

This project was designed to show end-to-end analytics capability:
from **raw data integration and transformation** to **risk scoring, visualization, and dashboard-ready outputs**.

If you're reviewing this repository for hiring, the fastest path is:
1. read the project summary
2. view the dashboard screenshots
3. check the notebook / workflow
4. review the outputs folder

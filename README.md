# Power Outage Risk Analysis

An end-to-end analytics project that combines **EIA-861 utility reliability data** with **NOAA storm event records** to evaluate outage risk across U.S. utilities and generate state-level risk rankings.

The project uses **SAIDI**, **SAIFI**, and related reliability measures to identify higher-risk regions, compare outage outcomes against storm exposure, and produce dashboard-ready outputs for interactive analysis.

---

## Overview

Power outage performance is influenced by more than weather alone. This project integrates utility reliability data with storm event records to examine where outage duration and frequency appear disproportionately high relative to storm severity.

The workflow covers:

- large-scale data cleaning and integration
- outage reliability analysis across 3,000+ U.S. utilities
- state-level risk scoring using SAIDI and SAIFI thresholds
- dashboard dataset creation in CSV and Parquet formats
- visual analysis using Plotly and Matplotlib
- optional utility-level predictive modeling

---

## Project Objectives

- Analyze outage reliability across U.S. utilities
- Create state-level outage risk rankings
- Compare storm severity with outage duration and interruption frequency
- Highlight states where outage performance appears worse than storm exposure alone would suggest
- Automate the workflow from raw input data to dashboard-ready outputs

---

## Dataset

**Sources**
- EIA-861 utility reliability data
- NOAA Storm Events data

**Dataset Link**
- [Google Drive Dataset](https://drive.google.com/file/d/1ppvx0fkmi1QdsbZOnhZ-LAEc-BPF52DS/view?usp=drive_link)

**Primary fields used**
- Utility Number
- Utility Name
- State
- Ownership
- NERC Region
- County_Count
- Counties_Served
- IEEE_AllEvents_SAIDI_min_per_yr
- IEEE_AllEvents_SAIFI_times_per_yr
- IEEE_AllEvents_CAIDI_min_per_interruption
- IEEE_NoMED_SAIDI_min_per_yr
- IEEE_NoMED_SAIFI_times_per_yr
- IEEE_NoMED_CAIDI_min_per_interruption
- EVENT_TYPE
- CZ_NAME
- MONTH_NAME
- YEAR
- BEGIN_DATE_TIME
- END_DATE_TIME
- MAGNITUDE
- Property damage and crop damage fields
- Injury and fatality fields

---

## Tech Stack

- Python
- Pandas
- NumPy
- Plotly
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- EIA-861
- NOAA Storm Events

---

## Methodology

### 1. Data Preparation
- Loaded the merged utility-storm dataset
- Selected dashboard-relevant columns
- Removed unnecessary fields
- Filtered the dataset to the 50 U.S. states

### 2. Data Cleaning
- Standardized data types
- Handled missing values
- Optimized processing for large files using chunked loading
- Exported cleaned datasets for downstream analysis

### 3. Reliability Analysis
- Analyzed outage reliability using SAIDI, SAIFI, and CAIDI
- Calculated utility-level percentile ranks for outage performance
- Built a composite outage risk score
- Grouped utilities into risk categories

### 4. Geographic Risk Ranking
- Aggregated metrics at the state level
- Created state-level risk views based on reliability thresholds
- Compared outage performance across regions

### 5. Visualization and Dashboard Preparation
- Produced dashboard-ready CSV and Parquet outputs
- Built visuals to compare outage metrics and storm exposure
- Prepared data for interactive dashboard exploration

### 6. Predictive Modeling
The notebook also includes a modeling section to classify high-risk utilities using:
- Logistic Regression
- Random Forest
- Extra Trees

Additional analysis includes:
- model comparison
- feature importance
- error analysis
- sensitivity testing for top-risk utility definitions

---

## Key Metrics

### Reliability Metrics
- **SAIDI** — System Average Interruption Duration Index
- **SAIFI** — System Average Interruption Frequency Index
- **CAIDI** — Customer Average Interruption Duration Index

### Storm and Impact Metrics
- Event type
- Magnitude
- Property damage
- Crop damage
- Injuries
- Fatalities
- Monthly event patterns

### Derived Metrics
- SAIDI percentile rank
- SAIFI percentile rank
- Composite outage risk score
- Risk category labels
- State-level high-risk counts

---

## Key Outputs

This project generates:

- cleaned dashboard dataset in CSV format
- cleaned dashboard dataset in Parquet format
- state-level outage risk analysis
- utility-level risk scoring outputs
- model comparison results
- feature importance summaries
- error analysis files
- sensitivity testing outputs

---

## Dashboard Preview

Add your dashboard screenshots in this section.

```md
![Dashboard Overview](dashboards/screenshots/dashboard-overview.png)
![State Risk Map](dashboards/screenshots/state-risk-map.png)
![SAIDI vs SAIFI Scatter](dashboards/screenshots/saidi-saifi-scatter.png)

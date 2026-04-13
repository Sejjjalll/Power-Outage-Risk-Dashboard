# ⚡ Power Outage Risk Analysis

A data project on how utility reliability and storm exposure come together across the U.S.

I built this project to look past the usual “bad weather causes outages” explanation and ask a better question:  
**which states and utilities seem to perform worse than weather exposure alone would suggest?**

Using **EIA-861 reliability data** and **NOAA storm records**, I combined outage and weather signals for **3,000+ U.S. utilities**, created a clean analysis dataset, built state-level risk views, and prepared dashboard outputs for easier exploration.

---

## ✨ What this project does

- combines utility reliability data with storm event records
- cleans and reshapes the merged data for analysis
- uses **SAIDI** and **SAIFI** to create outage risk signals
- assigns utilities into **High / Medium / Low Risk** groups
- builds state-level comparisons for outage risk
- prepares dashboard-ready files in **CSV** and **Parquet**
- explores whether high-risk utilities can also be identified with machine learning

---

## 🧭 Why I built it

Power systems are usually discussed in broad terms, but I wanted to make the analysis more concrete.

This project helped me explore:
- where outage performance is consistently weak
- how storm severity relates to outage duration and frequency
- which states deserve a closer look from a resilience or infrastructure lens
- how to turn a heavy raw dataset into something clean enough for dashboards and repeatable analysis

---

## 📊 Project highlights

- merged reliability and storm data for **3,000+ U.S. utilities**
- created **state-level risk rankings**
- used **SAIDI** and **SAIFI** thresholds to flag higher-risk utilities
- compared storm severity with outage performance
- highlighted **4 states** where outage outcomes looked worse than storm exposure alone would suggest
- reduced repeated manual prep to a **single workflow run**

---

## 🗂️ Data sources

- **EIA-861** utility reliability data
- **NOAA Storm Events** data

**Dataset:**  
[Google Drive dataset link](https://drive.google.com/file/d/1ppvx0fkmi1QdsbZOnhZ-LAEc-BPF52DS/view?usp=drive_link)

---

## 🧪 Main metrics used

### Reliability
- **SAIDI** — outage duration
- **SAIFI** — outage frequency
- **CAIDI** — average interruption duration

### Storm / impact signals
- event type
- magnitude
- property damage
- crop damage
- injuries
- deaths
- month / timing patterns

### Derived fields
- percentile-based SAIDI rank
- percentile-based SAIFI rank
- composite risk score
- risk category label
- state-level risk summaries

---

## 🛠️ Tools used

`Python` `Pandas` `NumPy` `Plotly` `Matplotlib` `Scikit-learn` `Jupyter Notebook`

---

## 🧱 Project flow

### 1) Merge and clean
I started with a merged utility-storm dataset, kept only the columns needed for analysis, standardized field types, and filtered the data to the **50 U.S. states**.

### 2) Create risk signals
To make the reliability comparison more useful, I calculated percentile-based rankings from **SAIDI** and **SAIFI**, then combined them into a single outage risk score.

### 3) Build dashboard-ready data
The cleaned dataset was saved in both **CSV** and **Parquet** format so it could be used easily in dashboards and follow-up analysis.

### 4) Explore patterns by state
I looked at outage risk across states and compared storm exposure with outage outcomes to surface places that may be underperforming.

### 5) Model high-risk utilities
As an extension, I also tested a few models to see whether utilities in the higher-risk group could be identified from storm and utility features.

---

## 🖼️ Dashboard preview

Add your screenshots here once uploaded.

```md
![Dashboard Overview](dashboards/screenshots/dashboard-overview.png)
![State Risk Map](dashboards/screenshots/state-risk-map.png)
![SAIDI vs SAIFI](dashboards/screenshots/saidi-saifi-scatter.png)

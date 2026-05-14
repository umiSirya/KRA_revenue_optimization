# Kenya Revenue Authority (KRA) Revenue Performance Analysis

## Project Overview
This project analyses two government revenue datasets from the Kenya Revenue Authority (KRA) to uncover insights on tax head performance, revenue distribution, and growth trends across key revenue drivers. The goal was to clean, explore, and visualise the data to support data-driven decision making in public finance.

---

## Problem Statement
Kenya's tax revenue landscape is complex — with multiple tax heads growing at different rates and several revenue drivers contributing varying amounts. This project answers the following key questions:

- Which revenue driver brings in the most money?
- Which tax head is growing the fastest?
- How is total tax revenue split across different tax heads?
- Which tax head adds the most absolute value in the next period?
- What does projected revenue look like if current growth rates continue?

---

## Datasets
| Dataset | Description | Rows |
|---|---|---|
| `key-revenue-drivers-for-kenya.csv` | Key initiatives driving revenue collection (e.g. Tax Amnesty, Debt Collection) with collection figures in Bn Ksh | 6 |
| `performance-of-key-tax-heads.csv` | Performance of major tax categories (e.g. PAYE, VAT, Corporation Tax) with revenue and growth % | 6 |

---

## Tools & Technologies
- **Python** — Data cleaning and feature engineering
- **Pandas** — Data manipulation and analysis
- **Matplotlib** — Data visualisation
- **NumPy** — Numerical computations
- **Google Colab** — Development environment
- **Power BI Desktop** — Interactive dashboard

---

## Project Structure
```
kenya-revenue-analysis/
│
├── key-revenue-drivers-for-kenya.csv
├── performance-of-key-tax-heads.csv
├── KRA_revenue_analysis.ipynb
├── KRA Revenue Performance Dashboard.pbix
├── KRA Revenue Performance Dashboard.png
└── README.md
```

---

## Data Cleaning Steps
1. Loaded both datasets and inspected for nulls, duplicates and data types
2. Confirmed both datasets were clean with no missing values or duplicate rows
3. Standardised column names to snake_case for consistency
4. Stripped whitespace from string columns to prevent silent merge errors
5. Tagged each dataset with a Source column (Revenue Driver vs Tax Head)

---

## Feature Engineering
New columns calculated to enrich the analysis:

| Column | Description |
|---|---|
| `Revenue_Share_Pct` | Each item's % contribution to total revenue in its group |
| `Projected_Revenue` | Next period revenue estimate using current growth rate |
| `Revenue_Change` | Absolute difference between projected and current revenue |

**Projection formula:**
```
Projected Revenue = Current Revenue × (1 + Growth Rate / 100)
```

---

## Key Insights

### Revenue Drivers
- **Debt Collection Initiatives** is the biggest revenue driver at **Ksh 103.39 Bn** — nearly double the second largest
- **Anti-Corruption Measures** contributes the least at **Ksh 4.22 Bn**
- The top 2 drivers (Debt Collection + Dispute Resolution) account for over **62%** of total driver revenue

### Tax Head Performance
- **PAYE dominates** total tax revenue at **43.7%** (Ksh 543 Bn) — Kenya's tax base is heavily dependent on employment income
- **Capital Gains Tax** has the highest growth rate at **49.5%** but contributes only **0.7%** of total revenue — high growth on a small base
- **PAYE + Domestic VAT** together account for **69%** of all tax revenue — a concentration risk for Kenya's fiscal policy
- **PAYE adds the most absolute value** in projected revenue at **+Ksh 52.7 Bn** despite having a modest 9.7% growth rate — a classic base effect

### The Base Effect
> Capital Gains Tax grows at 49.5% but adds only Ksh 4 Bn. PAYE grows at 9.7% but adds Ksh 52.7 Bn. Growth rate alone does not tell the full story — the size of the base matters just as much.

---

## Python Visualisations
Five charts were built in Matplotlib:

1. **Revenue by Driver** — Horizontal bar chart showing Debt Collection leads
2. **Fastest Growing Tax Heads** — Horizontal bar chart showing Capital Gains Tax at 49.5%
3. **Revenue Split by Tax Head** — Pie chart showing PAYE dominance
4. **Current vs Projected Revenue** — Grouped bar chart comparing before and after
5. **Absolute Revenue Change** — Horizontal bar chart showing which tax head adds the most value

---

## Power BI Dashboard
An interactive dashboard was built in Power BI Desktop featuring:

- **4 KPI Cards** — Total Revenue Collection, Total Tax Revenue, Highest Growing Tax Head, Biggest Revenue Driver
- **Revenue by Driver** — Horizontal bar chart
- **Tax Head by Revenue** — Horizontal bar chart
- **Revenue Splits by Tax Head** — Donut chart
- **Revenue Growth % by Tax Head** — Horizontal bar chart

![KRA Dashboard](KRA%20Revenue%20Performance%20Dashboard.png)

---

## How to Run
1. Clone this repository
```bash
git clone https://github.com/naomis-hub/kenya-revenue-analysis.git
```
2. Open `KRA_revenue_analysis.ipynb` in Google Colab or Jupyter Notebook
3. Upload `key-revenue-drivers-for-kenya.csv` and `performance-of-key-tax-heads.csv` when prompted
4. Run all cells in order
5. Open `KRA Revenue Performance Dashboard.pbix` in Power BI Desktop

---

## Author
**Naomi S**
- LinkedIn: [linkedin.com/in/naomi-s-a6750613a](https://www.linkedin.com/in/naomi-s-a6750613a/)

---

## License
This project is open source and available under the [MIT License](LICENSE).

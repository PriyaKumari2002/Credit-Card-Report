# 💳 Credit Card Report Dashboard

> End-to-end Power BI analytics covering transaction patterns and customer demographics — built with Power Query and DAX across two themed dashboards.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=flat)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat)

---

## 📊 Overview

| Metric | Value |
|---|---|
| Total Revenue | $55M |
| Total Transactions | 656K |
| Interest Earned | $8M |
| Total Customer Income | $576M |

---

## 🗂️ Dashboards

### 1. Transaction Report *(Rose theme)*
Focuses on the financial side of credit card usage:
- Revenue breakdown by **card category** (Blue, Silver, Gold, Platinum)
- Revenue by **expense type** — Bills, Entertainment, Fuel, Grocery, Food, Travel
- Revenue by **education level** and **job type**
- Revenue by **payment method** — Swipe, Chip, Online
- **Quarterly revenue** vs total transaction volume (combo chart)
- Slicers: Week, Gender, Card Type, Chip Usage

### 2. Customer Report *(Green theme)*
Focuses on customer demographics:
- Revenue by **age group**, **income level**, and **number of dependents**
- Revenue by **marital status** and **gender**
- **Weekly revenue trend** across 2023
- **Top 5 states** by revenue (TX, NY, CA, FL, NJ)
- Customer job segment table with revenue, income, and interest breakdowns
- Slicers: Week, Card Type, Chip Usage, Gender

---

## 🔄 Data Pipeline

### Step 1 — Source Data
Two CSV files loaded into Power BI Desktop:
- `credit_card.csv` — transaction-level data (amounts, categories, chip usage, etc.)
- `customer.csv` — customer demographics, income, job type, marital status, location

### Step 2 — Power Query Cleaning
- Removed duplicate rows
- Handled null and missing values
- Standardised column data types (dates, currency, integers)
- Trimmed whitespace from text fields
- Renamed columns for readability and consistency
- Filtered out irrelevant or erroneous records

### Step 3 — Data Modelling
- Established a relationship between the transaction and customer tables via a shared **Customer ID** key
- Created a **Date table** to enable time-intelligence functions
- Defined cardinality and cross-filter direction for the data model

### Step 4 — DAX Measures
Custom measures built using DAX:
- `Total Revenue` — sum of revenue across all transactions
- `Interest Earned` — aggregated interest earned per card
- `Transaction Count` — total number of transactions
- `CSS Score` — customer satisfaction score (avg)
- Segment-level revenue breakdowns using `CALCULATE`, `SUMX`, and `FILTER`

### Step 5 — Dashboard Design
- Two separate report pages with distinct colour palettes
- KPI cards for headline metrics
- Bar charts, line charts, and combo charts for trends
- Interactive slicers for dynamic filtering

---

## 💡 Key Insights

- **Blue card holders** dominate revenue at $46M — nearly 10× the Platinum tier.
- **Swipe** is the most used payment method ($35M), far ahead of chip ($17M) and online ($3M).
- **Businessmen** are the top revenue-generating job segment at $17M, followed by White-collar workers at $10M.
- **Graduate customers** generate the highest revenue by education ($22M), more than double any other group.
- **Age group 40–50** is the highest-spending cohort, contributing $25M combined across genders.
- **TX, NY, and CA** are the top three revenue states, with Texas leading at $6.2M.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Power BI Desktop | Report building, visuals, and publishing |
| Power Query | ETL — data cleaning and transformation |
| DAX | Custom measures and calculated columns |
| CSV (2 files) | Source data |

---

## 📁 Files

```
📦 credit-card-report
 ┣ 📄 credit_card.csv          # Raw transaction data
 ┣ 📄 customer.csv             # Customer demographics & income
 ┗ 📊 Credit_Card_Report.pbix  # Power BI project file
```

---

## 🚀 How to Use

1. Clone or download this repository.
2. Open `Credit_Card_Report.pbix` in **Power BI Desktop**.
3. If needed, update the data source paths to point to your local `credit_card.csv` and `customer.csv`.
4. Click **Refresh** to reload the data.
5. Use the slicers on each page to filter by week, gender, card type, or chip usage.

---

*Built with Power BI · Data analysis project*

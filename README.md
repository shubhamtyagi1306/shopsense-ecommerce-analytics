# 🛒 ShopSense - E-Commerce Sales Analytics

> **E-Commerce Sales Analytics: Customer Behaviour, Revenue Trends and Churn Risk Analysis Using Python**

---

## 📌 Project Description

ShopSense is an end-to-end e-commerce data analytics project built entirely in Python. It analyses **8,500+ orders** from **1,200 customers** generating **$3.1M+ in revenue** across **18 months** and **6 product categories**.

The project simulates a real-world business analytics scenario where raw transaction data is cleaned, transformed and analysed across 7 structured modules - each answering a specific business question using data-driven insights and visualisations.

This project was built as a **MCA Semester 3 Mini Project** and is designed to demonstrate practical skills in data cleaning, exploratory analysis, time-series trends, customer segmentation and churn risk scoring using Python.

---

## 🎯 Business Problems Solved

| # | Business Question | Module |
|---|---|---|
| 1 | What does our data look like and is it clean? | EDA |
| 2 | Which categories and segments drive the most revenue? | EDA |
| 3 | How is revenue trending month over month? | Revenue Trends |
| 4 | Are customers coming back after their first purchase? | Cohort Retention |
| 5 | Which products are performing well and which are not? | Product Performance |
| 6 | Which customers are likely to stop buying? | Churn Risk Scoring |

---

## 📊 Key KPIs Analysed

| KPI | Value |
|---|---|
| Total Orders Analysed | 8,500+ |
| Total Revenue Tracked | $3.1M+ |
| Time Period | 18 Months (Jan 2023 – Jun 2024) |
| Unique Customers | 1,200 |
| Products Evaluated | 80 |
| Product Categories | 6 |
| Cohorts Built | 12 |
| Churn Risk Tiers | 3 (Low / Medium / High) |

---

## 🗂️ Project Structure

```
ShopSense/
│
├── data/
│   ├── customers.csv        # 1,200 customer records
│   ├── products.csv         # 80 product records
│   └── orders.csv           # 8,500 order records
│
├── notebooks/
│   └── shopsense_analysis.ipynb   # Main Jupyter Notebook
│
├── outputs/
│   ├── high_risk_customers.csv    # Exported churn risk list
│   └── plots/                     # All saved visualisations
│
├── generate_data.py         # Synthetic dataset generator
├── shopsense_analysis.py    # Full analysis pipeline script
└── README.md
```

---

## 🔬 Project Modules

### Module 1 - Data Loading & Inspection
- Loaded 3 CSV files (customers, products, orders)
- Checked data types, null values and shape
- Performed basic sanity checks on date ranges and unique values

### Module 2 - Data Cleaning & Feature Engineering
- Merged all 3 tables into one master dataframe
- Removed duplicates and fixed data types
- Engineered new columns: `year`, `month`, `quarter`, `weekday`, `age_group`, `order_size`
- Created a `delivered` subset for accurate revenue calculations

### Module 3 - Exploratory Data Analysis (EDA)
- Order status distribution
- Revenue and order count by category
- Revenue by customer segment and age group
- Orders by day of week
- Payment method breakdown

### Module 4 - Revenue Trend Analysis
- Monthly revenue trend with 3-month moving average
- Month-over-Month (MoM) growth tracking
- Average Order Value (AOV) over time
- Quarterly revenue comparison
- Active customer count per month

### Module 5 - Cohort Retention Analysis
- Built cohort table tracking customers by first purchase month
- Calculated period numbers (months since first purchase)
- Plotted retention heatmap across 12 cohorts and 8 periods
- Identified best and worst retention cohorts
- Plotted average retention curve across all cohorts

### Module 6 - Product Performance Analysis
- Top 10 and Bottom 10 products by revenue
- Revenue distribution per category using box plots
- Average discount % by category
- Product rating distribution
- Return rate analysis by category
- Rating vs Return Rate scatter plot to identify problem products

### Module 7 - Customer Churn Risk Scoring
- Built base customer table with Recency, Frequency and Monetary values
- Normalised all features to 0–1 scale
- Applied weighted churn formula: R(45%) + F(35%) + M(20%)
- Classified customers into Low, Medium and High risk tiers
- Visualised revenue at risk per tier
- Exported high-risk customer list for marketing action

---

## 📈 Sample Visualisations

| Plot | Description |
|---|---|
| Monthly Revenue Trend | Line chart with 3-month moving average |
| MoM Growth Bar Chart | Green/red bars for positive/negative growth |
| Cohort Retention Heatmap | 12×8 retention % grid |
| Rating vs Return Scatter | Product quality quadrant analysis |
| Churn Risk Distribution | Score histogram with tier boundaries |
| Revenue at Risk | Bar chart showing $ value per risk tier |

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, merging, aggregation |
| `numpy` | Numerical operations, normalization |
| `matplotlib` | Base plotting and chart customisation |
| `seaborn` | Statistical visualisations and heatmaps |

---

## ⚙️ How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/shopsense-ecommerce-analytics.git
cd shopsense-ecommerce-analytics
```

### 2. Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn
```

### 3. Generate the Dataset
```bash
python generate_data.py
```
This creates `customers.csv`, `products.csv` and `orders.csv` in your working directory.

### 4. Run the Analysis
```bash
python shopsense_analysis.py
```
Or open the Jupyter Notebook:
```bash
jupyter notebook notebooks/shopsense_analysis.ipynb
```

---

## 💡 Key Concepts Demonstrated

- **Data Merging** — joining multiple tables using `pd.merge()`
- **Feature Engineering** — creating derived columns from datetime and numerical data
- **GroupBy Aggregation** — `groupby().agg()` for multi-metric summaries
- **Cohort Analysis** — `transform()`, `pivot()`, retention % calculation
- **Moving Average** — `rolling(window=3).mean()` for trend smoothing
- **Normalization** — min-max scaling for fair feature comparison
- **Rule-Based Scoring** — weighted formula to compute churn risk
- **`pd.cut()` vs `pd.qcut()`** — fixed-width vs equal-frequency binning

---

## 📋 Dataset Description

The dataset is synthetically generated using `generate_data.py` to simulate a realistic e-commerce business scenario.

### customers.csv
| Column | Description |
|---|---|
| customer_id | Unique customer identifier |
| age | Customer age |
| city | City of residence |
| segment | Customer segment (Premium / Regular / Occasional / New) |
| join_date | Date customer joined |
| gender | Gender (M / F / Other) |

### products.csv
| Column | Description |
|---|---|
| product_id | Unique product identifier |
| category | Product category |
| price | Product price ($) |
| rating | Product rating (3.0 – 5.0) |
| return_rate | Historical return rate (0.02 – 0.20) |

### orders.csv
| Column | Description |
|---|---|
| order_id | Unique order identifier |
| customer_id | Linked customer |
| product_id | Linked product |
| order_date | Date of order |
| quantity | Units ordered |
| discount_pct | Discount applied (%) |
| payment | Payment method |
| status | Order status (Delivered / Cancelled / Returned / Pending) |
| revenue | Final order revenue after discount |

---

## 🎓 Academic Details

| Field | Detail |
|---|---|
| Project Title | E-Commerce Sales Analytics: Customer Behaviour, Revenue Trends and Churn Risk Analysis Using Python |
| Course | Master of Computer Applications (MCA) |
| Semester | Semester 3 |
| Domain | Data Analytics |
| Type | Mini Project |

---

## 🙋 Author

**Shubham Tyagi**
MCA Student | Data Analytics Enthusiast
📧 shubhamtyagi1306@gmail.com
🔗 [LinkedIn](https://github.com/shubhamtyagi1306)
🐙 [GitHub](https://www.linkedin.com/in/shubham-tyagi-40510617a/)

---

## ⭐ If you found this project helpful, please give it a star!

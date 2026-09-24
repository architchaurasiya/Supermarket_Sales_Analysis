# Supermarket Sales Analysis

**Student Name:** Archit Kumar Chaurasiya  
**Project Type:** Data Analytics  

---

## Project Overview

This project performs a comprehensive Exploratory Data Analysis (EDA) on a supermarket sales dataset of **500 transactions** recorded across **four branches** in four Indian cities (Jaipur, Delhi, Mumbai, Bengaluru) during **January 2026 – July 2026**.

The analysis covers sales patterns, product category performance, customer behaviour, payment preferences, and time-based trends, concluding with data-driven business insights and recommendations.

---

## Objective

1. Load and inspect the provided supermarket sales dataset.
2. Perform a thorough data quality assessment.
3. Verify and utilise the Sales calculation (Quantity × Unit Price).
4. Group and summarise data by branch, category, product, customer type, gender, payment method, and time period.
5. Create clear, informative visualisations.
6. Derive actionable business insights and decisions from the analysis results.

---

## Dataset Description

| Field | Value |
|---|---|
| Filename | `SUPER MARKET DATA - supermarket_sales_500_rows.csv` |
| Location (raw) | `data/raw/` |
| Rows | 500 |
| Columns | 13 |
| Date Range | 2026-01-01 to 2026-07-01 |

**Columns:**

| Column | Type | Description |
|---|---|---|
| Invoice ID | String | Unique transaction identifier (INV0001–INV0500) |
| Date | Date | Transaction date |
| Branch | String | Branch code (A, B, C, D) |
| City | String | City where the branch is located |
| Customer Type | String | Member or Normal |
| Gender | String | Male or Female |
| Product | String | Name of product purchased (20 unique products) |
| Category | String | Product category (8 categories) |
| Quantity | Integer | Units purchased (1–10) |
| Unit Price | Float | Price per unit (₹) |
| Payment | String | Payment method (Card, Cash, UPI, Net Banking) |
| Rating | Float | Customer satisfaction rating (1.0–5.0) |
| Sales | Float | Total sale value = Quantity × Unit Price |

---

## Data Quality & Cleaning Approach

### Data Quality Assessment
The dataset was assessed for:
- Missing / null values
- Duplicate rows and duplicate Invoice IDs
- Invalid numerical values (negative quantities, prices, ratings out of range)
- Inconsistent categorical values
- Branch–City mapping consistency
- Product–Category mapping consistency
- Accuracy of the existing Sales column

### Finding
**The dataset is completely clean.** No issues were found:

| Check | Result |
|---|---|
| Missing values | ✅ None (0 across all 13 columns) |
| Duplicate rows | ✅ None |
| Duplicate Invoice IDs | ✅ None |
| Negative/zero numeric values | ✅ None |
| Ratings outside 1–5 | ✅ None |
| Branch–City inconsistency | ✅ None |
| Product–Category inconsistency | ✅ None |
| Sales ≠ Quantity × Unit Price | ✅ All match exactly |

### Decision: CASE A — No Cleaning Required

> The original dataset is **directly used** for all analysis.  
> **No `cleaned_supermarket_sales.csv` was created.**  
> The original dataset was not modified in any way.

---

## Raw vs Processed Dataset

| | File |
|---|---|
| **Raw dataset** | `data/raw/SUPER MARKET DATA - supermarket_sales_500_rows.csv` — **preserved unchanged** |
| **Processed dataset** | **Not created** — no actual data modification was required |

---

## Technologies / Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, grouping, summarisation |
| `numpy` | Numerical operations |
| `matplotlib` | Chart creation |
| `seaborn` | Statistical visualisations (heatmap, boxplot, KDE) |
| `scipy` | KDE computation for distribution chart |
| `jupyter` / `notebook` | Interactive notebook environment |

---

## Project Workflow

1. **Load dataset** from `data/raw/`
2. **Initial inspection** — shape, columns, data types, sample rows
3. **Data quality assessment** — missing values, duplicates, range checks, consistency
4. **Cleaning decision** — CASE A: no cleaning required
5. **Sales verification** — confirm Sales = Quantity × Unit Price
6. **Feature engineering** — extract Month, Month Name, Day of Week (in-memory only)
7. **Grouped summaries** — by Branch, Category, Product, Customer Type, Gender, Payment, Month, Day
8. **Statistical summaries** — overall totals, averages, std dev, correlation matrix
9. **Visualisations** — 13 charts (bar, line, pie, donut, heatmap, box plot, histogram+KDE)
10. **Business insights** — 10 data-driven insights
11. **Business decisions** — 8 actionable recommendations
12. **Conclusion & audit**

---

## Analysis Performed

| Analysis | Description |
|---|---|
| Branch / City Sales | Total revenue, transaction count, average sale, average rating per branch |
| Category Sales | Revenue, transactions, average sale per product category |
| Product Sales | Top 10 products by total revenue |
| Customer Type | Revenue and average sale for Member vs Normal customers |
| Gender | Revenue split and category preferences by gender |
| Payment Method | Transaction count and revenue share by payment type |
| Monthly Trend | Month-by-month revenue and transaction trend |
| Day of Week | Revenue distribution across days of the week |
| Rating Analysis | Overall average, by branch, by category |
| Cross-tab Analysis | Customer Type × Category, Gender × Category |
| Statistical Summary | Total revenue, median, std dev, min/max, correlation matrix |

---

## Visualisations Created

| # | Chart | Type |
|---|---|---|
| 1 | Total Sales by Branch / City | Bar chart |
| 2 | Total Sales by Product Category | Horizontal bar chart |
| 3 | Top 10 Products by Total Sales | Horizontal bar chart |
| 4 | Monthly Sales Trend (Jan–Jul 2026) | Line + bar (dual-axis) |
| 5 | Payment Method Distribution (Transactions) | Pie chart |
| 6 | Payment Method Distribution (Revenue) | Pie chart |
| 7 | Transactions: Customer Type × Gender | Grouped bar chart |
| 8 | Revenue: Customer Type × Gender | Grouped bar chart |
| 9 | Avg Sale per Transaction by Category | Bar chart |
| 10 | Avg Customer Rating by Category | Bar chart with mean line |
| 11 | Sales Distribution (Histogram + KDE) | Histogram + KDE curve |
| 12 | Total Sales by Day of Week | Bar + line chart |
| 13 | Sales Heatmap: Branch × Category | Heatmap |
| 14 | Sales Value Distribution by Category | Box plot |
| 15 | Revenue Share by Product Category | Donut chart |
| 16 | Correlation Matrix | Heatmap |

---

## Key Findings

1. **Branch C (Mumbai)** leads in total revenue; **Branch A (Jaipur)** has the lowest transaction count.
2. **Personal Care** and **Dairy** are the top two revenue-generating categories.
3. **Cheese, Shampoo, and Coffee** are the top individual revenue-generating products.
4. **Digital payments** (UPI, Net Banking, Card) dominate; Cash is the least common.
5. Sales show **monthly variation** — certain months exhibit higher footfall and revenue.
6. **Member customers** achieve a slightly higher average transaction value than Normal customers.
7. **Female customers** contribute slightly more total revenue; category preferences differ by gender.
8. **Overall average customer rating is 4.0 / 5.0** — consistently high across all categories.
9. Sales distribution is **right-skewed** — most transactions fall in ₹100–₹700 range.
10. Low-revenue categories (Bakery, Snacks) have **high customer satisfaction**, suggesting a pricing or awareness gap.

---

## Business Insights & Decisions

| Decision | Basis |
|---|---|
| Expand Personal Care & Dairy shelf space in Branch A | These are top categories but under-represented in Jaipur |
| Strengthen loyalty programme for Member customers | Members show higher average transaction values |
| Incentivise digital payment usage | Digital methods already dominant; reinforces cost savings |
| Run promotions for Bakery & Snacks | High ratings + low revenue = awareness/pricing opportunity |
| Build peak-month inventory ahead of high-sales months | Monthly trend shows seasonal demand spikes |
| Gender-targeted category campaigns | Female → Personal Care; Male → Beverages & Grocery |
| Focused growth strategy for Branch A (Jaipur) | Low transactions despite good ratings — marketing gap |
| Bundle offers for low-ticket products | Biscuits, Bread, Chips — high frequency but low basket value |

---

## How to Run the Notebook

### Prerequisites
Install required Python packages:
```bash
pip install -r requirements.txt
```

### Steps
1. Clone or extract this project folder.
2. Ensure the original dataset is present at:
   ```
   data/raw/SUPER MARKET DATA - supermarket_sales_500_rows.csv
   ```
3. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
4. Open:
   ```
   notebook/Archit_Kumar_Chaurasiya_Supermarket_Sales_Analysis.ipynb
   ```
5. Run all cells: **Kernel → Restart & Run All**

The notebook runs from beginning to end without errors.

---

## Project Structure

```
Supermarket_Sales_Analysis/
│
├── data/
│   ├── raw/
│   │   └── SUPER MARKET DATA - supermarket_sales_500_rows.csv   ← Original dataset (unchanged)
│   │
│   └── processed/
│       └── (empty — no processed dataset created; original was sufficient)
│
├── notebook/
│   └── Archit_Kumar_Chaurasiya_Supermarket_Sales_Analysis.ipynb
│
├── Archit_Kumar_Chaurasiya_Supermarket_Sales_Analysis_ProjectReport.docx
├── requirements.txt
└── README.md
```

---

## Conclusion

This project successfully analysed 500 supermarket transactions using only the provided dataset.  
The data was clean and required no modification. All analysis, summaries, and visualisations are directly derived from the original raw data.  
The findings provide clear, actionable guidance for improving branch performance, inventory management, and customer engagement strategies.

---

*No synthetic, fake, or placeholder data was used at any stage of this project.*

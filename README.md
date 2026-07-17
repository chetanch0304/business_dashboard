# 🏦 Banking Customer Analytics Dashboard

An end-to-end data analysis project that turns a raw retail-banking customer dataset into an interactive **Power BI dashboard**, backed by a full **Python EDA pipeline**. The goal was to understand customer financial behavior — deposits, loans, savings, and risk profile — and surface patterns a bank could act on.

---

## 📌 Project Workflow

```
Raw CSV Data → Data Cleaning & Feature Engineering (Python/pandas) → 
Exploratory Data Analysis → Power BI Data Modeling (DAX) → Interactive Dashboard
```

## 📊 Dataset

| | |
|---|---|
| Records | 3,000 customers |
| Columns | 25 (demographic, account, and risk attributes) |
| Missing values | None (clean source) |
| Age range | 17 – 85 (mean ≈ 51) |
| Nationalities | European, Asian, American, Australian, African |
| Loyalty tiers | Jade, Silver, Gold, Platinum |

Key fields: `Estimated Income`, `Superannuation Savings`, `Credit Card Balance`, `Bank Loans`, `Bank Deposits`, `Checking Accounts`, `Saving Accounts`, `Foreign Currency Account`, `Business Lending`, `Properties Owned`, `Risk Weighting`.

## 🔧 Data Cleaning & Preparation

- Parsed `Joined Bank` into a proper datetime field for tenure analysis.
- Engineered an **Income Band** feature (`Low` / `Mid` / `High`) from `Estimated Income` using defined thresholds.
- Mapped coded fields to readable labels — gender codes (`1`/`2` → Male/Female) and branch IDs (`BRId`) → branch names.
- Verified data quality: zero nulls across all 3,000 rows, so no imputation was required.

## 🔍 Exploratory Data Analysis (Python)

- **Univariate analysis**: distribution plots for every numeric account/balance field to check skew and outliers.
- **Categorical analysis**: value-count breakdowns for Gender, Nationality, Occupation, Loyalty Classification, Fee Structure, Risk Weighting, and Income Band.
- **Correlation analysis**: full correlation matrix + heatmap across all balance/account fields.
- **Bivariate deep dives**: regression scatter plots on the strongest relationships (e.g. Bank Deposits vs. Saving Accounts, Bank Loans vs. Credit Card Balance).

## 🧠 Key Insights

- **Deposits and savings move together** — customers with high Bank Deposits also carry high Saving Account balances, suggesting overlapping "total funds held" behavior rather than independent products.
- **Age & income drive accumulation** — older, higher-income customers show moderately higher Superannuation, Savings, and Checking balances, consistent with normal financial lifecycle patterns.
- **Property ownership is a weak predictor** of banking balances, implying it's driven by factors outside this dataset (location, market conditions, inheritance).
- **Business and personal debt are loosely linked** — customers with Business Lending show a moderate correlation with personal Bank Loans, but little relation to deposit-side accounts, pointing to a distinct customer segment.

## 📈 Power BI Dashboard — 4 Pages

| Page | Focus |
|---|---|
| **Home** | Portfolio-level KPIs and summary visuals |
| **Loan Analysis** | Loan distribution by type, branch, and customer segment |
| **Deposit Analysis** | Deposit/savings breakdown and correlation patterns |
| **Summary** | Consolidated EDA findings and demographic trends |

## 🚀 Tools & Technologies

- **Python** (pandas, numpy, matplotlib, seaborn) — cleaning & EDA
- **Power BI** — data modeling, DAX measures, dashboard design
- **Jupyter Notebook** — analysis documentation

## 📁 Repository Structure

```
├── Banking.csv                # Source dataset
├── BankEDA.ipynb              # Python EDA notebook
├── Banking_Dashboard.pbix     # Power BI dashboard
├── README.md
└── PROJECT_REPORT.md          # Detailed methodology & findings
```

## ▶️ How to Run

1. Clone the repo and open `BankEDA.ipynb` in Jupyter to reproduce the EDA.
2. Open `Banking_Dashboard.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) to explore the interactive dashboard.

## 🧠 What I Learned

- Feature engineering (income banding, categorical mapping) for BI-ready data
- Reading correlation matrices to form and validate business hypotheses
- Structuring a multi-page Power BI dashboard for a non-technical audience
- Translating raw EDA output into narrative insights

## 🙏 Credit

Built on a public banking customer dataset commonly used for BI portfolio practice. Data cleaning, EDA, correlation analysis, and dashboard structuring in this repo are my own work.

---
*Feel free to explore the notebook and dashboard — feedback welcome!*

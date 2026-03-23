# Credit Card Spending & Risk Analysis
**Data Analyst Portfolio Project | Mikhail Tabong**  
[mikhail-tabong.github.io](https://mikhail-tabong.github.io)

---

## Overview
This project simulates the workflow of a data analyst at a financial institution like Capital One or JPMorgan Chase. Raw credit card transaction data is ingested, cleaned, and analyzed to surface three categories of business insight: spending patterns, customer segmentation, and transaction risk flags.

The final deliverable is an interactive Streamlit dashboard that a risk team, credit underwriting team, or product manager could realistically use to monitor portfolio health.

---

## Business Problem
Financial institutions process millions of credit card transactions daily. Analysts need to quickly answer questions like:
- Where are customers spending, and how is that changing month over month?
- Which customers are high-value vs. low-utilization?
- Which transactions look anomalous relative to a customer's normal behavior?

This project builds a lightweight analytics pipeline to answer all three.

---

## Dashboard Views
| View | Description |
|------|-------------|
| Spend Breakdown | Total and monthly spend by merchant category |
| Customer Segmentation | Customers grouped into spend tiers (Low / Medium / High / Premium) |
| Risk Flag Table | Transactions flagged as Elevated (2x avg) or High Risk (3x avg) |

---

## Tech Stack
| Layer | Tool |
|-------|------|
| Language | Python 3.10+ |
| Data Wrangling | pandas, numpy |
| SQL Engine | DuckDB |
| Visualization | Plotly |
| Dashboard | Streamlit |
| Notebook | Jupyter Notebook |
| Deployment | Streamlit Community Cloud |

---

## Project Structure
```
credit-card-risk-analysis/
│
├── data/
│   ├── credit_card_transactions.csv      # Raw dataset (not committed to repo)
│   └── processed/                        # Cleaned outputs from notebook
│       ├── transactions_clean.csv
│       ├── spend_by_category.csv
│       ├── monthly_spend.csv
│       ├── customer_summary.csv
│       ├── flagged_transactions.csv
│       └── mom_by_category.csv
│
├── credit_card_risk_analysis.ipynb       # EDA, cleaning, SQL analysis
├── app.py                                # Streamlit dashboard
├── requirements.txt                      # Dependencies
└── README.md
```

---

## How to Run Locally

**1. Clone the repo**
```bash
git clone https://github.com/YOUR_USERNAME/credit-card-risk-analysis.git
cd credit-card-risk-analysis
```

**2. Create and activate a virtual environment**
```bash
python -m venv venv
source venv/bin/activate        # Mac
venv\Scripts\activate           # Windows
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Add the dataset**  
Download the dataset from [Kaggle](https://www.kaggle.com/datasets/priyamchoksi/credit-card-transactions-dataset) and place it at `data/credit_card_transactions.csv`

**5. Run the notebook**  
Open `credit_card_risk_analysis.ipynb` and run all cells to generate the processed data files.

**6. Launch the dashboard**
```bash
streamlit run app.py
```
Opens at `http://localhost:8501`

---

## Dataset
- **Source:** [Kaggle — Credit Card Transactions Dataset](https://www.kaggle.com/datasets/priyamchoksi/credit-card-transactions-dataset)
- **Size:** ~1.8M transactions
- **Note:** Synthetic data — no real PII involved

---

## Key SQL Techniques Used
- Window functions (`LAG`, `SUM OVER`, `AVG OVER`) for month-over-month analysis
- CTEs for customer baseline calculation
- Aggregations across customer, category, and time dimensions
- Rule-based anomaly detection using per-customer rolling averages

---

## Live Demo
[View on Streamlit Community Cloud](#) ← *(update after deployment)*

---

*Built as part of a data analyst portfolio targeting roles in financial services.*

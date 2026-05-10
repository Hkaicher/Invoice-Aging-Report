# 📊 Invoice Aging Report 

A data analysis project built with Python (Pandas, NumPy, Matplotlib) that cleans, processes, and analyzes invoice data to produce an **accounts receivable aging report**.

---

## 📁 Project Structure

```
├── week2_hw_Hamdan_kaicher_ipynb.ipynb   # Main Jupyter Notebook
├── invoices_bd.csv                        # Source dataset (205 invoices)
├── aging_report_csv                       # Exported aging report output
└── README.md
```

---

## 🔍 Project Overview

This project processes a raw invoice dataset from Bangladesh and answers key business questions about outstanding payments. The analysis is broken into four structured parts:

| Part | Description |
|------|-------------|
| 1 | Load & Explore the dataset |
| 2 | Data Cleaning (nulls, duplicates, types, strings) |
| 3 | Build an Aging Report with overdue buckets |
| 4 | Analysis, Visualization & Export |

---

## 🧰 Libraries Used

- **Pandas** — data loading, cleaning, groupby, pivot tables
- **NumPy** — numerical operations
- **Matplotlib** — bar chart visualization of aging summary

---

## 🧹 Data Cleaning Steps

- Identified and handled **missing values** in `customer_name`, `paid_amount_bdt`, and `payment_date`
- Filled unpaid invoice amounts with `0` (status-aware decision)
- Removed **duplicate invoice IDs** using `keep='first'` to preserve original values
- Converted date columns (`invoice_date`, `due_date`, `payment_date`) to `datetime`
- Converted `amount_bdt` to numeric
- Standardized string casing (`.str.title()`, `.str.strip()`)
- Fixed city name inconsistency: `'dhaka'` → `'Dhaka'`

---

## 📦 Aging Buckets

Outstanding invoices (status: `Unpaid` or `Partial`) were categorized into aging buckets based on days overdue:

| Bucket | Days Overdue |
|--------|-------------|
| Current | 0–30 days |
| 31–60 Days | 31–60 days |
| 61–90 Days | 61–90 days |
| 90+ Days | 91+ days |

---

## 📈 Key Findings

- **Dhaka** has the highest total outstanding amount among all cities
- **Fatima Enterprises** holds the largest outstanding balance: **605,100 BDT**, requiring priority follow-up
- A pivot table summarizes outstanding balances by customer and aging bucket
- Weighted average days overdue calculated per customer for deeper risk assessment

---

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   cd YOUR_REPO_NAME
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib jupyter
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook week2_hw_Hamdan_kaicher_ipynb.ipynb
   ```

4. Place `invoices_bd.csv` in the same directory before running.

---

## 📤 Output

The aging report is exported as a CSV file (`aging_report_csv`) with each customer's outstanding balance broken down by aging bucket and a calculated **Total** column.

---

## 👤 Author

**Hamdan Kaicher**

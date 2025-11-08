# MR D.I.Y. Junior Data Engineer Assessment
**Candidate:** Chong Zhao Cheng (Zack)  
**Company:** MR D.I.Y. Trading Sdn Bhd  
**Section 2:** Technical Knowledge – Data Transformation using SQL & Python

---

## Overview & Objective
This repository contains the deliverables for the SQL and Python technical assessment.
Both implementations independently transform the raw dataset (`sql_test-raw`) into the final expected output (`sql_test-expected`),
calculating the required business metrics and presenting them in a structured pivot-style format.

---

## 🗂️ Dataset Description

**Input file:** `excel_sample_data_de.xlsx`  
**Sheet:** `sql_test-raw`

| Column Name | Description |
|--------------|-------------|
| `month` | Transaction month (in Excel date format displayed as `Jan-25`) |
| `product` | Product name |
| `store_code` | Store identifier |
| `category` | Product category (e.g. Beverage, Snack, Dairy) |
| `sales_qty` | Quantity sold |
| `sales_amt` | Total sales amount |
| `sales_cost` | Total cost of sales |

---

## Key Transformation Metrics

| Metric | Formula | Description |
|--------|----------|-------------|
| **Profit** | `sales_amt - sales_cost` | Calculates profit per product |
| **Sales Qty Contribution by Category** | `sales_qty / total monthly sales_qty (by category)` | Product’s quantity contribution |
| **Sales Amt Contribution by Category** | `sales_amt / total monthly sales_amt (by category)` | Product’s revenue contribution |
| **Sales Cost Contribution by Category** | `sales_cost / total monthly sales_cost (by category)` | Product’s cost contribution |
| **Profit Contribution by Category** | `profit / total monthly profit (by category)` | Product’s profit share |

---

## SQL Transformation

- Implemented using **MySQL** (`sql/Data Transformation (SQL).sql`).
- Script includes:
  - Database & table creation  
  - Data insertion  
  - Metric computation  
  - Pivot-style aggregation by month and metric  
- Final output exported as `sql_test-expected (SQL).csv`.

**NOTE:** Refer to [README_SQL.md](sql/README_SQL.md) for detailed setup and execution steps.

---

## Python Transformation

- Implemented in **Jupyter Notebook** (`python/Data Transformation (Python).ipynb`).
- Uses **pandas** for data manipulation and pivoting.
- Exports the final result as `sql_test-expected (Python).xlsx`.

**NOTE:** Refer to [README_Python.md](python/README_Python.md) for detailed setup and execution steps.

---

## 📁 Repository Structure

```
mrdiy-junior-data-engineer-assessment/
│
├── 📁 data/
│   └── Section_2_Instructions.md                 # Original Section 2 Instructions from word file provided
|   └── excel_sample_data_de.xlsx                 # Original dataset provided
│
├── 📁 sql/
│   ├── Data Transformation (SQL).sql             # SQL script with table creation & transformation
│   ├── sql_test-expected (SQL).csv               # Final output from SQL query (exported)
│   └── README_SQL.md                             # SQL setup & execution userguide
│
├── 📁 python/
│   ├── Data Transformation (Python).ipynb        # Python Jupyter Notebook transformation
│   ├── sql_test-expected (Python).xlsx           # Final output from Python pivot table
│   └── README_Python.md                          # Python setup & execution user guide
│
└── README.md                                     # Main overview file 
└── LICENSE                                       # MIT License
```

---

## ⚠️ Notes & Clarifications on Metrics

Although the assessment requirements mention four metrics
(profit, sales qty contribution, sales amt contribution, profit contribution),
the reference file sql_test-expected also includes sales cost contribution by category.
Both SQL and Python implementations include this metric for completeness.

> The original assessment brief listed four required metrics:
> 1. Profit  
> 2. Sales Qty Contribution by Category  
> 3. Sales Amt Contribution by Category  
> 4. Profit Contribution by Category  
>
> However, the provided reference output (`sql_test-expected` in *excel_sample_data_de.xlsx*) also included  
> **Sales Cost Contribution by Category**.
>
> To ensure alignment with the expected results, **both SQL and Python transformations include this additional metric**.  
> This was done intentionally for consistency and completeness.

---

## 🧾 Output Format Note

Both SQL and Python outputs contain the same values and correct metric order,
but differ slightly in table layout due to the formatting behavior of each platform.

| Implementation | Output Format | Example |
|--------|----------|-------------|
| SQL | Flattened columns | Jan_25_sales_qty_contribution_by_category, Feb_25_... |
| Python | Multi-level pivot (month grouped above metrics) | Jan-25 → [sales_qty, sales_amt, sales_cost, profit] |

✅ All calculated values have been verified identical to the reference sql_test-expected.
The only difference lies in table presentation, not in the underlying data or logic.

---

## 📤 Submission Details

- **Excel Section:** Completed directly in the provided Excel file  
- **Technical Section (SQL & Python):** Hosted in this GitHub repository  
- **Aptitude Section:** Completed in the provided Word document  

For clarification or review, please refer to this repository or contact me directly.

---

## 👤 Author Information

Name: Zack Chong Zhao Cheng
Email: chongzhaocheng06@gmail.com
Education: B.Sc. (Hons) Statistical Data Modelling — Sunway University
Date Submitted: 9th November 2025
LinkedIn: *[`LinkedIn Profile`](http://linkedin.com/in/chong-z-38b102131)* 

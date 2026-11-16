# IndiaKart E-Commerce Analytics Dashboard

End-to-end analytics project on IndiaKart e-commerce data: data cleaning and quality checks, SQL analysis, KPI development, an interactive Power BI dashboard, and an executive (CEO) report with business recommendations.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoftexcel&logoColor=white)

---

## 📖 Project Overview

I worked as a Junior Data Analyst for **IndiaKart**, an Indian e-commerce marketplace. Using **222,200 records across 8 relational tables**, I cleaned and validated the data, calculated business KPIs, answered business questions with SQL, built an interactive Power BI dashboard, and wrote a CEO report with clear recommendations.

## 🎯 Business Problem

IndiaKart's management wanted answers to these questions:

- Which product categories generate the most revenue, and is the business too dependent on one of them?
- Which states contribute the most sales?
- How are cancellations and returns affecting revenue?
- Which customer segments are the most valuable?
- Is the business growing, and what should management fix first?

## 🗂️ Dataset

| Metric | Value |
|---|---|
| Source | IndiaKart internship project dataset |
| Tables | 8 (orders, order_items, customers, products, payments, returns, inventory, suppliers) |
| Total records | 222,200 |
| Orders | 50,000 |
| Period covered | 24 June 2023 – 23 June 2025 |

## 🔄 Workflow

```
Data Cleaning → KPI Calculation → SQL Analysis → Power BI Dashboard → CEO Report
```

## 🧹 Phase 1 – Data Cleaning & Quality Check

Profiled all 8 tables and checked nulls, duplicates, data types, outliers and table-to-table links (referential integrity).

- **0 duplicate rows**; all foreign keys valid (0 orphan records)
- Nulls only in `delivered_date` (valid: only delivered orders have a date) and `payments.refund_date`
- Found **hidden business-logic issues**:
  - **10,255 orders** placed before the customer's registration date
  - **1,740 return records** linked to orders that were Cancelled or Shipped
  - 312 orders above ₹5 lakh (0.62% of orders, 5.8% of GMV) flagged as outliers
  - 78 products low or out of stock

## 📈 Phase 2 – KPI Analysis

| KPI | Result | Target | Status |
|---|---|---|---|
| GMV | ₹314.7 Cr | – | – |
| Net Revenue (delivered orders) | ₹205.4 Cr (65.3% of GMV) | – | – |
| Average Order Value | ₹63,198 | – | – |
| Cancellation Rate | 11.99% | < 10% | ❌ |
| Payment Failure Rate | 3.50% | < 2% | ❌ |
| Inventory Fill Rate | 92.2% | > 95% | ❌ |
| Return Rate (return records ÷ delivered orders) | 30.8% (12.1% by *Returned* status) | < 8% | ❌ |

## 🗄️ Phase 3 – SQL Analysis

12 business queries plus my own extra queries, using JOINs, GROUP BY, HAVING, aggregate functions, CASE statements, subqueries and CTEs:

- Monthly revenue trend, category-wise sales, state-wise revenue
- Customer segments and lifetime value
- Payment methods and failure rate by gateway
- Return rate by category, top products, supplier performance
- Inventory health by warehouse, channel performance, festive-season sales
- **My own extra queries:** what happened to failed-payment orders, rupee value lost, data-quality checks, and a what-if on reducing cancellations

## 📊 Phase 4 – Power BI Dashboard & CEO Report

An interactive dashboard with a data model, DAX measures, KPI cards, charts and slicers, plus an executive report for the CEO.

<!-- Add your dashboard screenshots below -->
![Dashboard Overview](images/dashboard-overview.png)

📄 CEO Report: [`report/Phase4_Report_Vaishali.docx`](report/Phase4_Report_Vaishali.docx)

## 💡 Key Insights

1. **Sales have stopped growing.** Year 2 sales were ₹157.1 Cr vs ₹157.7 Cr in Year 1 (**−0.4%**).
2. **Too dependent on one category.** Electronics earns **57.4%** of revenue, while Grocery, Books and Beauty & Health together bring only about 2%.
3. **Failed payments are costing money.** All **1,748** failed payments ended as cancelled orders worth about **₹10.7 Cr**, which explains about **29%** of all cancellations.
4. **Premium customers are the most valuable.** They are only 15% of customers but place **8.6 orders each** vs 5.7 for Regular customers.
5. **Two states drive the business.** Uttar Pradesh and Maharashtra together bring about **35%** of orders.
6. **Returns are not a category problem.** Return rates are similar across all categories (about 20–21%), so the causes are likely operational: quality, packaging and delivery. About 56% of returns are for reasons the company can control (damaged, wrong or defective products).

## ✅ Recommendations

1. **Offer an alternative payment method when a payment fails** to recover cancelled orders. Bringing cancellations down from 12% to 10% could save about **996 orders (≈ ₹6.1 Cr)**.
2. **Grow categories other than Electronics** to reduce concentration risk.
3. **Run targeted offers for Premium customers** and focus marketing on Uttar Pradesh and Maharashtra to bring growth back.
4. **Re-order the 78 low or out-of-stock products** to reach a 95%+ fill rate.
5. **Review suppliers** with defective or poor-quality products to cut controllable returns.
6. **Fix data quality issues** (orders before registration, returns on cancelled orders) before numbers go into official reports.

## 🛠️ Tools Used

Power BI (DAX), SQL, Python (Pandas, Matplotlib), Excel

## 📁 Repository Structure

```
IndiaKart-ECommerce-Analytics/
├── notebooks/   # Phase 1 cleaning, Phase 2 EDA, Phase 3 KPIs, SQL analysis
├── powerbi/     # Power BI dashboard (.pbix)
├── report/      # CEO report
├── images/      # Dashboard and chart screenshots
└── README.md
```

## 👩‍💻 About Me

**Vaishali Girase** – Aspiring Data Analyst | Excel · SQL · Power BI · Tableau
Valsad, Gujarat, India
💼 [LinkedIn](https://www.linkedin.com/in/vaishali-girase-539bb2433/)

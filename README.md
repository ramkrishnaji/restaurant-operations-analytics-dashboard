# 📊 Restaurant Operations & Customer Analytics Dashboard (Power BI)

An end-to-end business intelligence project modeling and visualizing **200,000+ transactional orders** across **20,000 customers** and **56,250 restaurants**. This dashboard translates raw, noisy transaction logs into actionable operational insights, focusing on logistics optimization, customer retention cohorts, and restaurant performance.

---

## 📸 Dashboard Preview (Restaurant.pdf)

---

## 🚀 Key Achievements & Business Impact
*   **Identified Logistical Risk**: Uncovered that **48.12% of orders (96.23K)** breached the 45-minute delivery SLA, indicating a systemic courier dispatch or vendor preparation delay.
*   **Advanced Data Cleaning**: Audited and cleansed a highly corrupted Zomato-based Excel dataset containing column-shifting anomalies affecting **8.03% of restaurants** and **5.05% of customers**.
*   **Customer Cohort Segmentation**: Designed a repeat-customer tracking model showing that **99.94%** of the customer base are repeat orderers (averaging 10 orders per customer).
*   **Modeled ₹164.9M in Sales**: Tracked revenue trends across 33 months (Jan 2023 – Sep 2025) with a stable Average Order Value (AOV) of **₹824.57**.

---

## 📁 Repository Structure
```
├── Restaurant.pbix               # Main Power BI Project file (Data Model & Visuals)
├── Restaurant.pdf                # PDF export of the complete dashboard (for quick recruiter viewing)
├── dataset.xlsx                  # Raw transactional dataset (Orders, Customers, Restaurants, Dates)
├── CALCULATED_COLUMNS_AND_MEASURES.txt  # DAX formulas cheat sheet
└── README.md                     # Project summary & recruiter guide
```
----

## 🛠️ Tech Stack & Methodology
*   **Visualization & Modeling**: Power BI Desktop
*   **Data Transformation**: Power Query (M Language)
*   **Analytical Computations**: DAX (Calculated Columns & Core Measures)
*   **Data Audit & Scripting**: Python (Pandas) for data quality analysis
*   **Data Schema**: Star Schema (1 Fact Table: `Orders`; 3 Dimension Tables: `Customers`, `Restaurants`, `DateTable`)

---

## 🎯 Executive Summary & Metrics

### 1. Operations & Logistics (Core KPIs)
*   **Total Revenue**: ₹164,914,494
*   **Total Orders**: 200,000
*   **Average Order Value (AOV)**: ₹824.57
*   **Average Delivery Time**: 44.55 minutes
*   **Order Completion Rate**: **80.11% Delivered** | **9.97% Cancelled** | **9.91% Delayed**

### 2. Customer Cohorts
*   **New Customers**: ₹81.9M Revenue | 99,397 Orders | 9,945 Customers
*   **Returning Customers**: ₹66.4M Revenue | 80,547 Orders | 8,052 Customers
*   **Premium Customers**: ₹16.6M Revenue | 20,056 Orders | 2,003 Customers

### 3. Top Performing Districts (by Volume)
1.  **BTM Layout**: 18,685 orders | ₹15.37M Revenue (Dominating **~9.3%** of total business)
2.  **Koramangala 5th Block**: 9,118 orders | ₹7.58M Revenue
3.  **HSR Layout**: 9,088 orders | ₹7.50M Revenue

---

## ⚠️ Data Quality Audit & Transformations
Data Analysts must verify data integrity before reporting. This project highlights a real-world scenario of **CSV-to-Excel delimiter shifting**:

1.  **Shifted Restaurants (8.03% of DB)**: Commas/newlines in text shifted columns, moving raw review content into the `online_order` and `book_table` columns. Shifted rows were programmatically isolated and cleansed.
2.  **Shifted Cities (5.05% of Customers)**: Long review text entered the `City` column. While the Power BI `FilterCity` length filter caught **50.5%** of these, **49.5%** (short fragments like `('Rated 4.0'`) leaked into the final database. A custom regex filter was created to guarantee clean geo-reporting.

---

## 💡 Business Recommendations
1.  **Optimize Courier Dispatch in BTM & Koramangala**: Since BTM accounts for nearly 10% of total revenue, deploying dedicated driver hubs there will reduce the **48.12% late delivery rate**.
2.  **SLA Penalty for Delayed Vendors**: Since average delivery is 44.55 minutes (just under the 45-minute late mark), enforce order-prep time limits for merchant partners to prevent late deliveries.
3.  **Monetize Returning Cohorts**: With a high repeat rate (**99.94%**), introduce a loyalty subscription program (similar to Zomato Gold) to shift high-frequency "Returning" users to high-margin "Premium" users.

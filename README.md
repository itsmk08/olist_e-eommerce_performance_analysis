# 📊 End-to-End Data Analytics Project  
## Olist E-Commerce Pipeline (Brazilian E-Commerce Dataset)

**Submitted by:** Mohan Koirala  
**Date:** 04/09/2026  

---

## 📌 Project Overview

This project simulates a real-world end-to-end data analytics pipeline using the **Olist Brazilian E-Commerce dataset (Kaggle)**. It demonstrates data ingestion, cleaning, transformation, modeling, and visualization across multiple tools including **PostgreSQL, Python (Pandas), Excel, Google Sheets, and Power BI**.

The goal is to transform raw transactional data into actionable business insights for decision-making.

---

## 🧱 Tech Stack

- **PostgreSQL** – Structured data storage & SQL transformations  
- **Python (Pandas, NumPy)** – Data cleaning & feature engineering  
- **Microsoft Excel** – Data sanitization & reference tables  
- **Google Sheets** – Target metrics tracking  
- **Power BI** – Data modeling & interactive dashboards  

---

## 📂 Dataset Description

- Source: Kaggle – Brazilian E-Commerce Public Dataset by Olist  
- Time Period: 2016–2018  
- Records: ~100,000+ orders  
- Files Used:
  - Orders
  - Order Items
  - Customers
  - Sellers
  - Products
  - Payments
  - Reviews
  - Geolocation
  - Product Category Translation

---

## 🏗️ Data Architecture

A **Star Schema** model was implemented for analytical efficiency.

### Fact Table:
- `Fact_Orders` (transactions, payments, delivery metrics, pricing)

### Dimension Tables:
- `Dim_Customers`
- `Dim_Products`
- `Dim_Sellers`
- `Dim_Date`

### 📌 Star Schema Diagram:
![Star Schema]()

---

## ⚙️ Data Pipeline Workflow

### 1. PostgreSQL (Core Data)
- Stored transactional tables
- Performed SQL-based cleaning
- Built RFM segmentation using window functions
- Handled null values using `COALESCE`

### 2. Excel (Reference Data)
- Cleaned product category mappings
- Standardized text using `PROPER()` and `TRIM()`
- Checked missing product attributes

### 3. Python (Pandas)
- Handled missing review comments
- Converted date fields using `pd.to_datetime()`
- Created delivery delay features
- Fixed geolocation inconsistencies

### 4. Google Sheets
- Maintained executive-level KPI targets
- Tracked monthly performance benchmarks

---

## 🔄 Data Transformations

- RFM Segmentation using SQL (`NTILE(5)`)
- Revenue calculation from order items
- Delivery variance classification:
  - On Time
  - Slightly Delayed
  - Severely Delayed
- Customer behavioral grouping
- Time-based feature engineering

---

## 📊 Power BI Dashboard

### 🧭 Page 1: Executive Overview (Z-Pattern Layout)

Key KPIs:
- Total Revenue
- Total Orders
- Average Order Value (AOV)
- Growth Trends
- Fulfillment Rate

Visuals:
- Revenue trend over time
- Revenue by region (map of Brazil)
- Top product categories
- Target vs actual performance

📸 Dashboard Preview:
![Executive Dashboard](/img/executive.png)

---

### 🔍 Page 2: Deep Dive Analysis (F-Pattern Layout)

Features:
- Slicers (Date, Region, Category, Payment Type)
- Decomposition Tree (Revenue drivers)
- Regional performance breakdown
- Profitability analysis

📸 Dashboard Preview:
![Deep Dive Dashboard](img/deep%20analysis.png)

---

## 📐 Data Model

- Central Fact Table: `Fact_Orders`
- Connected Dimension Tables via 1-to-Many relationships
- Date Dimension created using `CALENDARAUTO()`

---

## 📈 Key Insights

- Delivery times are generally faster than estimated, but forecasting needs improvement.
- Revenue shows steady growth but does not fully meet target benchmarks.
- Revenue is heavily concentrated in a few regions and product categories.

---

## 💡 Strategic Recommendations

- Improve delivery estimation models
- Expand operations in underperforming regions
- Strengthen high-performing product categories
- Apply RFM-based customer segmentation for targeted marketing

---

## 📁 Folder Structure (Suggested)

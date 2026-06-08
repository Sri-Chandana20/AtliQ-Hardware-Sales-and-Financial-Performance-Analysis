<p align="center">
  <img src="atliq_logo.png" width="140"/>
</p>

<h1 align="center"> AtliQ Hardware Business Performance Analysis </h1>

### Overview
This project analyzes the sales and financial performance of AtliQ Hardware using Microsoft Excel. The objective is to provide a consolidated view of business performance by evaluating customer sales, market performance against targets, and profitability trends across fiscal years and quarters.

The analysis helps stakeholders monitor business performance, identify top-performing customers and markets, evaluate target achievement, and understand revenue and profit trends for informed decision-making.

---

### Business Problem
Management requires a centralized reporting solution to track sales performance, compare actual results against targets, and assess financial performance across different time periods. This project addresses that need by transforming raw business data into actionable reports and insights.

---

### Table of Contents

- Data Source

- Data Cleaning & Transformation
  
- Data Modeling
  
- DAX Measures

- Tools & Technologies Used 

- Key Insights
  
- Recommendations
  
- Business Questions

- Acknowledgments

---

### Data Source 

The dataset consists of 3 dimension tables and 2 fact tables.

**Dimension Tables:** dim_customer, dim_market, and dim_product

**Fact Tables:** fact_sales_monthly, and ns_targets_2021

---

### Data Cleaning & Transformation

To ensure data quality and support accurate analysis, the following data preparation steps were performed:

* Standardized text values to maintain consistency across the dataset.
* Identified and corrected spelling mistakes and typographical errors.
* Created a Date Dimension table to derive fiscal year information and support time-based analysis.
* Established relationships between relevant tables using Power Pivot's Data Model.
* Created calculated columns in Power Pivot, including:

  * Total COGS (Cost of Goods Sold)
  * Fiscal Year
  * Fiscal Quarter
* Prepared the dataset for customer sales analysis, market performance analysis, and P&L reporting.

---

### Data Modeling
























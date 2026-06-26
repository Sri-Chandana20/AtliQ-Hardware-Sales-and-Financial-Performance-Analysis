<p align="center">
  <img src="atliq_logo.png" width="140"/>
</p>

<h1 align="center"> AtliQ Hardware Sales & Financial Performance Analysis </h1>

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

- Business Questions Answered
  
- Recommendations

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

- Designed a **star schema** with fact_sales_monthly and ns_targets_2021 as the central fact tables connected to dimension tables such as customer, market, product, and date through **one-to-many** relationships.

- All **relationships** were configured as **active** to ensure accurate aggregation across metrics.

---

### DAX Measures

### Base Measures

```DAX
Net Sales =
SUM(fact_sales_monthly[net_sales_amount])
```

```DAX
COGS =
SUM(fact_sales_monthly[total_COGS])
```

```DAX
Gross Margin =
[Net Sales] - [COGS]
```

```DAX
GM% =
DIVIDE([Gross Margin], [Net Sales], 0)
```

### Year-wise Net Sales Measures

```DAX
NetSales19 =
CALCULATE([Net Sales], dim_date[FY] = "2019")
```

```DAX
NetSales20 =
CALCULATE([Net Sales], dim_date[FY] = "2020")
```

```DAX
NetSales21 =
CALCULATE([Net Sales], dim_date[FY] = "2021")
```

### Target Measure

```DAX
Target21 =
SUM(ns_targets_2021[ns_target])
```

### Variance Analysis Measures

```DAX
2021 - Target =
[NetSales21] - [Target21]
```

```DAX
Variance % =
DIVIDE([2021 - Target], [Target], 0)
```

### Year-over-Year Growth Measure

```DAX
21 vs 20 =
DIVIDE([NetSales21], [NetSales20], 0)
```

---

### Tools & Technologies Used

- Microsoft Excel
  
- Power Query (Data Extraction, Transformation & Loading - ETL)
  
- Power Pivot (Data Modeling & Analysis)
  
- DAX (Data Analysis Expressions)
  
- Star Schema Data Modeling
  
- Pivot Tables & Financial Reporting
  
- CSV Files (Data Source)
  
---

### Business Questions Answered

**1. Which customers generated the highest revenue in 2021?**

The top revenue-generating customers in 2021 included:

- Amazon – 82.1M

- AtliQ Exclusive – 61.1M

- Atliq e Store – 53.0M

- Sage – 20.7M

- Flipkart – 19.3M

The highest revenue contributors in 2021 included company-owned sales channels (AtliQ Exclusive and Atliq e Store) as well as external retail partners such as Amazon, Sage, and Flipkart.

---

**2. Which customers showed the highest growth between 2020 and 2021?**

Several customers demonstrated exceptional year-over-year growth. Notable examples include:

- Nova – 2664.9%
  
- Integration Stores – 887.2%

- Chiptec - 722.0%

- Electricalsquipo Stores – 535.3%

- Logic Stores – 515.2%

These customers experienced rapid sales expansion compared to the previous year.

---

**3. Which markets generated the highest revenue in 2021?**

The highest-performing markets in 2021 were:

- India – 161.3M

- USA – 87.8M

- South Korea – 49.0M

- Canada – 35.1M

- United Kingdom – 34.2M

These markets represented the largest share of overall revenue.

---

**4. Did the company achieve its 2021 sales targets across markets?**

No. Overall sales were 54.9M below target, resulting in a -8.4% variance against the 2021 target. Every market reported negative variance against target, indicating opportunities for performance improvement.

---

**5. Which markets were closest to achieving their 2021 targets?**

The markets with the smallest negative variance were:

- Japan (-4.1%)

- Portugal (-4.3%)

- India (-5.9%)

These markets performed relatively better against their assigned targets compared to other regions.

---

**6. How has profitability changed across fiscal years?**

Although Gross Margin increased significantly, Gross Margin Percentage declined from **41.4% in FY2019 to 36.4% in FY2021.** This suggests that revenue grew faster than profitability and may warrant further analysis of cost structures.

---

**7. Which quarters generated the highest revenue & profitability in FY2021?**

In FY2021, Q1 generated the highest revenue (173.8M), followed by Q2 (164.7M). Revenue gradually declined during Q3 and Q4.

Also, Q1 generated the highest Gross Margin (63.3M), followed by Q2 (60.0M). 

This indicates that the first half of FY2021 contributed most significantly to revenue & profitability.

---

**8. How consistent was Gross Margin % across quarters?**

Gross Margin % remained relatively stable within each fiscal year. In FY2021, GM% was approximately 36.4% across all four quarters, indicating consistent profitability performance throughout the year.

---

### Recommendations

- Company-owned channels such as AtliQ Exclusive and Atliq e Store, along with major external partners such as Amazon and Flipkart, contributed significantly to 2021 revenue. The business can continue investing in these channels and partnerships to support future growth.

- Although overall sales grew substantially in 2021, the company missed its overall target by 8.4%. Markets with larger negative variances should be reviewed to understand issues related to sales execution, market demand, competition, or target-setting assumptions.

---

### Acknowledgments

Special thanks to **Dhaval Patel Sir, Hemanand Vadivel Sir, and Codebasics** for providing the dataset used in this analysis project.
The dataset enabled hands-on practice in data transformation, data modeling, and Sales & Finance analysis.

























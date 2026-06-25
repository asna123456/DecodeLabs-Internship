# DecodeLabs Internship

This repository contains my projects and learning outcomes from the DecodeLabs Data Analytics Internship (Batch 2026).

## About the Internship

During this internship, I am working on real-world data analytics projects involving data cleaning, exploratory data analysis, and data visualization.

# Projects Completed

## Project 1: Data Cleaning & Preparation

### Objective:
Clean and prepare raw datasets to improve data quality and make the data ready for analysis.

### Tasks Performed:
- Identified missing values
- Handled missing data
- Checked duplicate records and IDs
- Validated date and data formats
- Prepared cleaned dataset for analysis

### Tools Used:
- Microsoft Excel

### Dataset Details:
- Rows: 1200
- Columns: 14

### Project Outcome:
- Duplicate IDs verified: 0
- Duplicate records verified: 0
- Data formats validated successfully

📂 View Project 1

---

# Project 2: Exploratory Data Analysis (EDA)

### Objective:
Analyze the dataset to discover patterns, trends, distributions, and outliers using analytical methods.

### Tasks Performed:
- Calculated descriptive statistics (Mean, Median, Count)
- Performed product-wise sales analysis
- Analysed payment method distribution
- Studied monthly sales trends
- Identified outliers using data distribution analysis
- Created charts and summarized key insights

### Tools Used:
- Microsoft Excel
- Pivot Tables
- Data Visualization Charts

### Dataset Details:
- Rows: 1200
- Columns: 14

### Project Outcome:
- Identified sales patterns and trends
- Analysed customer payment preferences
- Found top-performing products
- Generated meaningful business insights from data

📂 View Project 2

---

# Skills Practiced

- Data Cleaning
- Data Preparation
- Exploratory Data Analysis (EDA)
- Excel Data Handling
- Pivot Tables
- Data Visualization
- Descriptive Statistics
- Analytical Thinking

# Internship Provider

DecodeLabs  
Data Analytics Internship - Batch 2026


### Project 3: SQL Data Analysis

**Objective:**
Step into the role of a Data Analyst to extract actionable business intelligence from raw transactional data using structured SQL queries and pure relational logic.

**Tasks Performed:**
- Handled text-to-numeric type conversions using dynamic type casting (`CAST`)
- Isolated transactional rows by filtering out embedded table headers (`WHERE`)
- Performed product-wise sales aggregations (`SUM`, `GROUP BY`)
- Analyzed customer purchasing behavior and cart sizes by payment preferences (`AVG`)
- Ordered and ranked business insights for precise reporting (`ORDER BY`)

**Tools Used:**
- SQLite / DB Browser for SQLite

**Dataset Details:**
- Rows: 1201 (including header)
- Columns: 14

**Project Outcome & Key Insights:**
- **Grand Total Volume:** Verified 1,201 total records accounting for a grand total revenue of **1,264,761.96**[cite: 1]
- **Top Product Category:** **Chairs** emerged as the top revenue contributor generating **195,620.11**, closely followed by Printers at **195,612.61**[cite: 1]
- **Consumer Behavior:** Customers paying with **Cash** checked out with the largest average cart sizes (**5.72 items**), whereas **Online** transactions showed the lowest average volumes (**5.23 items**)[cite: 1]

#### 🛠️ Core Queries Executed:
```sql
-- 1. Grand Total Sales Verification
SELECT COUNT(*) AS Total_Orders, SUM(CAST(field14 AS REAL)) AS Total_Sales 
FROM orders WHERE field14 != 'TotalPrice';

-- 2. Total Sales by Product Category
SELECT field4 AS Product, SUM(CAST(field14 AS REAL)) AS Total_Revenue
FROM orders WHERE field4 != 'Product'
GROUP BY field4 ORDER BY Total_Revenue DESC;

-- 3. Average Items per Cart by Payment Method
SELECT field8 AS Payment_Method, AVG(CAST(field11 AS REAL)) AS Avg_Items
FROM orders WHERE field8 != 'PaymentMethod'
GROUP BY field8 ORDER BY Avg_Items DESC;



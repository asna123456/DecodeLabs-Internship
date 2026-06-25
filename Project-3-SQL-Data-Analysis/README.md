# Project 3: SQL Data Analysis - DecodeLabs Internship

This folder contains my queries, database files, and learning outcomes for Milestone 3 (SQL Data Analysis) of the DecodeLabs Industrial Training Program.

##  Project Overview
The objective was to query a relational database containing **1,201 transaction records** using SQLite to discover trends across product categories, revenues, and customer purchasing habits.

### Key Skills Demonstrated:
- **SQL Data Aggregation:** `COUNT()`, `SUM()`, `AVG()`
- **Relational Logic & Structuring:** `WHERE`, `GROUP BY`, `ORDER BY`
- **Data Wrangling & Type Casting:** Handling dirty CSV data structures, string-to-numeric data type transformation using `CAST()`.

---

##  Tech Stack Used
- **Database Engine:** SQLite (DB Browser for SQLite)
- **Source Format:** CSV UTF-8 (Converted from raw Excel dataset)

---

##  Key Insights Discovered

### 1. Grand Total Volume & Sales Revenue
- **Total Orders Processed:** 1,201 orders
- **Grand Total Revenue:** 1,264,761.96
- **SQL Query Used:**
   ```sql
   SELECT COUNT(*) AS Total_Orders, 
       SUM(CAST(field14 AS REAL)) AS Total_Sales 
       FROM orders 
    WHERE field14 != 'TotalPrice'; 

### 2. Revenue Breakdown by Product Category
 -  **Top Performing Product:** Chair generated the highest total revenue of 195,620.11.
 -  **Close Competitor:** Printer came second with a total revenue of 195,612.61.
 -  **SQL Query Used:**
    ```sql
    SELECT field4 AS Product, SUM(CAST(field14 AS REAL)) AS Total_Revenue
           FROM orders 
           WHERE field4 != 'Product'
           GROUP BY field4
    ORDER BY Total_Revenue DESC;

### 3. Customer Purchasing Behavior by Payment Method
  - **Highest Cart Size:** Customers using Cash buy the most items per transaction, averaging 5.72 items per cart.
  - **Lowest Cart Size:** Online transactions recorded the lowest average cart size with 5.23 items.
  - **SQL Query Used:**
      ```sql
      SELECT field8 AS Payment_Method, AVG(CAST(field11 AS REAL)) AS Avg_Items
         FROM orders 
         WHERE field8 != 'PaymentMethod'
      GROUP BY field8;






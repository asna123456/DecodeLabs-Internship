# Project 3: SQL Data Analysis - DecodeLabs Internship

This folder contains my queries, database files, and learning outcomes for Milestone 3 (SQL Data Analysis) of the DecodeLabs Industrial Training Program.

## 📌 Project Overview
The objective was to query a relational database containing **1,201 transaction records** using SQLite to discover trends across product categories, revenues, and customer purchasing habits.

### Key Skills Demonstrated:
- **SQL Data Aggregation:** `COUNT()`, `SUM()`, `AVG()`
- **Relational Logic & Structuring:** `WHERE`, `GROUP BY`, `ORDER BY`
- **Data Wrangling & Type Casting:** Handling dirty CSV data structures, string-to-numeric data type transformation using `CAST()`.

---

## 🛠️ Tech Stack Used
- **Database Engine:** SQLite (DB Browser for SQLite)
- **Source Format:** CSV UTF-8 (Converted from raw Excel dataset)

---

## 📈 Key Insights Discovered

### 1. Grand Total Volume & Sales Revenue
- **Total Orders Processed:** 1,201 orders
- **Grand Total Revenue:** 1,264,761.96
- **SQL Query Used:**
```sql
SELECT COUNT(*) AS Total_Orders, 
       SUM(CAST(field14 AS REAL)) AS Total_Sales 
FROM orders 
WHERE field14 != 'TotalPrice';

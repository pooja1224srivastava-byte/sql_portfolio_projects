# 🛍️ Sales Data Analysis – SQL Portfolio Project

## 📘 Project Overview
This project analyzes a **real-world sales dataset** using SQL to uncover important business insights such as:
- Which countries generate the most revenue  
- Which products and customers contribute the most  
- Monthly sales trends and cancellations  

💡 *Objective:* To demonstrate SQL skills in data cleaning, transformation, and business analysis for a data analyst portfolio project.  

---

## 🧰 Tools Used
- **MySQL Workbench** – For running SQL queries  
- **Excel / Power BI (optional)** – For creating visuals  
- **VS Code** – For organizing SQL scripts and documentation  
- **GitHub** – For showcasing the project  

---

## 📂 Folder Structure

sql_portfolio_projects/
│
├── Data/
│ └── sales_data_sample.csv
│
├── sql/
│ ├── create_table.sql
│ ├── data_cleaning.sql
│ └── analysis_queries.sql
│
├── results/
│ ├── avg_order_value_by_dealsize
│ ├──cancelation_rate_by_product
│ ├── country_sales
│ ├── productline_by_revenue
│ ├── top_product_by_country
│ 
│
└── README.md



---

## 🧹 Data Cleaning Steps
Script: [`data_cleaning.sql`](./sql/data_cleaning.sql)

1. **Converted `ORDERDATE`** to proper date format using `STR_TO_DATE()`
2. **Created new columns:**
   - `order_value` → computed if `SALES` missing  
   - `order_year`, `order_month`, `order_ym` for trend analysis
3. **Verified data consistency** between `SALES` and computed order value  
4. **Removed unwanted characters** (like `$` or `,`) from numeric columns  

✅ *Result:* Dataset cleaned, ready for analysis.  

---

## 📊 Analysis & Insights
Script: [`analysis_queries.sql`](./sql/analysis_queries.sql)

### 1️⃣ Total Sales by Country
```sql
SELECT COUNTRY, ROUND(SUM(SALES), 2) AS total_sales
FROM sales_data_sample
GROUP BY COUNTRY
ORDER BY total_sales DESC;

Insight:
🇺🇸 USA generated the highest revenue, followed by Spain and France.

SELECT PRODUCTLINE, SUM(SALES) AS revenue
FROM sales_data_sample
GROUP BY PRODUCTLINE
ORDER BY revenue DESC
LIMIT 10;

Insight:
🚗 Classic Cars and Vintage Cars contribute the most — strong demand for collectible products.

💡 Key Learnings

-- Practiced real-world SQL data cleaning & analysis

-- Learned window functions, aggregation, CASE, COALESCE, and date handling

-- Understood how to translate SQL results into business insights

-- Organized project structure for GitHub portfolio
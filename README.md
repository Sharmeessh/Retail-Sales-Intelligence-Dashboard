# 🛍️ Retail Sales Intelligence Dashboard

End-to-end Data Analytics project analyzing 50K+ retail transactions using **Snowflake, SQL & Power BI** to uncover sales, profit, discount and customer insights.

**Author:** Sharmila K | MCA, Bharathiar University | Process Associate @ AGS Health
**Tools:** Snowflake, SQL, Power BI, Excel

---

## 📊 Dashboard Preview

| Overview | Product Intelligence |
|---|---|
| ![Overview](screenshots/overview.png) | ![Product](screenshots/product.png) |

| Customer Intelligence | Discount Analysis |
|---|---|
| ![Customer](screenshots/customer.png) | ![Discount](screenshots/discount.png) |

---

## 🎯 Business Problem

A retail company was losing profit due to high discounts and had no clarity on:
- Which products / regions are actually profitable?
- Which customers drive revenue?
- How does discount affect profit?

**Goal:** Build an intelligence dashboard in Power BI on top of Snowflake to help management take data-driven decisions.

## 🔑 Key KPIs

| KPI | Value |
|---|---|
| Total Revenue | $2.3M+ |
| Total Profit | $280K+ |
| Profit Margin % | 12.4% |
| Total Orders | 50K+ |
| Avg Order Value | $45.8 |
| Total Customers | 7,900+ |
| Return Rate | 8.2% |

## 📈 Key Insights

1.  **15% of products generate 60% of revenue** - Pareto principle applies.
2.  **Discount > 20% reduces profit by 32%** - High discount = Loss in Furniture category.
3.  **South Region is top performer** with 35% of total revenue.
4.  **Repeat customers (20%) contribute 65% of revenue** - Retention is key.
5.  **Furniture has highest sales but lowest profit margin** due to heavy discounting.

## 🛠️ Tech Stack & Steps

### 1. Snowflake - Data Warehouse & Upload

**Step 1: Create Warehouse, Database & Table**
```sql
CREATE WAREHOUSE RETAIL_WH WITH WAREHOUSE_SIZE = 'XSMALL' AUTO_SUSPEND = 60;
CREATE DATABASE RETAIL_DB;
CREATE SCHEMA RETAIL_DB.PUBLIC;

CREATE TABLE RETAIL_DB.PUBLIC.RETAIL_SALES (
    Order_ID VARCHAR,
    Order_Date DATE,
    Customer_Name VARCHAR,
    Product_Name VARCHAR,
    Category VARCHAR,
    Region VARCHAR,
    Sales FLOAT,
    Quantity INT,
    Discount FLOAT,
    Profit FLOAT
);

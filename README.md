# SQL-integration-with-Python

## 📌 Objective
Analyze **monthly revenue** and **order volume** using SQL queries to identify sales trends over time.

---

## 🧰 Tools Used
- **SQLite** (for executing SQL queries)
- **Python (sqlite3)** – to connect and interact with the database
- **GitHub** – for version control and task submission

---

## 📂 Dataset Description
The database includes a table named `orders` with the following relevant fields:

- `order_date` – Date when the order was placed
- `Total_Price` – Revenue from the order
- `Order_ID` – Unique ID for each order
- `Product_ID` – ID of the purchased product

---

## 🔍 Analysis Performed

### 1. 📅 Monthly Revenue and Order Volume
```sql
SELECT 
  strftime('%Y', order_date) AS year,
  strftime('%m', order_date) AS month,
  SUM(amount) AS total_revenue,
  COUNT(DISTINCT order_id) AS order_volume
FROM online_sales
GROUP BY year, month
ORDER BY year, month;

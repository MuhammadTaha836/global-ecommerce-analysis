 Project: Global E-Commerce Sales Analysis 2025
 Author: Muhammad Taha
 Tool: SQLiteOnline
 Dataset: Kaggle - Global E-Commerce Sales Dataset 2025
 Date: April 2026

 Query 1: Revenue by Country + Percentage Share
SELECT 
    country,
    ROUND(SUM(total_amount), 2) AS total_revenue,
    COUNT(*) AS total_orders,
    ROUND(SUM(total_amount) * 100.0 / 
        (SELECT SUM(total_amount) FROM global_ecommerce_sales), 2) 
        AS revenue_share_pct
FROM global_ecommerce_sales
WHERE country IS NOT NULL
AND total_amount IS NOT NULL
GROUP BY country
ORDER BY total_revenue DESC
LIMIT 10;

 Query 2: Category Sales Volume and Revenue
SELECT 
    category,
    COUNT(*) AS total_orders,
    SUM(quantity) AS total_units_sold,
    ROUND(SUM(total_amount), 2) AS total_revenue,
    ROUND(AVG(total_amount), 2) AS avg_order_value
FROM global_ecommerce_sales
WHERE category IS NOT NULL
AND total_amount IS NOT NULL
GROUP BY category
ORDER BY total_revenue DESC;

 Query 3: Average Order Value by Country and Category
SELECT 
    country,
    category,
    COUNT(*) AS total_orders,
    ROUND(AVG(total_amount), 2) AS avg_order_value,
    ROUND(SUM(total_amount), 2) AS total_revenue
FROM global_ecommerce_sales
WHERE country IS NOT NULL
AND category IS NOT NULL
AND total_amount IS NOT NULL
GROUP BY country, category
ORDER BY avg_order_value DESC
LIMIT 15;

 Query 4: Monthly Sales Trends and Seasonality
SELECT 
    SUBSTR(order_date, -4) AS year,
    SUBSTR(order_date, 1, INSTR(order_date, '/') - 1) AS month,
    COUNT(*) AS total_orders,
    ROUND(SUM(total_amount), 2) AS total_revenue
FROM global_ecommerce_sales
WHERE order_date IS NOT NULL
AND total_amount IS NOT NULL
GROUP BY year, month
ORDER BY year ASC, CAST(month AS INTEGER) ASC;

 Query 5: Top Country and Category Combinations by Revenue
SELECT 
    country,
    category,
    ROUND(SUM(total_amount), 2) AS total_revenue,
    COUNT(*) AS total_orders,
    ROUND(AVG(total_amount), 2) AS avg_order_value
FROM global_ecommerce_sales
WHERE country IS NOT NULL
AND category IS NOT NULL
AND total_amount IS NOT NULL
GROUP BY country, category
ORDER BY total_revenue DESC
LIMIT 10;

 Query 6: Quantity vs Revenue Correlation by Country
SELECT 
    country,
    SUM(quantity) AS total_units_sold,
    ROUND(SUM(total_amount), 2) AS total_revenue,
    ROUND(AVG(quantity), 1) AS avg_units_per_order,
    ROUND(AVG(total_amount), 2) AS avg_order_value
FROM global_ecommerce_sales
WHERE country IS NOT NULL
AND quantity IS NOT NULL
AND total_amount IS NOT NULL
GROUP BY country
ORDER BY total_units_sold DESC;

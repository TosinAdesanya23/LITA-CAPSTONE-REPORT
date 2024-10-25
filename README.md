# Salesdata

---
##MY SQL QUERIES
```
SELECT category_name, SUM(quantity * price) AS total_sales
FROM sales
GROUP BY category_name;
```

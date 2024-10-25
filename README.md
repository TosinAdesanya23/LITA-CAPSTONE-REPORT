# Salesdata

---
##MY SQL QUERIES
###Total sales for each product category:
```
SELECT product, SUM(quantity * unitprice) AS total_sales
FROM salesdata
GROUP BY product;
```

###Number of sales transactions in each region:
```
SELECT region, COUNT(orderID) AS transaction_count
FROM salesdata
GROUP BY region;
```

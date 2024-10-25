# Salesdata

---
## MY SQL QUERIES
### Total sales for each product category:
```
SELECT product, SUM(quantity * unitprice) AS total_sales
FROM salesdata
GROUP BY product;
```

### Number of sales transactions in each region:
```
SELECT region, COUNT(orderID) AS transaction_count
FROM salesdata
GROUP BY region;
```
### Highest-selling product by total sales value:

```
SELECT product, SUM(quantity * unitprice) AS total_sales
FROM salesdata
GROUP BY product
ORDER BY total_sales DESC
LIMIT 1;
```
THE ANSWER IS SHOES!!

### Total Revenue per product
```
SELECT product, SUM(quantity * unitprice) AS total_revenue
FROM salesdata
GROUP BY product;
```
### Monthly sales total for the current year

### Top 5 customers by total purchase amount
```
SELECT customerID, SUM(quantity * unitprice) AS total_purchase
FROM salesdata
GROUP BY customerID
ORDER BY total_purchase DESC
LIMIT 5;
```
### Percentage of total sales contributed by each region:
```
SELECT region, 
       SUM(quantity * unitprice) / (SELECT SUM(quantity * unitprice) FROM salesdata) * 100 AS percentage_sales
FROM salesdata
GROUP BY region;
```




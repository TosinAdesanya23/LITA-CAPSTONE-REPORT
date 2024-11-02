# LITA CAPSTONE  Salesdata REPORT

### DESCRIPTION.

#### THE DATASET CONTAINS RECORDS ON CAPSTONE SALES PERFORMANCE BY REGION, QUANTITY SOLD, UNIT COST, ORDERDATE AND PRODUCTS SOLD BETWEEN 2023-2024.

### PROJECT OVERVIEW

This data Analysis project aims to give insights on the sales performance of the CAPSTONE DATASET AND THE SUBSCRIPTION DATASET project for a period of two years (2023-2004) . This analysis will help to make  data-driven decisions for  growth strategies.

### SUMMARY
This is an exploration of the CAPSTONE sales dataset to uncover key insights such as top-selling products, motnly sales data and regional performance.

### GOAL
The goal is to produce an interactive and understandable analysis for an informed growth strategy for the Capstone and Package subscription company.

### DATA SOURCES
The primary source of Data used here is an Excel data file, CSV file.

### TECHNOLGY USED
- Excel sheet 
- excel SUM and AVERAGE functions 
- Excel pivot table 
- SQL SERVER (My SQL) 
- POWER BI

### TOOLS USED
- Microsoft Excel [(Download here)](https://1drv.ms/x/c/45b106d15656cf28/EYXe7GV0cORIk3pJQxx0qfMBAgHEFp4YsnYEL4UoBZUCyA?e=hcSmcq)
- Data cleaning
- Data Visualization
- Calcutions
- Analysis
- SQL- (structured query language) for data querrying
- Github- for porfolio Building


### SKILLS 
1. Data Cleaning
2. Data EXPLORATION
3. Data Analysis
4. Data Visualisation

### DATA CLEANING AND PREPARATION
On the initial phase of Data cleaning and preparations, I performed the following action;
Data loading and inspection
Handling missing variables
Data cleaning and formatting

### EXPLORATORY DATA ANALYSIS
EDA involved the exploration of the data to answer some questions about the Data such as:
 -  Total Sales for each product category and What product is the highest selling?
 -  what is the overall sales trend?
 -  number of sales transaction in each region, and what region has the highest sales?
 -  percentage of total sales by region?

### DATA ANALYSIS AND VISUALISATION - MS EXCEL 
![image](https://github.com/user-attachments/assets/bea8e389-16a7-4105-b4d9-73a3a9c8d689)
![image](https://github.com/user-attachments/assets/ba19c4bb-0ce3-4d36-aea3-c6b2dc543ab9)

![image](https://github.com/user-attachments/assets/53e6be32-66bd-4a32-aa38-cd52af0747f9)

![image](https://github.com/user-attachments/assets/44c4da60-e0a9-4fac-8d9f-fba18bf7ceb7)

![image](https://github.com/user-attachments/assets/d001e637-58a4-4d7a-82a2-3ce2554f5435)


Sum of Total Monthly sales year 2023 

![image](https://github.com/user-attachments/assets/3f4f1dac-c332-4783-9156-cc2610c4899c)
![image](https://github.com/user-attachments/assets/8b4e4419-aee3-40b1-9322-f929ec88951d)


### DATA ANALYSIS- SQL
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
### Products with no sales in the last quarter
```
SELECT product
FROM salesdata
GROUP BY product
HAVING SUM(CASE WHEN orderdate >= DATE_SUB(CURDATE(), INTERVAL 3 MONTH) THEN 1 ELSE 0 END) = 0;

```


### DATA VISUALISATION- MICROSOFT POWER BI

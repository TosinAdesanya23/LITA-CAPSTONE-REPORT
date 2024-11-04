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

![new visual](https://github.com/user-attachments/assets/17e3063c-0d27-4251-9fc8-cd00f49a7120)

### Findings and Results

Summary:

Top Product: Shoes have emerged as the best-selling item.
Regional Performance: The South region leads in total sales performance.

### Recommendations
Targeted Marketing Campaigns:

- Optimize marketing expenditures by concentrating on high-revenue areas and promoting best-selling products.
- Develop region-specific promotions, such as offering discounts in lower-performing areas to encourage sales growth.

Product Strategy:
- Increase inventory levels and enhance visibility for high-demand products.
- Reassess pricing strategies for underperforming items to make them more appealing, or consider bundling them with popular products to drive sales.

Seasonal Promotions:

- Strategize targeted promotions and campaigns during identified peak sales months to maximize revenue opportunities.
- Proactively plan for traditionally low-sales months by introducing new promotions or product bundles to stimulate consumer interest.

Customer Retention Programs:

- Identify and focus on top customers by implementing loyalty programs or exclusive offers to enhance engagement and boost their lifetime value.

Pricing Adjustments:

- Assess potential pricing adjustments for certain products to optimize profit margins without adversely affecting sales volume.
- Introduce discounts or value packs for slower-moving items to accelerate their turnover rates.



# LITA-CAPSTONE---CUSTOMER-DATA--REPORT

LITA CAPSTONE Customer  REPORT
### DESCRIPTION.
#### THE DATASET CONTAINS RECORDS ON CAPSTONE SALES PERFORMANCE BY REGION, QUANTITY SOLD, UNIT COST, ORDERDATE AND PRODUCTS SOLD BETWEEN 2023-2024.

### PROJECT OVERVIEW

This data Analysis project aims to give insights on the sales performance of the CAPSTONE DATASET AND THE SUBSCRIPTION DATASET project for a period of two years (2023-2004) . This analysis will help to make data-driven decisions for growth strategies.

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
- Microsoft Excel [(Download here)] https://1drv.ms/x/c/45b106d15656cf28/EYXe7GV0cORIk3pJQxx0qfMBEP0vvfRZWVw60YwZD1uWkA?e=2UVmOq
- Data cleaning
- Data Visualization
- Calcutions
- Analysis
- SQL- (structured query language) for data querrying
- Github- for porfolio Building
  
### SKILLS
- Data Cleaning
- Data EXPLORATION
- Data Analysis
- Data Visualisation

### DATA CLEANING AND PREPARATION
On the initial phase of Data cleaning and preparations, I performed the following action; Data loading and inspection Handling missing variables Data cleaning and formatting

### EXPLORATORY DATA ANALYSIS
EDA involved the exploration of the data to answer some questions about the Data such as:

- to retrieve the total number of customers from each region.
- to find the most popular subscription type by the number of customers.
- to find customers who canceled their subscription within 6 months.
- to calculate the average subscription duration for all customers.
- to find customers with subscriptions longer than 12 months.
- to calculate total revenue by subscription type.
- to find the top 3 regions by subscription cancellations.
- to find the total number of active and canceled subscription
- 
### DATA ANALYSIS AND VISUALISATION - MS EXCEL
### DATA ANALYSIS - SQL
#### SQL QUERIES 
**Here are the revised SQL queries based on the single table structure:**

1. **Total number of customers from each region:**

   ```sql
   SELECT region, COUNT(*) AS total_customers
   FROM customers
   GROUP BY region;
   ```

2. **Most popular subscription type:**

   ```sql
   SELECT subscription_type, COUNT(*) AS total_customers
   FROM customers
   GROUP BY subscription_type
   ORDER BY total_customers DESC
   LIMIT 1;
   ```

3. **Customers who canceled within 6 months:**

   ```sql
   SELECT *
   FROM customers
   WHERE end_date IS NOT NULL
   AND end_date BETWEEN CURDATE() - INTERVAL 6 MONTH AND CURDATE();
   ```

4. **Average subscription duration:**

   ```sql
   SELECT AVG(DATEDIFF(end_date, start_date)) AS avg_duration
   FROM customers
   WHERE end_date IS NOT NULL;
   ```

5. **Customers with subscriptions longer than 12 months:**

   ```sql
   SELECT *
   FROM customers
   WHERE end_date IS NOT NULL
   AND DATEDIFF(end_date, start_date) > 365;
   ```

6. **Total revenue by subscription type:**

   ```sql
   SELECT subscription_type, SUM(revenue) AS total_revenue
   FROM customers
   GROUP BY subscription_type;
   ```

7. **Top 3 regions by subscription cancellations:**

   ```sql
   SELECT region, COUNT(*) AS total_cancellations
   FROM customers
   WHERE end_date IS NOT NULL
   GROUP BY region
   ORDER BY total_cancellations DESC
   LIMIT 3;
   ```

8. **Total active and canceled subscriptions:**

   ```sql
   SELECT
       SUM(CASE WHEN end_date IS NULL THEN 1 ELSE 0 END) AS active_subscriptions,
       SUM(CASE WHEN end_date IS NOT NULL THEN 1 ELSE 0 END) AS canceled_subscriptions
   FROM customers;
   ```

DATA VISUALISATION - POWER BI
![Customer data visualisation](https://github.com/user-attachments/assets/f5c31789-3946-457a-b343-8ffc3c74aaf5)


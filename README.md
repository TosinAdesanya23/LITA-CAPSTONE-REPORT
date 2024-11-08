# LITA CAPSTONE REPORT
## PROJECT 1

### DESCRIPTION.

#### THE DATASET CONTAINS RECORDS ON CAPSTONE SALES PERFORMANCE BY REGION, QUANTITY SOLD, UNIT COST, ORDERDATE AND PRODUCTS SOLD BETWEEN 2023-2024.

### PROJECT OVERVIEW

This data Analysis project aims to give insights on the sales performance of the CAPSTONE DATASET project for a period of two years (2023-2004) . This analysis will help to make  data-driven decisions for  growth strategies.

### SUMMARY
This is an exploration of the CAPSTONE sales dataset to uncover key insights such as top-selling products, motnly sales data and regional performance. The goal is to produce an interactive and understandable analysis for an informed growth strategy for the Capstone company.

### DATA SOURCES
The primary source of Data used here is an Excel data file, CSV file.

### TECHNOLGY USED
- Excel sheet [(Download here)](https://1drv.ms/x/c/45b106d15656cf28/EYXe7GV0cORIk3pJQxx0qfMBAgHEFp4YsnYEL4UoBZUCyA?e=hcSmcq)
- excel SUM and AVERAGE functions 
- Excel pivot table 
- SQL SERVER (My SQL) 
- POWER BI

### SKILLS 
1. Data Cleaning
2. Data EXPLORATION
3. Data Analysis
4. Data Visualisation
5. SQL- (structured query language) for data querrying
6. Data Analysis Expressions DAX
7. Microsoft Power BI
8. Github- for porfolio Building

### DATA CLEANING AND PREPARATION
On the initial phase of Data cleaning and preparations, I performed the following action;
Data loading and inspection
Handling missing variables
Data cleaning and formatting

### EXPLORATORY DATA ANALYSIS
EDA involved the exploration of the data to answer some questions about the Data such as:
 -  Overall sales trend
 -  Total Sales for each product category and product with highest sales
 -  Regional analysis, including region with highest sales and percentage of total sales by 
    region.

### DATA ANALYSIS AND VISUALISATION - MS EXCEL 

### Table 1: Best Selling Product
From the visuals below we can see the sales of shoes coming first place, above all other products.

![image](https://github.com/user-attachments/assets/bea8e389-16a7-4105-b4d9-73a3a9c8d689)
![image](https://github.com/user-attachments/assets/9395e029-2fd7-4a86-ae05-570e3c272565)




### Table 2: Regional Performance
South takes the lead with sales, this is a positivefeedbck. It also highlights areas that Capstone team will need to work on to bring about a national competitiveness.

![image](https://github.com/user-attachments/assets/44c4da60-e0a9-4fac-8d9f-fba18bf7ceb7)
![image](https://github.com/user-attachments/assets/d001e637-58a4-4d7a-82a2-3ce2554f5435)

#### Table 3: Sum of Total Monthly sales year 2023
From the graph below  we need to analyze the reasons behind the significant drop in sales from March onwards and then a spike again in July. It could be a seasonal issue, demand forecasting error, or other factors.

![image](https://github.com/user-attachments/assets/8b4e4419-aee3-40b1-9322-f929ec88951d)
![image](https://github.com/user-attachments/assets/3f4f1dac-c332-4783-9156-cc2610c4899c) 

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

![WhatsApp Image 2024-11-05 at 23 35 31_f28c6fb0](https://github.com/user-attachments/assets/b4a1e51c-69fb-4692-8b0f-844e43b23819)


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



# PROJECT 2 - LITA-CAPSTONE---CUSTOMER-DATA--REPORT

### DESCRIPTION.
#### THE DATASET CONTAINS RECORDS ON PACKAGE SUBSCRIPTION COMPANY PERFORMANCE BY CUSTOMER BEHAVIOR EXPERIENCE, RETENTION REGIONAL PERFORMANCE AND PRODUCT SUMMARY.

### PROJECT OVERVIEW

This data Analysis project aims to give insights on the customer and product performance of SUBSCRIPTION DATASET. This analysis will help to make data-driven decisions for growth strategies.

### TOOLS USED
- Microsoft Excel [(Download here)] https://1drv.ms/x/c/45b106d15656cf28/EYXe7GV0cORIk3pJQxx0qfMBEP0vvfRZWVw60YwZD1uWkA?e=2UVmOq

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
   FROM customerdata
   GROUP BY region;
   ```

2. **Most popular subscription type:**

   ```sql
   SELECT subscriptiontype, COUNT(*) AS total_customers
   FROM customerdata
   GROUP BY subscriptiontype
   ORDER BY total_customers DESC
   LIMIT 1;
   ```

3. **Customers who canceled within 6 months:**

   ```sql
    SELECT *
   FROM customerdata
   WHERE subscriptionend IS NOT NULL
   AND subscriptionend BETWEEN CURDATE() - INTERVAL 6 MONTH AND CURDATE()

   ```

4. **Average subscription duration:**

   ```sql
   SELECT AVG(DATEDIFF(subscriptionend, subscriptionstart)) AS avg_duration
   FROM customerdata
   WHERE SubscriptionEnd IS NOT NULL;

   ```

5. **Customers with subscriptions longer than 12 months:**

   ```sql
   SELECT *
   FROM customerdata
   WHERE subscriptionend IS NOT NULL
   AND DATEDIFF(subscriptionend, subscriptionstart) > 365;
   ```

6. **Total revenue by subscription type:**

   ```sql
   SELECT subscriptiontype, SUM(revenue) AS total_revenue
   FROM customerdata
   GROUP BY subscriptiontype;
   ```

7. **Top 3 regions by subscription cancellations:**

   ```sql
   SELECT region, COUNT(*) AS total_cancellations
   FROM customerdata
   WHERE subscriptionend IS NOT NULL
   GROUP BY region
   ORDER BY total_cancellations DESC
   LIMIT 3;
   ```

8. **Total active and canceled subscriptions:**

   ```sql
   SELECT
       SUM(CASE WHEN subscriptionend IS NULL THEN 1 ELSE 0 END) AS active_subscriptions,
       SUM(CASE WHEN subscriptionend IS NOT NULL THEN 1 ELSE 0 END) AS canceled_subscriptions
   FROM customerdata;
   ```

### DATA VISUALISATION - POWER BI
![image](https://github.com/user-attachments/assets/baaf4ef3-91fa-4b4a-b378-a25e5066c793)


#### RECOMMENDATIONS
Customer Preference Analysis: 
- The popularity of Basic subscriptions suggests a preference for lower-cost options. Analyzing feedback on Premium and Standard plans could help make higher-tier plans more appealing.
  
Enhanced Cancellation Insights:
- Detailed cancellation data can be used for targeted outreach. Identifying groups with high cancellation rates allows for tailored campaigns to address specific needs.
  
## CONCLUSION 
The insights derived from these analyses empower us to significantly improve sales performance and optimize subscription services.


# Walmart Sales Data Analysis

## About
This project delves into Walmart sales data to uncover insights into top-performing branches, popular products, sales trends, and customer behavior. The dataset originates from the Kaggle Walmart Sales Forecasting Competition, encompassing transactions from three branches.

## Objectives
The primary objective is to analyze Walmart's sales data to enhance sales strategies and operational efficiencies across different branches.

## Dataset Overview
The dataset comprises 17 columns and 1000 rows, including information such as invoice details, branch locations, customer demographics, product details, transaction specifics, and financial metrics.

### Column Description
- **invoice_id:** Invoice identifier for sales transactions.
- **branch:** Walmart branch where the sales were conducted.
- **city:** Location of the branch.
- **customer_type:** Type of customer making the purchase.
- **gender:** Gender of the customer.
- **product_line:** Category of the product sold.
- **unit_price:** Price per unit of the product.
- **quantity:** Quantity of the product sold.
- **VAT:** Value Added Tax on the purchase.
- **total:** Total cost of the purchase.
- **date:** Date of the transaction.
- **time:** Time of the transaction.
- **payment_method:** Method of payment used.
- **cogs:** Cost of Goods Sold.
- **gross_margin_percentage:** Gross margin percentage.
- **gross_income:** Gross income generated from the sales.
- **rating:** Customer rating of the product or service.

## Analysis Goals
### Product Analysis
Explore product lines to identify top-performing categories and opportunities for improvement.

### Sales Analysis
Examine sales trends across different products to evaluate the effectiveness of sales strategies.

### Customer Analysis
Segment customers based on purchasing behavior and demographics to optimize marketing efforts.

## Methodology
### Data Wrangling
Initial data inspection to handle missing values and ensure data quality.

### Database Setup
Creation of a dedicated database and tables to store and analyze the Walmart sales data.

### Feature Engineering
Creation of new columns such as 'time_of_day' to analyze sales patterns during different parts of the day, 'day_name' to assess weekly sales trends, and 'month_name' to identify seasonal variations in sales.

### Exploratory Data Analysis (EDA)
In-depth analysis to answer key business questions and derive actionable insights.

## Conclusion
**This project provides a comprehensive analysis of Walmart's sales data, offering insights into product performance, sales trends, and customer behavior. By leveraging this analysis, Walmart can optimize sales strategies and enhance overall business performance.**

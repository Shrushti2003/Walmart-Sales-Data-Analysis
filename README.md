# Walmart Sales Data Analysis

## About
This project seeks to analyze Walmart's sales data to identify top-performing branches and products, understand sales trends across different product categories, and evaluate customer behavior. The ultimate goal is to enhance and optimize sales strategies. The dataset used was sourced from the Kaggle Walmart Sales Forecasting Competition.

"In this recruiting competition, participants are provided with historical sales data for 45 Walmart stores across various regions. Each store has numerous departments, and competitors must forecast sales for each department in each store. To add complexity, the dataset includes selected holiday markdown events, which are known to impact sales. Predicting which departments are affected and to what extent is part of the challenge." - source

## Project Goals
The primary aim of this project is to derive insights from Walmart's sales data to understand the various factors influencing sales performance across different branches.

## Dataset Details
The dataset was acquired from the Kaggle Walmart Sales Forecasting Competition. It contains sales records from three Walmart branches located in Mandalay, Yangon, and Naypyitaw. The dataset includes 17 columns and 1000 rows:

### Column Descriptions
- **invoice_id:** Unique identifier for the sales invoice (VARCHAR(30))
- **branch:** Branch where the sale occurred (VARCHAR(5))
- **city:** Location of the branch (VARCHAR(30))
- **customer_type:** Type of customer making the purchase (VARCHAR(30))
- **gender:** Gender of the customer (VARCHAR(10))
- **product_line:** Category of the product sold (VARCHAR(100))
- **unit_price:** Price per unit of the product (DECIMAL(10, 2))
- **quantity:** Quantity of products sold (INT)
- **VAT:** Value Added Tax on the purchase (FLOAT(6, 4))
- **total:** Total cost of the purchase (DECIMAL(10, 2))
- **date:** Date of the transaction (DATE)
- **time:** Time of the transaction (TIMESTAMP)
- **payment_method:** Payment method used (DECIMAL(10, 2))
- **cogs:** Cost of Goods Sold (DECIMAL(10, 2))
- **gross_margin_percentage:** Gross margin percentage (FLOAT(11, 9))
- **gross_income:** Gross income from the sale (DECIMAL(10, 2))
- **rating:** Customer rating (FLOAT(2, 1))

## Analysis Focus
### Product Analysis
Analyze data to understand performance across various product lines, identifying high-performing categories and areas needing improvement.

### Sales Analysis
Investigate sales trends across different products to assess the effectiveness of current sales strategies and identify opportunities for enhancement.

### Customer Analysis
Explore customer segments, purchasing patterns, and profitability to better tailor marketing efforts and improve customer engagement.

## Methodology
### Data Wrangling
Initial data inspection to detect and handle NULL values and missing data, ensuring data quality for analysis.

### Database Creation
Set up a database and tables to store and manage the Walmart sales data.

### Feature Engineering
Generate new columns to provide additional insights:
- **time_of_day:** Classifies transactions into Morning, Afternoon, and Evening, helping to identify peak sales periods.
- **day_name:** Extracts day of the week from transaction dates (e.g., Mon, Tue), identifying the busiest days.
- **month_name:** Extracts month from transaction dates (e.g., Jan, Feb), determining seasonal sales trends.

### Exploratory Data Analysis (EDA)
Conduct in-depth analysis to answer key business questions and derive actionable insights.

## Conclusion
**This project delivers a detailed analysis of Walmart's sales data, offering valuable insights into product performance, sales trends, and customer behavior. The findings can help Walmart optimize its sales strategies and improve overall business efficiency.**

## Business Questions to Address
### General Questions
- How many unique cities are represented in the dataset?
- Which city is each branch located in?

### Product-Specific Questions
- How many unique product lines are there?
- What is the most common payment method?
- Which product line is the best seller?
- What is the total monthly revenue?
- Which month had the highest COGS?
- Which product line generated the highest revenue?
- Which city had the highest revenue?
- Which product line had the highest VAT?
- Add a "Good" or "Bad" label to product lines based on average sales.
- Which branch sold more products than the average?
- What is the most common product line by gender?
- What is the average rating for each product line?

### Sales Questions
- Number of sales per time of day across weekdays.
- Which customer type generates the most revenue?
- Which city has the highest VAT percentage?
- Which customer type pays the most VAT?

### Customer Questions
- How many unique customer types exist?
- How many unique payment methods are used?
- What is the most common customer type?
- Which customer type purchases the most?
- What is the gender distribution of customers?
- Gender distribution per branch.
- Time of day with the highest customer ratings.
- Time of day with the highest ratings per branch.
- Which day of the week has the highest average ratings?
- Which day has the highest average ratings per branch?

## Revenue and Profit Calculations
### Formulas
- **COGS:** \( \text{COGS} = \text{unit_price} \times \text{quantity} \)
- **VAT:** \( \text{VAT} = 5\% \times \text{COGS} \)
- **Total:** \( \text{total} = \text{VAT} + \text{COGS} \)
- **Gross Profit:** \( \text{gross_profit} = \text{total} - \text{COGS} \)
- **Gross Margin:** \( \text{gross_margin} = \frac{\text{gross_income}}{\text{total}} \)

### Example Calculation
For the first row in the database:
- **Unit Price:** 45.79
- **Quantity:** 7
- **COGS:** \( 45.79 \times 7 = 320.53 \)
- **VAT:** \( 5\% \times 320.53 = 16.0265 \)
- **Total:** \( 320.53 + 16.0265 = 336.5565 \)
- **Gross Margin Percentage:** \( \frac{16.0265}{336.5565} \approx 4.76\% \)

## Code
For the complete SQL code, refer to the [Walmart SQL Project](./Walmart%20sql%20Project.sql).

### Example SQL Statements
```sql
-- Create database
CREATE DATABASE IF NOT EXISTS walmartSales;

-- Create table
CREATE TABLE IF NOT EXISTS sales(
	invoice_id VARCHAR(30) NOT NULL PRIMARY KEY,
    branch VARCHAR(5) NOT NULL,
    city VARCHAR(30) NOT NULL,
    customer_type VARCHAR(30) NOT NULL,
    gender VARCHAR(30) NOT NULL,
    product_line VARCHAR(100) NOT NULL,
    unit_price DECIMAL(10,2) NOT NULL,
    quantity INT NOT NULL,
    tax_pct FLOAT(6,4) NOT NULL,
    total DECIMAL(12, 4) NOT NULL,
    date DATETIME NOT NULL,
    time TIME NOT NULL,
    payment VARCHAR(15) NOT NULL,
    cogs DECIMAL(10,2) NOT NULL,
    gross_margin_pct FLOAT(11,9),
    gross_income DECIMAL(12, 4),
    rating FLOAT(2, 1)
);

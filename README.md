# Sales Insights in Data Analytics

## Project Overview

The aim is to provide valuable insights into sales data using data analytics techniques. By analyzing historical sales data, we can uncover trends, patterns, and actionable insights to drive business decisions and improve sales performance.

## Features

- Data Cleaning and Preprocessing
- Sales Trend Analysis
- Sales Forecasting
- Customer Segmentation
- Visualizations and Dashboards

## Dataset

The dataset used for this project includes historical sales data, which contains information such as:

- Date
- Product Code
- Market Name
- Sales Quantity
- Sales Revenue
- Customer Name
- Region

## Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/Rahulchafle/sales-insights-data-analytics.git
    cd sales-insights-data-analytics
    ```


### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`


















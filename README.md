# Superstore Sales Analysis
Superstore Sales Analysis – Power BI End-to-End Project

## Project Overview

This is an end-to-end Power BI project built using the Superstore dataset. The objective of this project is to analyze business performance by tracking key metrics such as Sales, Profit, and Returned Orders, and comparing sales performance with the previous year. The dashboard provides insights into profitable products, loss-making products, Sales performance over time, and customer segments.

## Business Questions Solved

This dashboard answers the following business questions:

1. What are the total Sales, Profit, and % of Returned Orders? Show % change vs Previous Year (PY).
2. Compare Sales performance versus the previous year over time.
3. Determine the most profitable product and the most loss-making product.
4. Analyze Sales by Customer Segment.

## Dataset

https://www.kaggle.com/datasets/bitricks/superstore-dataset

## Tools & Technologies Used

- Power BI
- Power Query (Data Cleaning & Transformation)
- DAX (Data Analysis Expressions)
- Data Modeling
- Data Visualization

## DAX Measures Created

Some important DAX measures used in the project:

- Sales = SUM(Orders[Sales])

- Profit = sum(Orders[Profit])

- % Returned Orders = 
VAR _total_orders = DISTINCTCOUNT(Orders[Order ID])
VAR _returned_orders = DISTINCTCOUNT(Returns[Order ID])
VAR _perc = DIVIDE( _returned_orders, _total_orders)
RETURN 
_perc

- Sales PY = CALCULATE([Sales], SAMEPERIODLASTYEAR('Date Table'[Date]))

- Profit PY = CALCULATE([Profit], SAMEPERIODLASTYEAR('Date Table'[Date]))

- % Returned Orders PY = CALCULATE([% Returned Orders], SAMEPERIODLASTYEAR('Date Table'[Date]))

- vs PY - Sales = DIVIDE([Sales] - [Sales PY], [Sales PY])

- vs PY - Profit = DIVIDE([Profit] - [Profit PY], [Profit PY])

- vs PY - % returned orders = [% Returned Orders] - [% Returned Orders PY]

## Dashboard Features

The Power BI dashboard includes the following visuals:

- KPI Cards → Total Sales, Total Profit, Returned Orders %, YoY % Change
- Line Chart → Sales vs Previous Year Sales over time
- Bar Chart → Most Profitable and Loss-Making Products
- Donut/Bar Chart → Sales by Segment
- Slicers → Customer Name, Country/Region, Segment, Date

## Key Insights

- Identified the most profitable product and the product causing the most loss.
- Compared current year sales with previous year sales to track growth.
- Analyzed returned orders percentage and its impact on profit.
- Identified which customer segment contributes the most to sales.

## How to run the Project

- Download the Power BI file (.pbix).
- Open the file in Power BI Desktop.
- Refresh the data if required.
- Use slicers and filters to interact with the dashboard.

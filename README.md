# Sales & Customer Segmentation Dashboard

## Overview

An interactive Power BI dashboard analyzing sales performance, product profitability, and customer segmentation using the Superstore dataset. This project demonstrates the ability to identify revenue drivers, unprofitable products, and high-value customer segments.

## Business Problem

Sales managers need visibility into which products, regions, and customer segments drive revenue and profit. Without this analysis, companies risk investing in unprofitable product lines and overlooking their most valuable customers.

## Data Source

**Superstore Sales Dataset** from [Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- 4 years of sales data (2014-2017)
- 5,009 orders across 4 regions
- 17 product sub-categories
- 3 customer segments

## Key Features

### Page 1: Sales Overview
- KPI cards (Revenue, Profit, Orders, Profit Margin)
- Revenue breakdown by Region and Category
- Revenue trend over time (2014-2017)
- Profit by Sub-Category with conditional formatting (green = profitable, red = loss)
- Interactive filters for Region and Category

### Page 2: Customer Segmentation Analysis
- Revenue distribution by Customer Segment (donut chart)
- Profit Margin comparison by Segment
- Top Customers table with revenue, profit, and order count
- Scatter plot showing Revenue vs Profit by Customer
- Interactive filters for Region and Category

## Key Insights

1. **Unprofitable Product Identified**: Tables sub-category loses $17,730 despite generating significant revenue—requires pricing or supplier cost review

2. **Top Customer is Unprofitable**: Sean Miller (#1 by revenue at $25K) actually loses the company $1,981—suggests excessive discounting or high return rates

3. **Segment Profitability Mismatch**: Consumer segment drives 50.56% of revenue, but Home Office has the highest profit margin—opportunity to optimize Consumer pricing

4. **Regional Performance**: West region leads revenue, followed by East, Central, and South

5. **Strong Growth Trend**: Revenue grew approximately 50% from 2015 ($470K) to 2017 ($733K)

6. **Category Leaders**: Technology leads revenue; Copiers is the most profitable sub-category ($55.6K profit)

## Technical Details

**Tools Used:**
- Microsoft Power BI Desktop
- Power Query (data cleaning & transformation)
- DAX (Data Analysis Expressions)

**Data Model:**
- Single fact table with 16 fields
- Date hierarchy for time-based analysis

**DAX Measures Created:**
```dax
Total Revenue = SUM(Sales[Sales])

Total Profit = SUM(Sales[Profit])

Total Orders = DISTINCTCOUNT(Sales[Order ID])

Profit Margin = DIVIDE([Total Profit], [Total Revenue], 0)

Total Quantity = SUM(Sales[Quantity])

Avg Order Value = DIVIDE([Total Revenue], [Total Orders], 0)
```

## Business Recommendations

Based on this analysis, I would recommend:

1. **Investigate Tables pricing** — Either increase prices, negotiate better supplier costs, or consider discontinuing

2. **Review Sean Miller's account** — Analyze discount levels and return history; implement discount caps if needed

3. **Expand Home Office segment** — Highest margin segment deserves more marketing investment

4. **Replicate West region success** — Analyze what's working in the West and apply to underperforming South region

## How to Use

1. Download the `.pbix` file
2. Open with Power BI Desktop (free from Microsoft)
3. Use Region and Category slicers to filter data
4. Click on any visual to cross-filter the dashboard
5. Hover over data points for detailed tooltips

## Future Enhancements

- Add RFM (Recency, Frequency, Monetary) customer segmentation
- Build cohort analysis for customer retention
- Create forecasting model for future sales
- Add drill-through pages for product-level detail

## Author

**David Chirino**  
Data Analyst | Tampa, FL  

# AdventureWorks Sales Analysis — Power BI Dashboard

## Overview
This project is an end-to-end Power BI dashboard built on the AdventureWorks Cycles dataset, a widely used retail sales dataset that simulates the operations of a global bicycle and accessories manufacturer. The goal of this project was to design a complete business intelligence solution — from importing raw data and building a proper data model, to writing DAX measures and designing an interactive, multi-page dashboard that tells a clear business story.

The dashboard covers sales performance, product profitability, customer behavior, and geographic distribution of orders, and is intended to demonstrate practical, job-ready Power BI skills including data modeling, DAX, and dashboard/report design.

## Problem Statement
AdventureWorks Cycles sells bikes, components, clothing, and accessories across multiple countries and needs a way to monitor its sales performance at a glance. Management wants answers to questions such as:

- What is the overall revenue, profit, order volume, and return rate of the business?
- Which product categories and individual products are driving the most orders, revenue, and returns?
- How is business performance distributed across continents and countries?
- Who are the top customers, and what do the demographics (age, gender, income, occupation) of the customer base look like?
- How are revenue, orders, and returns trending over time?

This dashboard was built to answer these questions through a single, interactive reporting tool rather than static spreadsheets.

## Dataset
The dataset used is the AdventureWorks sales sample dataset, provided as a set of related CSV files (dimension tables) along with a sales fact table modeled inside the Power BI file itself. In total, 7 tables were imported and connected through relationships to build a proper star-schema data model:

| Table | Description |
|---|---|
| Calendar | A standalone date table used for time intelligence calculations |
| Customers | Customer demographic details (name, birth date, gender, income, occupation, marital status, etc.) |
| Product_Categories | Top-level product categories (Bikes, Components, Clothing, Accessories) |
| Product_Subcategories | Product subcategories mapped to their parent category |
| Products | Product-level details including cost, price, color, size, and style |
| Returns | Product return records by date, territory, and quantity |
| Territories | Sales territory information including region, country, and continent |

Along with these, a **Sales** fact table (order-level transaction data) sits at the center of the model, connected to each of the dimension tables above through relationships in Power BI.

> Note: Customer and product data in this dataset is anonymized/simulated and used strictly for learning and portfolio purposes.

## Tools and Technologies
- **Power BI Desktop** — data modeling, DAX, and report/dashboard design
- **Power Query (M)** — data cleaning and transformation
- **DAX (Data Analysis Expressions)** — calculated columns, measures, and KPIs
- **Star Schema Data Modeling** — fact and dimension table relationships
- **CSV files** — source data format

## Methods
1. **Data Import & Cleaning:** Imported all 7 tables into Power BI using Power Query, checked data types, handled formatting issues (such as currency symbols in the AnnualIncome column), and removed inconsistencies.
2. **Data Modeling:** Built a star schema by connecting the Sales fact table to the Calendar, Customers, Products, Territories, and Returns tables through defined relationships. Product_Categories and Product_Subcategories were linked in a snowflake pattern to the Products table.
3. **DAX Calculations:** Created measures for Total Revenue, Total Profit, Total Cost, Total Orders, Return Rate, Monthly Revenue/Orders/Returns with month-over-month comparisons, and time-intelligence calculations using the Calendar table.
4. **Dashboard Design:** Designed four report pages (Executive Summary, Map View, Product Details, Customer Detail) with slicers, KPI cards, trend charts, and drill-through style navigation to allow users to explore the data from multiple angles.
5. **Interactivity:** Added slicers for Month and Continent, drill-through from the Top 10 Products table to a dedicated Product Details page, and cross-filtering across all visuals.

## Key Insights
- The business generated **$18.51M in total revenue** and **$7.86M in total profit** across **23K total orders**, with an overall **return rate of 2.14%**.
- **North America** is the leading market by orders (47.27%), followed by **Europe** (29.6%) and **Pacific** (23.13%).
- **Accessories** and **Clothing** have strong order volumes, but certain products such as the **Sport-100 Helmet (Blue/Red)** show noticeably higher return rates (over 3%) compared to other top-selling products.
- **Water Bottle – 30 oz.** is the top product by order volume, while **Mountain-200 Black, 46** is the top product by profit — highlighting the difference between high-volume, low-margin items and lower-volume, high-margin items.
- Revenue, profit, and orders all show a **steady upward trend from January 2016 through mid-2017**, indicating consistent business growth.
- Customer demographics are fairly balanced by gender, with the majority of customers falling into the **"Average" and "Low" income brackets** and the **Professional and Skilled Manual** occupation categories.

## Dashboard / Model / Output
The dashboard consists of four interactive pages:

1. **Executive Summary** — High-level KPIs (Revenue, Profit, Orders, Return Rate), orders by category and gender, a continent/country donut chart, top 10 products by orders and return rate, and monthly revenue/orders/returns trend cards.
   ![Executive Summary](images/01_executive_summary.png)

2. **Map View** — A geographic map showing order concentration by country and continent, filterable by continent and month.
   ![Map View](images/02_map_view.png)

3. **Product Details** — A drill-through page focused on a single product, showing weekly revenue trends, monthly revenue/orders/returns gauges, and a returns trend line with a forecast band.
   ![Product Details](images/03_product_details.png)

4. **Customer Details** — A customer-level view with a ranked customer table, orders by gender/income/occupation, an age distribution treemap, and orders & revenue trends by month.
   ![Customer Detail](images/04_customer_detail.png)

## How to Run this Project?
1. Clone or download this repository.
2. Make sure you have **Power BI Desktop** installed (free download from Microsoft).
3. Open the file `Adventure_Works_Sales_Dashboard.pbix` in Power BI Desktop.
4. If prompted to refresh data or update source file paths, point Power Query to the CSV files inside the `data/` folder.
5. Use the slicers (Month, Continent) on each page to explore the report interactively.
6. Right-click on any product in the Top 10 Products table on the Executive Summary page to drill through to the Product Details page.

## Results & Conclusion
This project demonstrates a complete Power BI workflow — from raw CSV data to a fully modeled, DAX-driven, multi-page interactive dashboard. It highlights the ability to design a clean star-schema data model, write meaningful business calculations, and present insights in a way that is easy for non-technical stakeholders to understand and act on. The dashboard successfully surfaces actionable insights around revenue growth, product profitability, return trends, and customer demographics.

## Future Work
- Add Year-over-Year and Year-to-Date comparison measures using more advanced time intelligence DAX.
- Incorporate a "What-If" parameter to simulate the impact of discount or return-rate changes on profit.
- Add a dedicated Returns Analysis page to investigate return reasons and high-return products in more depth.
- Publish the report to the Power BI Service and set up a scheduled data refresh.
- Add row-level security (RLS) to simulate territory-based access control for different regional managers.

## Author & Contact
**Ahtasham Ul Haq**
Data Analyst

- 📧 Email: ahtashamulhaq2006@gmail.com.com
- 💼 LinkedIn: www.linkedin.com/in/ahtasham-ul-haq-6647973a3


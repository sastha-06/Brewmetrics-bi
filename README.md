# Brewmetrics-bi
Business Intelligence mini project for BrewMetrics Coffee Co.

# BrewMetrics – Coffee Sales Performance Dashboard

## Project Overview

BrewMetrics is a Power BI sales analytics project for a coffee business. The project uses a star-schema data model to analyze sales performance across cities, products, dates, and store formats.

## Data Model

The model follows a star-schema structure.

### Fact Table

- **Fact_Sales** – contains the sales transactions, including sale ID, date, city, store format, category, item, quantity, unit price, and sales amount.

### Dimension Tables

- **Dim_Date** – provides date information used for time-based analysis.
- **Dim_City** – contains the city dimension used for geographic analysis.
- **Dim_Product** – contains product information such as category and item.

The dimension tables are related to the Fact_Sales table to support filtering and analysis.

## DAX Measures

The report includes three main DAX measures:

- **Total Sales** – calculates total sales amount.
- **Previous Month Sales** – calculates sales for the previous month.
- **MoM Sales Growth %** – calculates the percentage change in sales compared with the previous month.

## Dashboard Insights

1. **City performance:** Bengaluru has the highest sales among the four cities shown in the dashboard, followed by Chennai, Hyderabad, and Coimbatore.

2. **Monthly pattern:** Sales are substantially higher from April through June and show a sharp decline in July in the displayed period.

3. **Store-format performance:** The drill-down visual allows city sales to be examined by store format, including Drive-Thru, Flagship, and Kiosk. This makes it possible to compare store-format contributions within each city.

## Dashboard Features

The dashboard includes:

- Cold Brew seasonal sales pattern
- Sales performance by city
- Monthly sales trend by city
- City slicer
- Date filter
- City → Store Format drill-down

## Tools Used

- Power BI Desktop
- DAX
- Git
- GitHub
- GitHub Copilot
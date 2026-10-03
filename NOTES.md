# Copilot Notes

## DAX Measures Suggested by GitHub Copilot

GitHub Copilot was used to assist with creating DAX measures for the BrewMetrics Coffee Co. Power BI project.

### 1. Total Sales

Copilot suggested:

```DAX
Total Sales =
SUM ( Fact_Sales[sales_amount] )
```

This measure calculates the total sales amount from the Fact_Sales table.

### 2. Previous Month Sales

Copilot suggested:

```DAX
Previous Month Sales =
CALCULATE (
    [Total Sales],
    DATEADD ( Dim_Date[date], -1, MONTH )
)
```

This calculates sales for the previous month using the Dim_Date date column.

### 3. MoM Sales Growth %

Copilot suggested:

```DAX
MoM Sales Growth % =
DIVIDE (
    [Total Sales] - [Previous Month Sales],
    [Previous Month Sales]
)
```

This calculates the percentage change in sales compared with the previous month.

### 4. Running Total Sales

Copilot suggested:

```DAX
Running Total Sales =
CALCULATE (
    [Total Sales],
    FILTER (
        ALLSELECTED ( Dim_Date ),
        Dim_Date[date] <= MAX ( Dim_Date[date] )
    )
)
```

This measure calculates cumulative sales through the current date while respecting the selected date range and other report filters.

### 5. City Sales Rank

Copilot suggested:
```DAX
City Sales Rank =
RANKX (
    ALL ( Dim_City[city] ),
    [Total Sales],
    ,
    DESC,
    DENSE
)
```

This measure ranks cities according to Total Sales, with the highest-sales city receiving rank 1.
The measure was reviewed and tested in Power BI.
## Copilot Suggestion and Review

Copilot's initial response suggested that the date table should contain a complete and contiguous range of dates and have an active one-to-many relationship with Fact_Sales.

The suggested measures were reviewed and tested in Power BI. The measures were used in a table visual with Year and Month Name to check monthly sales and MoM growth.

The Month Name field was sorted using Month Number so that the months appear in chronological order instead of alphabetical order.

The MoM Sales Growth % measure was formatted as a percentage with two decimal places.

## Final Review

The DAX measures were checked in Power BI and all three measures are visible under Fact_Sales:

- Total Sales
- Previous Month Sales
- MoM Sales Growth %

The Copilot suggestions were reviewed before being used in the final Power BI model.

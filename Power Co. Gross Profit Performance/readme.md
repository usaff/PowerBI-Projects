

# Plant Co. Gross Profit Performance Dashboard

This dashboard provides in-depth insights into Plant Co.'s gross profit performance across various countries, product types, and time periods. The aim is to enhance decision-making by presenting dynamic and interactive visualizations.

By analyzing year-to-date (YTD) gross profit and comparing it to the prior year-to-date (PYTD), this dashboard helps stakeholders understand profitability trends and make informed business decisions.

---

## Inspiration and Motivation

This dashboard was created to provide actionable insights into Plant Co.'s profitability metrics. By segmenting performance by country, product type, and time period, decision-makers can optimize strategies to maximize gross profit.

With dynamic and interactive visuals, users can easily identify trends, understand drivers of profitability, and make data-driven decisions.

---

## Purpose of the Project

The primary purpose of this project is to:

- Analyze year-to-date (YTD) gross profit and compare it to the prior year-to-date (PYTD).
- Segment profitability by country, product type, and other dimensions.
- Provide dynamic titles and visuals reflecting selected filters.
- Support strategic decision-making through detailed profitability analysis.

---

## Data Source

The dataset used for this analysis is sourced from **Mo Chen YouTube Channel**, which provides sales and profitability data for Plant Co. across multiple dimensions such as country, product type, and time period.

---

## Project Workflow

### Step 1: Loading and Preparing the Data

- Imported the dataset into Power BI.
- Cleaned and transformed the data using Power Query, including:
  - Removing null values and duplicates.
  - Standardizing column names for consistency.
  - Converting data types for better DAX compatibility.

### Step 2: Data Modeling

- Established relationships in the Model View.
- Ensured accurate calculations by connecting dimensions (e.g., Country, Product) to the fact table containing sales and profit details.

### Step 3: Creating Measures Using DAX

- **Gross Profit Percentage (GP%)**:
  ```DAX
  GP% = DIVIDE([Gross Profit], [Sales])
  ```
- **PYTD Gross Profit**:
  ```DAX
  PYTD_GrossProfit = CALCULATE([Gross Profit], SAMEPERIODLASTYEAR(Dim_Date[Date]), Dim_Date[InPast] = TRUE)
  ```
- **PYTD Quantity and Sales**:
  ```DAX
  PYTD_Quantity = CALCULATE([Quantity], SAMEPERIODLASTYEAR(Dim_Date[Date]), Dim_Date[InPast] = TRUE)
  PYTD_Sales = CALCULATE([Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]), Dim_Date[InPast] = TRUE)
  ```

### Step 4: Dynamic Titles and Context Switching

- **Dynamic Titles**: Created to reflect selected filters, ensuring context-specific insights:
  - Column Chart Title:
    ```DAX
    SELECTEDVALUE(Slc_Values[Values]) & " YTD vs PYTD | Month"
    ```
  - Report Title:
    ```DAX
    "Plant Co. Performance " & SELECTEDVALUE(Slc_Values[Values]) & " Performance " & SELECTEDVALUE(Dim_Date[Date].[Year])
    ```
- **Switching Contexts for YTD and PYTD**:
  - Example:
    ```DAX
    S_YTD = SWITCH(Selected_Values, "Sales", [YTD_Sales], "Quantity", [YTD_Quantity], "Gross Profit", [YTD_GrossProfit], BLANK())
    ```
- **YTD vs PYTD Comparison**:
  ```DAX
  YTD vs PYTD = [S_YTD] - [S_PYTD]
  ```

---

## Dashboards Overview

### 1. Gross Profit Performance Overview

This dashboard provides an overview of gross profit performance, including:

- YTD vs PYTD comparison for Gross Profit, Sales, and Quantity.
- Dynamic titles reflecting selected filters.

---

### 2. Country and Product Type Analysis

This dashboard focuses on performance metrics by country and product type, including:

- Profitability segmentation by GP%.
- Country-wise and product-wise Gross Profit comparison.

---

### 3. Account Profitability Segmentation

This dashboard explores account profitability by segmenting GP% and selected metrics, including:

- Dynamic scatter charts for GP% vs. Gross Profit/Sales/Quantity.
- Insights into high-performing and underperforming segments.

---

## Key Features

- Dynamic titles and visuals reflecting selected filters.
- Comparison of YTD vs. PYTD for Gross Profit, Sales, and Quantity.
- Profitability segmentation by GP%.
- Dynamic filtering and drill-down capabilities for in-depth analysis.

---

## Technologies Used

- **Power BI**: For creating interactive and dynamic visualizations.
- **DAX (Data Analysis Expressions)**: For dynamic calculations and titles.
- **Power Query**: For data cleaning and transformation.

---

## How to Use the Dashboard

- Users can interact with the dashboard by selecting metrics (Gross Profit, Sales, or Quantity) and filtering by time period.
- Dynamic titles and visuals will update accordingly.
- Drill down into charts for a more granular analysis of profitability trends.

---

## Future Improvements

- Incorporate additional metrics for comprehensive analysis.
- Improve performance optimization for large data sets.
- Enhance interactivity with more drill-down and cross-filtering options.

---

## Conclusion

This project provides valuable insights into Plant Co.'s profitability metrics, supporting strategic decision-making and performance optimization. By segmenting gross profit across countries, product types, and time periods, stakeholders can identify growth opportunities and improve profitability.

With dynamic visuals and interactive filters, this dashboard empowers decision-makers to make data-driven choices, ensuring sustainable business growth.

---

## Acknowledgments

Special thanks to **Mo Chen YouTube Channel** for providing the raw data and inspiring this project.

---

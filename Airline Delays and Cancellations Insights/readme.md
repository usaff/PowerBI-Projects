# Airline Flight Status Analysis Dashboard

This project provides a comprehensive analysis of the airline industry, focusing on flight delays, cancellations, and on-time performance. By examining historical flight data, we aim to provide actionable insights to help airlines improve operational efficiency and enhance the passenger experience.

The insights drawn from this project help stakeholders understand industry trends, make informed decisions, and improve customer satisfaction by minimizing disruptions in air travel.

---

## Inspiration and Motivation

With the increasing dependence on air travel for personal and business needs, flight delays and cancellations can cause significant inconvenience and financial losses. This project was inspired by the desire to understand the patterns behind these disruptions and find ways to minimize them.

By analyzing historical flight data, we aim to provide airlines with the tools to enhance punctuality and improve customer experiences. This isn’t just about data analysis—it's about making air travel more reliable and stress-free for millions of passengers worldwide.

---

## Purpose of the Project

The primary goal of this project is to create an interactive Power BI dashboard that provides a comprehensive overview of airline flight statuses, focusing on:

- Identifying patterns in flight delays and cancellations.
- Understanding the impact of different factors (e.g., City, Airline, Day of the Week) on flight performance.
- Supporting airlines and stakeholders in making data-driven operational decisions.

---

## Data Source

The dataset used for this analysis is sourced from **Maven Analytics**, which provides historical flight information including status, airline, city, and cancellation reasons. The data has been cleaned and transformed for analytical purposes.

---

## Project Workflow

### Step 1: Loading and Preparing the Data

- Imported the flight data into Power BI.
- Cleaned and transformed the data using Power Query, including:
  - Removing null values and duplicates.
  - Standardizing column names for consistency.
  - Converting data types for better DAX compatibility.

### Step 2: Data Modeling

- Established relationships in the Model View.
- Ensured accurate calculations by connecting dimensions (e.g., City and Airline) to the fact table containing flight details.

### Step 3: Creating Measures Using DAX

- On-Time Flights:
  ```DAX
  On-Time Flights = CALCULATE([Total Flights], flights[Status] = "On-Time")
  ```
- Cancelled Flights:
  ```DAX
  Cancelled Flights = CALCULATE([Total Flights], flights[Status] = "Cancelled")
  ```
- Delayed Flights:
  ```DAX
  Delayed Flights = CALCULATE([Total Flights], flights[Status] = "Delayed")
  ```

### Step 4: Percentage Calculations for Flight Status

- % Cancelled:
  ```DAX
  % Cancelled = DIVIDE([Cancelled Flights], [Total Flights], "-")
  ```
- % Delayed:
  ```DAX
  % Delayed = DIVIDE([Delayed Flights], [Total Flights], "-")
  ```
- % On-Time:
  ```DAX
  % On-Time = DIVIDE([On-Time Flights], [Total Flights], "-")
  ```

### Step 5: Building the Flight Status Dashboard

The dashboard includes:

- Total Flights and On-Time % with trend analysis.
- City-wise Flight Count and Airline Delays breakdown.
- Cancellation Reasons and % Canceled by Day of the Week.
- Total Flights by Status using a stacked bar chart.

---

## Dashboards Overview

### 1. Flight Status Overview Dashboard

This dashboard provides an overview of flight statuses, including:

- On-Time, Delayed, and Cancelled flight counts.
- Trend analysis of flight statuses over time.

---

### 2. City and Airline Performance Analysis

This dashboard focuses on performance metrics by city and airline, including:

- City-wise Flight Count and On-Time % comparison.
- Airline-wise Delays and Cancellations breakdown.

---

### 3. Cancellation Reasons Analysis

This dashboard explores the reasons behind flight cancellations, including:

- Percentage of Cancellations by Reason.
- Day of the Week analysis for cancellation trends.

---

## Key Features

- Comprehensive overview of flight statuses including On-Time, Delayed, and Cancelled.
- Interactive visualizations for trends by month, city, airline, and day of the week.
- Detailed breakdown of cancellation reasons and their impact on overall flight performance.
- Dynamic filtering and drill-down capabilities for in-depth analysis.

---

## Technologies Used

- **Power BI**: For creating interactive and dynamic visualizations.
- **DAX**: For advanced calculations and measures.
- **Power Query**: For data cleaning and transformation.
- **SQL/MySQL**: (If used) For data extraction and querying.

---

## How to Use the Dashboard

- Hover over visual elements for detailed tooltips and insights.
- Click on specific data points to filter related visuals dynamically.
- Use slicers to customize the view by city, airline, or time period.
- Drill down into charts for a more granular analysis of flight trends.

---

## Future Improvements

- Integrate predictive analytics to forecast flight delays and cancellations.
- Enhance interactivity with more drill-down and cross-filtering options.
- Include more external factors like weather data for better insights.
- Optimize performance for faster data loading and visualization rendering.

---

## Conclusion

This project is more than just a data analysis exercise—it's about understanding the human impact behind the numbers. Every delayed or canceled flight affects passengers' lives, from missing important meetings to losing precious moments with loved ones.

By empowering airlines with data-driven insights, we contribute to improving punctuality and reliability, making air travel a better experience for everyone. This isn’t just about flights—it's about connecting people and making journeys smoother.

---

## Acknowledgments

Special thanks to **Maven Analytics** for providing the raw data and inspiring this project.

---

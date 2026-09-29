# Blinkit-Sales-Analysis-SQL

**Blinkit Sales Analysis – SQL & Power BI**

**📌 Project Overview**

This project presents an end-to-end analysis of Blinkit sales data using SQL Server and Microsoft Power BI.

The objective is to analyze sales performance, product characteristics, outlet performance, customer ratings, and outlet distribution through SQL-based analysis and an interactive Power BI dashboard.

The project covers the complete analytics workflow:

Data → Cleaning → SQL Analysis → KPI Development → Power BI Visualization → Business Insights

**🎯 Business Requirement**

To conduct a comprehensive analysis of Blinkit's sales performance, customer satisfaction, and inventory distribution to identify key insights and opportunities for optimization using KPIs and interactive visualizations.

**📊 Key KPIs**

The Power BI dashboard provides the following primary KPIs:

| KPI | Description | Dashboard Value |
| --- | --- | --- |
| **Total Sales** | Overall revenue generated | **$1.2M** |
| **Average Sales** | Average sale value | **$141** |
| **Number of Items** | Total item records | **8,523** |
| **Average Rating** | Mean customer rating | **3.92** |

**KPI	Description**
Total Sales	Overall revenue generated from items sold
Average Sales	Average sales value
Number of Items	Total number of item records
Average Rating	Average customer rating
Dashboard KPI Values

**Based on the dashboard:**

Total Sales: $1.2M
Average Sales: $141
Number of Items: 8,523
Average Rating: 3.92

Note: These values represent the current version of the dashboard shown in this project.

**🛠️ Tools & Technologies**
SQL Server
SQL Server Management Studio (SSMS)
Microsoft Power BI
Microsoft Excel
GitHub
PowerPoint
🧹 Data Cleaning

Before analysis, the Item_Fat_Content field was standardized because the dataset contained multiple representations of the same categories.

**For example:**

LF
low fat
Low Fat
reg
Regular

These values were standardized into:

Low Fat
Regular
SQL
UPDATE blinkit_data
SET Item_Fat_Content =
    CASE
        WHEN Item_Fat_Content IN ('LF', 'low fat')
            THEN 'Low Fat'
        WHEN Item_Fat_Content = 'reg'
            THEN 'Regular'
        ELSE Item_Fat_Content
    END;

The cleaned values were then validated using:

SELECT DISTINCT Item_Fat_Content
FROM blinkit_data;
📈 Power BI Dashboard
Dashboard Overview

The interactive dashboard analyzes Blinkit sales performance across multiple dimensions.

Dashboard Features

**The dashboard includes:**

KPI cards
Date/outlet analysis
Fat-content analysis
Item-type analysis
Outlet-size analysis
Outlet-location analysis
Outlet-type performance
Interactive filters
Cross-filtering between visuals
🔍 Analysis Performed
1. Total Sales by Fat Content

Analyzes sales performance based on:

Low Fat
Regular

It also supports comparison of related KPIs such as average sales, number of items, and average rating.

2. Total Sales by Item Type

Analyzes sales across different product categories.

The dashboard allows identification of item types contributing to overall sales.

3. Fat Content by Outlet

Compares Low Fat and Regular product sales across different outlet location types.

The SQL analysis uses a PIVOT operation to transform fat-content categories into columns.

4. Total Sales by Outlet Establishment

Analyzes total sales according to the outlet establishment year.

This helps understand how sales vary across outlets established during different periods.

5. Percentage of Sales by Outlet Size

Analyzes the contribution of different outlet sizes to total sales.

The SQL analysis uses a window function:

SUM(SUM(Total_Sales)) OVER ()

to calculate the overall sales total without collapsing the grouped result.

6. Sales by Outlet Location

Compares total sales across:

Tier 1
Tier 2
Tier 3

This provides a view of sales distribution across outlet location categories.

7. Metrics by Outlet Type

The dashboard compares multiple metrics across outlet types:

Total Sales
Average Sales
Number of Items
Average Rating
Item Visibility
🧮 SQL Analysis

The SQL analysis includes:

Data Cleaning
CASE
WHEN ...
THEN ...
END
Aggregations
SUM()
AVG()
COUNT()
Grouping
GROUP BY
Sorting
ORDER BY
Data Transformation
PIVOT
NULL Handling
ISNULL()
Window Functions
SUM(...) OVER()

These queries are available in:

SQL/Blinkit_Analysis.sql

Detailed explanations are available in:

Documentation/Blinkit_SQL_Analysis.md

📊 Dashboard Insights

The dashboard provides a consolidated view of:

Overall sales performance
Product-level sales distribution
Fat-content sales comparison
Outlet-size contribution
Outlet-location performance
Outlet-type performance
Customer rating
Item visibility

The interactive filters allow users to analyze the dashboard from different business perspectives.

📂 Project Files
Folder	Contents
SQL/	SQL Server analysis queries
PowerBI/	Power BI .pbix dashboard
Presentation/	Project presentation
Documentation/	Detailed SQL documentation
Dataset/	Project dataset
Images/	Dashboard and analysis screenshots
💡 Skills Demonstrated
SQL
Data cleaning
Data transformation
Aggregation
GROUP BY
CASE
PIVOT
ISNULL
Window functions
KPI calculations
Power BI
Dashboard development
KPI cards
Interactive slicers
Data visualization
Business reporting
Comparative analysis
Dashboard layout design
Business Analysis
Requirement understanding
KPI definition
Sales performance analysis
Outlet performance analysis
Product analysis
Business-focused visualization
🚀 Project Workflow
Raw Dataset
     ↓
Data Cleaning
     ↓
SQL Server
     ↓
Data Validation & Analysis
     ↓
KPI Development
     ↓
Power BI
     ↓
Interactive Dashboard
     ↓
Business Insights
     ↓
Presentation
📁 Repository

The complete project contains the SQL queries, Power BI dashboard, presentation, documentation, dataset, and dashboard screenshots.

👤 Author

Dara Ganesh

Data Analyst | Power BI | SQL | Excel | Python

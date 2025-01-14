# Car-sales-Data-Analysis-project-Power-BI-
Analyzed car sales data using Power BI, utilizing Power Query for data cleaning and transformation. Applied DAX for advanced calculations and insights. Created interactive visualizations with time intelligence functions to track sales trends and developed dynamic reports for stakeholders to explore sales by region, model, and period.

## Dataset Used
- <a href = "https://github.com/Arshawon/Car-sales-Data-Analysis-project-Power-BI-/blob/main/Car%20Sales.xlsx">Dataset</a>

## Problem Statement

The goal is to create a dynamic Car Sales Dashboard in Power BI that visualizes key performance indicators (KPIs) to track and analyze sales performance. The dashboard will focus on:

KPI Requirements:
- Sales Overview (YTD, MTD, YOY growth, PTYD comparisons)
- Average Price Analysis (YTD, MTD, YOY growth, PTYD comparisons)
- Cars Sold Metrics (YTD, MTD, YOY growth, PTYD comparisons)

Chart Requirements:
- Weekly YTD Sales Trend (line chart)
- YTD Sales by Body Style and Color (pie charts)
- YTD Cars Sold by Dealer Region (map chart)
- Company-wise Sales Trend (grid)
- Detailed Sales Information Grid (table with car model, style,   color, sales data, etc.)

The dashboard will offer real-time insights to help monitor performance, identify trends, and support data-driven decision-making.
## Steps followed 

### Data Import and Pre-processing:

1. Import sales data into Power BI (CSV, Excel).
2. Cleanse the data using Power Query: replace erroneous values (e.g., fix "DoubleÂ Overhead Camshaft"), and ensure correct headers by using the first row.
3. Check column quality and distribution in Power Query for errors.

### Creating Calendar Table for Time Intelligence:

Generate a Calendar Table: CALENDAR(MIN(car_data[Date]), MAX(car_data[Date])).

Extract Year, Month, and Week from the Calendar Table for time-based analysis:

Year = YEAR('Calendar Table'[Date])

Month = FORMAT('Calendar Table'[Date], "MMMM")

Week = WEEKNUM('Calendar Table'[Date])

### Data Modeling:

Connect the Calendar Table to the car sales data via the Date column.
Use model view to establish relationships between tables.
### Calculating KPIs with DAX:

1. YTD Sales: TOTALYTD(SUM(car_data[Price ($)]), 'Calendar Table'[Date])
2. PYTD Sales: CALCULATE(SUM(car_data[Price ($)]), SAMEPERIODLASTYEAR('Calendar Table'[Date]))
3. Sales Difference: YTD Sales - PYTD Sales
4. YOY Growth: (Sales Difference) / PYTD Sales
5. MTD Sales: TOTALMTD(SUM(car_data[Price ($)]), 'Calendar Table'[Date])
6. Average Price: SUM(car_data[Price ($)]) / COUNT(car_data[Car_id])
7. YTD Average Price: TOTALYTD([Avg Price], 'Calendar Table'[Date])
8. MTD Average Price: TOTALMTD([Avg Price], 'Calendar Table'[Date])
9. Cars Sold: COUNT(car_data[Car_id])
10. YTD Cars Sold: TOTALYTD(COUNT(car_data[Car_id]), 'Calendar Table'[Date])

Format KPIs as needed, e.g., concatenate sales info and format in millions or thousands.

### Creating Visualizations:

Line Chart: YTD Sales Weekly Trend.

Pie Charts: YTD Sales by Body Style and Color.
Map Chart: Sales distribution by dealer region.
Grid Table: Company-wise sales trend and detailed car sales data.
Area Chart: Display YTD Sales Weekly Trend with max sales point.
Dashboard Design:

Arrange KPIs at the top and detailed visualizations below.
Add slicers for filtering by body style, color, region, and company.


# Snapshot of Dashboard 

![Car sales Data Analysis project overview](https://github.com/user-attachments/assets/3523ebf0-2f86-4981-923b-ae0536ae841b)

![Car sales Data Analysis project Details](https://github.com/user-attachments/assets/d53d99ba-ec37-401c-bf3a-c64cdbf65b82)
 

# Insights

### Sales Overview:

Year-to-Date (YTD) Total Sales: $371.2M
Month-to-Date (MTD) Total Sales: $54.28M
Year-over-Year (YOY) Growth in Total Sales: 23.59%
Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales: $70.8M

![Car sales Data Analysis  1](https://github.com/user-attachments/assets/d679ae54-a3b6-44e6-a273-566596e83903)
### Average Price Analysis:

YTD Average Price: $28.02K
MTD Average Price: $28.26K
YOY Growth in Average Price: -0.79% (indicating a slight price decrease compared to last year)
Difference between YTD Average Price and PTYD Average Price: The average price has slightly decreased compared to the previous year.

![Car sales Data Analysis  2](https://github.com/user-attachments/assets/27f04c76-7a72-434d-8fe9-d579064ddb6e)
### Cars Sold Metrics:

YTD Cars Sold: 13.3K
MTD Cars Sold: (This seems to be an error as it shows sales amount, which should be the total number of cars sold.)
YOY Growth in Cars Sold: 19.73%
Difference between YTD Cars Sold and PTYD Cars Sold: 2.62K more cars sold compared to the previous year.

![Car sales Data Analysis  3](https://github.com/user-attachments/assets/bd02178d-baea-42d6-9383-d51373069579)


## visualizations for deeper analysis:

### YTD Sales Weekly Trend:

A line chart showcasing weekly YTD sales, highlighting that the 36th week had the highest sales, which can help identify peak sales periods.

![Car sales Data Analysis  4](https://github.com/user-attachments/assets/a3f735ed-217e-42ca-95fe-96d5a633c4f4)
### YTD Total Sales by Body Style:

A pie chart displaying the distribution of YTD total sales across different body styles. SUVs and Hatchbacks are the two most popular body styles.

![Car sales Data Analysis  5](https://github.com/user-attachments/assets/6ba50c52-cfca-4ad2-be0c-b05a467e8b9a)

### YTD Total Sales by Color:

A pie chart showing the distribution of YTD sales by car color, with pale white being the most popular color among customers.

![Car sales Data Analysis  6](https://github.com/user-attachments/assets/913d5d60-bfe2-43d0-875b-0108b3a8f5b4)

### YTD Cars Sold by Dealer Region:

A map chart showing the distribution of sales by geographical region, identifying Austin, Janesville, and Scottsdale as the top-performing dealer regions.

### Company-Wise Sales Trend in Grid Form:

A tabular grid displaying YTD sales data for each company. The grid will include major car brands like Chevrolet, Ford, and Dodge, helping to compare the performance of each.

![Car sales Data Analysis  7](https://github.com/user-attachments/assets/6b6ba4ce-a703-4651-98f4-067ada26fe43)
### Details Grid Showing All Car Sales Information:

A detailed grid presenting all relevant data for each car sale, including car model, body style, color, sales amount, dealer region, and sale date (covering sales from January 2, 2022, to December 31, 2023).

![Car sales Data Analysis  8](https://github.com/user-attachments/assets/b4940a78-1a8e-4c35-921c-d27a7e2ed677)


### Dealer and Company Performance:

The company-wise sales grid enables comparisons between different car companies like Chevrolet, Ford, and Dodge, helping to focus on top-performing brands.
### Car Sales Information:

The detailed sales grid gives a deeper view into each sale, including sales amount, car model, and other key attributes, assisting in understanding customer preferences and improving sales tactics.
# Conclusion
This Car Sales Dashboard will empower the dealership to track, analyze, and act on sales data in real-time. By leveraging insights from key KPIs, sales trends, and detailed analysis, the company can make informed decisions, optimize its sales strategies, enhance customer satisfaction, and drive growth.

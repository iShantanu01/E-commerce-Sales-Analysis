# E-commerce-Sales-Analysis

# 1. Project Overview: 
In today’s data-driven digital economy, analyzing e-commerce sales data has become crucial for businesses to optimize operations, identify sales trends, and increase profitability. This project focuses on extracting actionable insights from e-commerce transactions using a combination of Exploratory Data Analysis (EDA) in Python and interactive visualizations in Power BI. Unlike dashboard-only approaches, this project highlights the essential role of EDA in cleaning, understanding, and shaping the data before visualization. Using the CRISP-DM framework, the analysis explored key sales trends, regional performance, and product demand, based on features like Order Date, Product, Quantity Ordered, Price Each, and Address. The insights derived from EDA guided the design of a business-focused Power BI dashboard.

# 2. Project Objective:
The objective of this project is to extract accurate, business-relevant insights from e-commerce sales data by following the CRISP-DM framework, with a strong emphasis on Exploratory Data Analysis (EDA) as the foundation for precision-driven reporting. The project begins with consolidating and standardizing 12 months of sales data from separate CSV files into a unified, clean dataset using Python. Through detailed EDA, patterns in product performance, regional demand, and monthly sales trends were uncovered. These insights were then used to design a dynamic Power BI dashboard that enables stakeholders to make informed, data-driven decisions based on thoroughly validated and structured data.

![Image Alt](https://github.com/iShantanu01/E-commerce-Sales-Analysis/blob/main/Ecom_objectuve.png)

# 3. Dataset Description:
The dataset contains e-commerce sales transactions with the following columns:
Order ID: Unique identifier for each purchase transaction.
Product: Name of the product sold.
Order Date: Date and time when the order was placed.
Quantity Ordered: Number of units ordered for a product in a transaction.
Price Each: Price of a single unit of the product.
Address: Full shipping address, which includes street, city, state, and ZIP code .

# 4. Tools Used:
Python:   was used for data preprocessing and exploratory data analysis (EDA). It helped in loading and merging 12-month CSV files, cleaning
and standardizing the data, creating new columns (e.g., Sales, Month, City), and uncovering trends and patterns using libraries like Pandas,
Matplotlib, and Seaborn.

Power BI:  was used to build an interactive dashboard based on the insights gathered from EDA. The cleaned and prepared dataset was loaded
into Power BI to create visuals such as bar charts, line graphs, and slicers, allowing users to explore sales performance by time, product, and region.


# 5. Exploratory Data Analysis (EDA)
It is the process of analyzing datasets to summarize their main characteristics using statistical methods and visualizations. It is often the first and crucial step before building predictive models, as it helps in understanding the structure of data, detecting patterns, identifying anomalies, and selecting relevant features. EDA guides effective data preprocessing and model selection, ultimately improving model performance and interpretability.

1. Profile of Data
Understand data types and structure (e.g., numerical, categorical)
Identify missing values, duplicates, or incorrect formats
Assess data completeness and consistency
2. Statistical Analysis
Calculate key metrics like mean, median, mode, standard deviation
Analyze distributions and detect outliers
Explore relationships and correlations between variables
3. Graphical Analysis
Univariate Analysis: Focuses on visualizing individual variables to understand their distribution, central tendency, and outliers using charts like histograms, bar plots, or box plots.
Bivariate Analysis: Examines the relationship between two variables through visual tools such as scatter plots or line plots, helping identify trends, correlations, or group differences.
Multivariate Analysis: Involves analyzing and visualizing interactions among three or more variables using heatmaps, pair plots, or facet grids to uncover deeper patterns and variable dependencies.

# 6. DAX used:
1. calender = CALENDAR("2019-01-01","2020-01-01") 
2. Month = FORMAT(calender[Date].[Date] , "MMMM")
3. month_no = MONTH(calender[Date].[Date]) 
4. year = YEAR(calender[Date])
5. Income_movement = SUM(ecom[Order Price])-[Prior_month_revenue]
6. month_avg_revenue= CALCULATE(AVERAGEX(VALUES(calender[Month]),CALCULATE(SUM(ecom[Order Price]))) , calender[year] = 2019)
7. MTD = TOTALMTD(SUM(ecom[Order Price]) ,calender[Date].[Date])
8. QTD = TOTALQTD(SUM(ecom[Order Price]) ,calender[Date].[Date])
9. Order Price = ecom[Quantity Ordered] * ecom[Price Each] 
10. Prior_month_revenue = CALCULATE(SUM(ecom[Order Price]) , DATEADD(calender[Date].[Date],-1, MONTH))
11. Quarter = "Q" & QUARTER(ecom[Date(New)]) 

# Dashboard:-
<img width="650" alt="ecom_distribution" src="https://github.com/user-attachments/assets/005e43a5-7257-4394-983b-f08782e662ee" />


# 7. KPI-
1. What is the Product Price Range?
2. How many product are ordered in a certain range?
3. What is the Product name and ordered quantity (form the Product list)?
4. Mean , Median , Standard Deviation- how far the data point lies around the mean?
5. Is the Product Ordered count and Revenue ratio is same? (comparison)
6. What is the order count and Revenue for a Particular category?
7. What is the total revenue?
8. What is the monthly revenue trends?
9. Which city causes the max revenue and min revenue?
10. What is the Top and button revenue cities?
11. What are the revenue generated by each  city?
12. What is the revenue generated by each category?
13. What is the share percentage of revenue generation by each category?
14. High and low revenue generated category?
15. Orders vs quantity Orders by each city?
16. What are the orders count and ordered quantity for each city? (helps in stock and inventory)
17. Orders vs orders quantity by category?
18. What is the orders and orders quantity of a product category? (help in stock and inventory)
19. What is the product ordered count and quantity ordered for each  product?
20. Orders vs quantity orders comparison.
21. Which month revenue increases from the last month or decreases? - month wise revenue movement
 















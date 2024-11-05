# LITA-PROJECT

  # Project Overview
The aim of this project is to analyse the sales perfomance of a retail store by exploring the sales data to uncover key insights such as top-selling products, regional 
performance, and monthly sales trends. Additionally, this project involves analyzing customer data for a subscription service to identify segments and trends. The aim is to  track subscription types, and identify key trends in cancellations and renewals. Power BI dashboard was used to highlights these findings.

# Introduction 
Data analysis is the practice of working with data to glean useful information, which can then be used to make informed decisions. Extracting meaning from data empowers us to make better decisions. And we’re living in a time when we have more data than ever at our fingertips. Because of that, companies have been wisening up to the benefits of leveraging data—and turning to data analysis to find insights to further business goals.  To carry out data analysis, some tools are used for data cleaning they include; Ms Excel, SQL, Power BI. 

# Tools Used
Ms Excel
   - Data cleaning: Duplicates were found in the dataset, Excel was used to clean the duplicates.
   - Pivot tables: Pivot table was used to summarize total sales by product, region, and month. 

SQL

 - Importing: The dataset was imported from Excel as flat file into SQL studio before executing the queries.
    
Power BI

  - Creating dashboard: a dashboard was created to visualize the insights found in Excel and SQL. 
    The dashboard included a sales overview, top-performing products, and 
regional breakdowns

# Discussion/Result
   - Sales Data

The sales data was analyzed and key insights were discovered, which include; Total sales was gotten by multiplying unitprice by quantity sold. The total revenue generated was 2M. Shoes was the highest selling product with total sales of NGN 613,380. The highest monthly total sales for the current year was in Ferbruary with a total sales of NGN 298,800. South region had the highest contribution in percentage with a total sales of 44.15%. 

 

Below are pictorial representations of the key insights discovered.


# MS Excel

![SALES DATA MS EXCEL](https://github.com/Abasianam/LITA-PROJECT/blob/main/SALES%20DATA%20MS%20EXCEL.jpg)


# SQL
I executed some queries to discover key insights of the data. The queries are displayed below:

select * from   [dbo].[CAPSTONE DATA]

-----------retrieve the total sales for each product category------

select product, sum (Total_Sales) as Total_Sales from [dbo].[CAPSTONE DATA]
Group By Product

-------find the number of sales transactions in each region----

Select Region, COUNT(OrderID)
AS No_of_Sales_Transaction from [dbo].[CAPSTONE DATA]
Group By Region

------find the highest-selling product by total sales value--------

Select Product, Sum (Total_Sales) As Highest_Selling from [dbo].[CAPSTONE DATA]
Group By Product
Order By 2 Desc

----calculate total revenue per product-------

select product, sum (Total_Sales) as Total_Revenue from [dbo].[CAPSTONE DATA]
Group By Product

-----calculate monthly sales totals for the current year-----

Select Orderdate, Sum (Total_Sales) as Monthly_sales from [dbo].[CAPSTONE DATA]
Where Orderdate between '2024-01-01' and '2024-12-31'
Group By Orderdate
Order By Orderdate

-----find the top 5 customers by total purchase amount----

Select TOP 5 Customer_ID, SUM (Total_Sales) as Total_Purchase from [dbo].[CAPSTONE DATA]
Group By Customer_ID
Order By Total_Purchase Desc

---------calculate the percentage of total sales contributed by each region--------

With Region AS (Select Region, Sum (Total_Sales) AS Sales from [dbo].[CAPSTONE DATA]
Group By Region)
Select Region, (Sales * 100.0 / (Select Sum (Total_Sales) from [dbo].[CAPSTONE DATA])) AS Sales_Percentage From Region


------identify products with no sales in the last quarter-----

Select product from [dbo].[CAPSTONE DATA]
where product NOT IN (
SELECT PRODUCT 
from [dbo].[CAPSTONE DATA]
where orderdate >= '2024-06-01' AND Orderdate <= '2024-08-31')

# Power BI

  
![Power BI visualisation](https://github.com/user-attachments/assets/67058485-6765-444f-a827-80ffd0cb1b9e)











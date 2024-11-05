# Introduction Overview 

 This project has to do with analyzing the sales performance of a retail store. 
 Sales data was explored to uncover key insights such as top-selling products, regional 
performance, and monthly sales trends. The aim was to produce an interactive Power BI 
dashboard that highlights these findings. 

# Tools Used 
# MS Excel

![SALES DATA MS EXCEL](https://github.com/user-attachments/assets/4a82e99e-f163-4377-ae3e-23dfb2cde6e5)


 
 - Duplicates were found in the data and deleted.
  
 - Total revenue was derived by multiplying unitprice by sales.

 - Pivot tables pivot tables was to summarize total sales by product, region, and month.

   # SQL
   I executed some qeries to retrieve
   
  - the total sales for each product category.
  - find the number of sales transactions in each region.
  - find the highest-selling product by total sales value.
  - calculate total revenue per product.
  - calculate monthly sales totals for the current year.
  - find the top 5 customers by total purchase amount.


 # Power BI

I created a dashboard that visualized the insights found in Excel and SQL. The 
dashboard included a sales overview, top-performing products, and 
regional breakdowns.

# Discussion/Result

The total number of customers was 9921. The total revenue was 2M. Top performing products were, hats and shoes. 
The product with the highest sales was shoes, with a total of NGN 613,380. Southern region had the highest number of sales, 2,480.
Ferbruary had the highest monthly sales totals for the current year, NGN 298,800. Southern region had the highest percentage of total sales, 44.1%. 

# MS Excel 

# SQL

The following queries were executed to discover key insights:
select * from   [dbo].[CAPSTONE DATA]

- Retrieve the total sales for each product category

select product, sum (Total_Sales) as Total_Sales from [dbo].[CAPSTONE DATA]
Group By Product

- Find the number of sales transactions in each region

Select Region, COUNT(OrderID)
AS No_of_Sales_Transaction from [dbo].[CAPSTONE DATA]
Group By Region

- Find the highest-selling product by total sales value

Select Product, Sum (Total_Sales) As Highest_Selling from [dbo].[CAPSTONE DATA]
Group By Product
Order By 2 Desc

- Calculate total revenue per product
  
select product, sum (Total_Sales) as Total_Revenue from [dbo].[CAPSTONE DATA]
Group By Product

- Calculate monthly sales totals for the current year

Select Orderdate, Sum (Total_Sales) as Monthly_sales from [dbo].[CAPSTONE DATA]
Where Orderdate between '2024-01-01' and '2024-12-31'
Group By Orderdate
Order By Orderdate

- Find the top 5 customers by total purchase amount

Select TOP 5 Customer_ID, SUM (Total_Sales) as Total_Purchase from [dbo].[CAPSTONE DATA]
Group By Customer_ID
Order By Total_Purchase Desc

- Calculate the percentage of total sales contributed by each region

With Region AS (Select Region, Sum (Total_Sales) AS Sales from [dbo].[CAPSTONE DATA]
Group By Region)
Select Region, (Sales * 100.0 / (Select Sum (Total_Sales) from [dbo].[CAPSTONE DATA])) AS Sales_Percentage From Region


- Identify products with no sales in the last quarter

Select product from [dbo].[CAPSTONE DATA]
where product NOT IN (
SELECT PRODUCT 
from [dbo].[CAPSTONE DATA]
where orderdate >= '2024-06-01' AND Orderdate <= '2024-08-31')

# Power BI
    
  ![Power BI visualisation](https://github.com/user-attachments/assets/0714a684-e5c4-4add-bf56-1af994da980f)

  


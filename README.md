# LITA_-Project_Sales_Data
Documentation of LITA Capstone Project

## Project Title: Sales Performance Analysis for a Retail Store
A sales performance analysis in a retail store focuses on evaluating and understanding major sales trends,
identifying high-performing products, and uncovering areas needing improvement
Here’s an outline to help structure a sales performance analysis project:


1. Objective
- Analyze historical data to uncover seasonal patterns, peak sales periods, and growth trends.
- Identify products with the highest sales volume or revenue to focus marketing and stocking efforts effectively.
- Assess performance across different regions to understand geographical preferences and opportunities for expansion or targeted marketing
  

2. Data Collection

The main data sources for this analysis is the "Data Sales" file, which are open-source datasets.


3. Data Description
The dataset includes the following fields:
- OrderID: Unique identifier for each order.
- Customer Id: Identifier for each customer.
- Product: Type of product sold.
- Region: Geographic region of the sale.
- OrderDate: Date of the order.
- Quantity: Number of items sold per order.
- UnitPrice: Price per unit of each product.

4. Tools Used

- Excel: for data cleaning and visualization
  
- SQL: Applied for data cleaning through queries
- PowerBI: Leveraged for both data cleaning and visualization

5. Data Cleaning and Preparations 
- Data loading and inspection
- Handling missing variables
- Data Cleaning and Formatting

  ## Answers to the questions 

1. Excel
- Exploration of the sales data.
![Screenshot  Excel](https://github.com/user-attachments/assets/13b17097-f4b9-40fa-8ff8-a5163df1192c)

- Average sales per product
  
  AVERAGRIF
```
=AVERAGEIF(C2:C9922,C2,H2:H9922)
```

- Total revenue by region.
  
  SUMIF
  ```
  =SUMIF(D2:D9922,D2,H2:H9922)
  ```

  
  ![Excel](https://github.com/user-attachments/assets/69261ce0-0b01-42e5-ac34-54ca0b725a0b)

---

  2. SQL
 Load the dataset into your SQL Server environment

```
Create Database CAPSTONE_PROJECT_SALES_DATA

Select *from Sales_Data
```

o Retrieve the total sales for each product category.
  ```
Select Product, 
SUM(Revenue) AS TotalSales
From [dbo].[Sales_Data ]
Group By Product;
```

![Sql Qest1](https://github.com/user-attachments/assets/aa99d9ab-78f4-4e4e-840b-76b0800ec71e)

o Find the number of sales transactions in each region.
```
Select Region,
Count(*) AS NumberofTransactions
From [dbo].[Sales_Data ]
Group By Region;
```

![Sql Qest2](https://github.com/user-attachments/assets/f9e18319-71ec-4ea1-b2a7-b52830b3a5d2)

o Find the highest-selling product by total sales value.
```
Select Product,
SUM(Quantity * UnitPrice) AS
TotalSalesValue
From [dbo].[Sales_Data ]
Group By Product
```

![Sql Qest3](https://github.com/user-attachments/assets/1f940064-1ff8-41c9-9c5f-79fe61fbc59a)


o Calculate total revenue per product. 

```
Select Product,
SUM(Quantity * UnitPrice) AS
TotalRevenue
From [dbo].[Sales_Data ]
Group By Product
```
![Sql Qest4](https://github.com/user-attachments/assets/d5d4a67b-9542-476b-8a7c-572bcbefc29a)

o Calculate monthly sales totals for the current year. 

```

Select Month(orderdate) AS
Month, SUM(quantity * UnitPrice) AS
monthly_sales
From [dbo].[Sales_Data ]
Where Year(orderdate)= 
Year(GETDATE())
Group By Month(orderdate);
```

![Sql Qest5](https://github.com/user-attachments/assets/8b9fa0e1-01e0-4d14-87fa-48c5758b082d)


o Find the top 5 customers by total purchase amount.

```
Select Top 5 [Customer_Id],
SUM(quantity * UnitPrice) AS
TotalPurchaseAmount
From [dbo].[Sales_Data ]
Group By [Customer_Id]
Order By TotalPurchaseAmount DESC;
```

![Sql Qest6](https://github.com/user-attachments/assets/9df11552-6d61-4372-9e1a-ba1e8e7a4e04)

o Calculate the percentage of total sales contributed by each region.
```
With TotalSales AS (
Select SUM(quantity * UnitPrice) AS 
TotalSalesAmount
From [dbo].[Sales_Data ]
)
Select Region, SUM(quantity * UnitPrice) AS RegionSales,
(SUM(quantity * UnitPrice) * 100.0)/ts.TotalSalesAmount AS PercentageContribution
From [dbo].[Sales_Data ]
CROSS JOIN TotalSales ts
Group By Region,
ts.TotalSalesAmount;
```

![Sql Qest7](https://github.com/user-attachments/assets/e807dcf7-9756-4126-a005-b3ba5c20e88e)

o identify products with no sales in the last quarter
```
SELECT DISTINCT Product
FROM [dbo].[Sales_Data ]
WHERE Product NOT IN (
SELECT Product
FROM [dbo].[Sales_Data ]
WHERE OrderDate >= DATEADD(QUARTER, -1, GETDATE())
)
```
![Sql Qest8](https://github.com/user-attachments/assets/37369467-8582-4ab2-86b6-5db8a4e103c4)

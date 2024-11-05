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

o find the number of sales transactions in each region.
```
Select Region,
Count(*) AS NumberofTransactions
From [dbo].[Sales_Data ]
Group By Region;
```

![Sql Qest2](https://github.com/user-attachments/assets/f9e18319-71ec-4ea1-b2a7-b52830b3a5d2)



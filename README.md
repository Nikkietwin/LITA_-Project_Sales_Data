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

Excel
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



  

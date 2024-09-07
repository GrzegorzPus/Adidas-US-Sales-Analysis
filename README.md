# 📊 Adidas US Sales Analysis

Welcome to my repository! This section provides an overview of my project, which focuses on the analysis of Adidas sales data using a combination of Python and SQL techniques. Below is a detailed outline of the project::
<br>
<br>
## 🛒 Project 1: [Adidas Sales Data Analysis - Raport](https://github.com/GrzegorzPus/Adidas-US-Sales-Analysis/blob/main/Sales%20Analysis.ipynb)

This project involves analyzing a comprehensive dataset of Adidas' US sales. The objective is to explore various sales metrics and trends to gain actionable insights into the company's performance. The analysis focuses on multiple key areas such as overall sales performance, profitability, product performance, and time-based trends.


#### Key Areas of Analysis:
1. **General Sales Analysis**:
   - Total sales revenue, top retailers, and sales distribution by region, state, and cities.
   - Analysis of sales by product categories, including footwear and apparel, and gender-wise sales distribution.
   - Revenue generated per invoice, unique retailers involved, and operating profit by region.

2. **Profit and Margin Analysis**:
   - A detailed breakdown of operating profit across retailers, regions, and product types.
   - Investigating trends in operating margin by sales methods (e.g., online vs. in-store).
   - Gender-wise profit analysis, and identification of products or retailers with the highest and lowest operating margins.

3. **Product Performance**:
   - Identifying top-selling products, revenue generated per unit, and the distribution of units sold across different product types.
   - Price per unit by retailer, and an evaluation of product categories contributing the most to sales and profitability.
   - Trends in athletic vs. street footwear sales, and profitability per unit sold.

4. **Time and Seasonal Analysis**:
   - Monthly and seasonal variations in sales, operating margins, and units sold.
   - Exploring peak sales periods, including quarterly trends and the impact of seasons on product categories.
   - Trends in sales methods and time-based analysis of retailer performance.

### Goals of the Project:
- **Improve business decision-making** by identifying top-performing regions, retailers, and products.
- **Enhance profitability** by understanding operating margins and product pricing strategies.
- **Forecast future trends** by examining time-based sales variations, including seasonal peaks and monthly performance.

<br>

   ### 📊 Example Visualizations

  ![image](https://github.com/user-attachments/assets/618f8433-a8a5-448e-b5eb-251879df1741)


   *Profit Comparison*
<br>
<br>

## 🛠️ Technologies

- **Programming Language**: Python
- **Libraries**: `pandas`  `numpy`  `matplotlib`  `seaborn`

---
<br>

## 🛒 Project 2: [Adidas Sales Data Analysis Using SQL](https://github.com/GrzegorzPus/Adidas-US-Sales-Analysis/blob/main/Sales%20Analysis%20in%20SQL.sql)

This project focuses on analyzing Adidas' US sales data by executing SQL queries to explore critical business metrics and trends. The goal is to provide actionable insights to improve decision-making and operational efficiency. The analysis is structured around four key areas: general sales performance, profitability, product performance, and seasonal trends.


#### Key Areas of Analysis:

1. **General Sales Analysis**:
   - SQL queries were used to calculate **total sales revenue**, identify **top retailers** and analyze **sales distribution by region, state, and cities**.
   - The data was further broken down by **product categories** (footwear, apparel) and **gender-wise sales** using SQL `GROUP BY` and `SUM` functions.
   - Specific queries helped determine top retailers and cities by sales and calculate cumulative sales trends across regions using window functions such as `ROW_NUMBER`, `RANK` and `PARTITION BY`.

2. **Profit and Margin Analysis**:
   - Using SQL, we performed an in-depth analysis of **total operating profit** by retailers and regions, as well as product types.
   - `CTE` were particularly useful for hierarchical calculations, such as determining **profitability by product category**, where initial subcategories were calculated and later grouped into broader categories.
   - By analyzing **profitability per unit sold** and **operating margin trends** by state and retailer, the project reveals key drivers of profitability.

3. **Product Performance**:
   - SQL queries were designed to identify **top-selling products**, **average price per unit** by category using windows functions like `LAG` and `LEAD` which helped analyze sales trends by comparing product sales between months or quarters.
   - Special attention was given to **product pricing** strategies, with SQL used to analyze the **price per unit** by retailer and the overall profitability of different products.
   - Additionally, trends in **athletic vs. street footwear** sales were explored using SQL `CASE` statements and filtering conditions.

4. **Time and Seasonal Analysis**:
   - SQL `DATE` functions were used to explore **monthly and seasonal sales variations**, including identifying peak sales periods and understanding **quarterly sales trends**.
   - Queries evaluated **seasonal impacts on operating margin** and product sales, while also providing insights into **monthly performance** across different regions and retailers.

### Goals of the Project:
- **Enhance business decision-making** by leveraging SQL to extract insights on top-performing regions, retailers, and products.
- **Optimize profitability** through a detailed understanding of operating margins, sales methods, and product pricing.
- **Forecast sales trends** by analyzing time-based variations such as monthly, quarterly, and seasonal patterns.


<br>

 ### 👨‍💻 Sample Code
   ```sql
WITH PeakSales AS (
SELECT 
    Retailer,
    YEAR(InvoiceDate) AS Year,
	DATENAME(MONTH, InvoiceDate) AS Month,
    SUM(TotalSales) AS TotalSales,
	RANK() OVER (PARTITION BY Retailer ORDER BY SUM(TotalSales)) AS Peak
FROM 
    SalesData
GROUP BY
    Retailer,
    DATENAME(MONTH, InvoiceDate),
    MONTH(InvoiceDate),
    YEAR(InvoiceDate)
)
SELECT 
	Retailer,
	Year,
	Month,
	TotalSales
FROM
	PeakSales
WHERE Peak = 1
ORDER BY TotalSales DESC;
   ```
<br>

## 🛠️ Technologies

- **Programming Language**: SQL
- **Functions**: `GROUP BY`  `SUM`  `CASE`  `ORDER BY`  `CTE`  `WINDOWS FUNCTIONS`  `WHERE`  `CAST`  `TEMPORARY TABLE`

---
<br>
## 👥 Contact

If you have any questions about the projects or would like to discuss potential collaborations, feel free to reach out:

- **[LinkedIn](https://www.linkedin.com/in/grzegorz-pu%C5%9B/)** 

Thank you for visiting my repository!

---

#Python #R #Excel #Finance #GARCH #Cointegration #DataAnalysis #MachineLearning #Investments #Microsoft #TimeSeriesAnalysis

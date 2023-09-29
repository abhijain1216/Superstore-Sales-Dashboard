# Superstore Sales Dashboard

### *Project Summary*

The Superstore sales dashboard utilized a Kaggle dataset to find business insights about sales and profit. The Sample Superstore Sales dataset provides sales data for the United States, including information on products, orders, and customers. The data was initially in denormalized form, underwent normalization, and was transformed into four tables: dimCustomer, dimProducts, dimShip, and factSales. Data preprocessing was done to ensure that the data was free from errors and ready for analysis. Irrelevant columns were removed, and the error in the date format was also handled effectively. A new dimDate table was created that contained all dates, and then additional date-related columns were generated. A measures table was also created to consolidate all measures.Data modeling was done to establish one-to-many relationships between the factSales table and the dimension tables, resulting in a star schema.Time intelligence functions were also utilized in our analysis that enable us to manipulate data using time periods, including days, months, quarters, and years,and compare calculations over those periods. The resulting dashboard featured various visualizations including bar charts,pie chart, cards, tables, area chart tool tip, slicers and filters. The superstore sales analysis project aimed to provide insights about sales and profit over years across product categories, segments, and regions. The insights that have been found from the dashboard will be helpful in making business and strategic decisions.


### *Problem Statement*
Build a Superstore Sales Dashboard that aims to provide data-driven insights regarding sales and profit among various states and regions in the United States. The superstore seeks to achieve sustainable revenue growth and profitability through the effective use of the dashboard's insights.


### *Business Objective*
The business objective of the superstore sales dashboard is to increase sales and profitability by leveraging data-driven insights. Obtained insights will be helpful in making business decisions and planning market and advertisement strategies regarding future sales. This information will also be useful in identifying opportunities for growth and improvement, such as cross-selling, upselling, and product diversification. By utilizing the insights provided by the dashboard, the superstore aims to achieve sustainable growth and profitability.


### *Dataset Information*

#### *Dataset Link*

https://www.kaggle.com/datasets/vivek468/superstore-dataset-final

#### *Variable Description*

* **Row ID** - Unique ID for each row
* **Order ID** - Unique Order ID for each Customer
* **Order Date** - Order Date of the product
* **Ship Mode** - Shipping Mode specified by the Customer
* **Customer ID** - Unique ID to identify each Customer
* **Customer Name** - Name of the Customer
* **Segment** - The segment where the Customer belongs 
* **Country** - Country of residence of the Customer
* **City** - City of residence of of the Customer
* **State** - State of residence of the Customer
* **Postal Code** - Postal Code of every Customer 
* **Region** - Region where the Customer belong
* **Product ID** - Unique ID of the Product
* **Category** - Category of the product ordered
* **Sub-Category** - Sub-Category of the product ordered
* **Product Name** - Name of the Product
* **Sales** - Sales of the Product
* **Quantity** - Quantity of the Product
* **Profit** - Profit/Loss incurred

### *Dashboard*

<img width="623" alt="Superstore Sales Dashboard" src="https://github.com/abhijain1216/Superstore-Sales-Dashboard/assets/129052975/114df462-96d6-4092-8eec-d63de4dedeb3">

### *Data Model*

<img width="605" alt="Data Model" src="https://github.com/abhijain1216/Superstore-Sales-Dashboard/assets/129052975/018a798f-affd-46f1-b256-b7e306716837">

### *DAX Expressions Used*
The DAX Expressions used for creating measures in the Measure Table are:
* *Total sales = CALCULATE(SUM(factSales[Sales]))*
  
* *YTD Sales = TOTALYTD([Total sales],'dimDate'[Date])*
  
* *LY YTD Sales = COALESCE(CALCULATE(TOTALYTD([Total sales],'dimDate'[Date]),SAMEPERIODLASTYEAR('dimDate'[Date])),0)*
  
* *YTD sales Growth % = CALCULATE(DIVIDE(([YTD Sales]-[LY YTD Sales]),[LY YTD Sales],0))*

Where,   
YTD sales - Year-to-date sales   
LY YTD Sales - Last Year-to-date sales
       
DAX Expressions used for creating columns in Date table are:

* *Date = CALENDAR(MIN(factSales[Order Date]),MAX(factSales[Order Date]))*
  
* *Year = FORMAT(dimDate[Date],"yyyy")*
  
* *Month = FORMAT(dimDate[Date],"mmmm")*
  
* *Month year = FORMAT('dimDate'[Date],"MMM-YY")*
  
* *Quarter = "Q" & QUARTER(dimDate[Date])*
  
* *Month Number = Month(dimDate[Date])*

### *Insights*

* Peak sales occur in March, September, and November.

* Total sales are highest for 2017 and minimum for 2015.

* The West region has the highest sales and profits among all other regions, whereas the South stands last on the list.

* California, New York, Pennsylvania, Texas, and Washington have the highest contribution in total sales and profits.

* The lowest sales are in South Dakota, District of Columbia, Kansas, Maryland, and Nevada.

* The least profitable states are Nevada, Oregon, Arkansas, Kansas,and North Carolina.

* Subcategories like Phones, chairs, Binders, Storage and Tables are among the top selling goods, while Supplies, Art, Envelopes, Fasteners and labels are the lowest selling items.

* Technology alone holds 51% of the total profit.Technology has the highest sales (836K) and profits (145K), followed by Furniture (742K sales, 18K profits) and Office Supplies (719K sales, 122K profits). 

* From 2015 to 2016, growth in YTD sales was the highest. YTD sales in 2016 increased by 29.5% from 2015.

* From 2014 to 2015, there was the highest downfall in sales of supplies by 86%.

* For all years, quarterly sales is maximum for the fourth quarter.



### *Recommendations*

* Increase marketing efforts for Office Supplies and Technology products during March to capitalize on the tax season.

* Focus on Furniture, Technology and Office Supplies during September to target back-to-school/college sales.

* Adopt different marketing and advertisement strategies to target the right audience.

* Focus on increasing sales in states where sales and profit are very low when compared to other states, such as South Dakota, District of Columbia, Kansas, Maryland, Nevada, North Carolina, Arkansas, Oregon.

* Increase efforts to improve profits in the South and Central Regions.

* Conduct market research to understand the needs and preferences of customers in states with very low sales. Adopt a targeted marketing campaign to spread awareness about the brand and its products.

* Continuously monitor and analyze sales and profit trends by product category and segment. Identify opportunities for cross-selling, upselling, and product diversification to maximize sales and profitability, particularly in the Technology, Office supplies, and Furniture categories.

* Explore ways to enhance the customer experience and strengthen customer loyalty across all segments, with a particular focus on the Consumer segment, which has the highest sales. Implement personalized marketing initiatives, loyalty programs, and customer retention strategies to drive repeat business and increase customer lifetime value.

# Sales-Quantity-and-Profit-Analysis-Dashboard
### Overview : 
This Tableau dashboard provides real-time insights into the sales performance of a computer hardware business facing challenges in a dynamically changing market. The dashboard covers various key metrics, allowing users to analyze revenue, sales quantity, profit, and other crucial aspects. You can view the dashboard created via this link: https://public.tableau.com/views/salesinsightstableaudashboard/Dashboard-SalesQuantityAnalysis?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
#### Profit analysis Dashboard : 
![image](https://github.com/ImaneMdn/Sales-Quantity-and-Profit-Analysis-Dashboard/assets/115882702/f36f4b7a-d2e5-4270-82af-7f8d7c8279e3)
![image](https://github.com/ImaneMdn/Sales-Quantity-and-Profit-Analysis-Dashboard/assets/115882702/02ee2162-2db6-466f-9b14-e66a798a997d)
#### Sales Quantity analysis Dashboard : 
![image](https://github.com/ImaneMdn/Sales-Quantity-and-Profit-Analysis-Dashboard/assets/115882702/ea608e75-a83a-42e3-984c-e50501353e63)
![image](https://github.com/ImaneMdn/Sales-Quantity-and-Profit-Analysis-Dashboard/assets/115882702/dac9e0fe-d629-481b-921e-40656aa48a62)

### Key Questions Addressed by the Dashboard :

1. What is the revenue distribution by markets?
2. How does sales quantity vary by market?
3. How has revenue evolved over the years?
4. Who are the top 5 customers contributing to sales?
5. What are the top 5 products driving sales?
6. What is the overall sales quantity and total revenue?
7. What is the profit distribution by markets?
8. How does profit margin vary across markets?
9. What is the trend in profit over time?
10. Who are the key customers impacting profitability?

### Data Analysis Using SQL : 

1. Show all customer records 

SELECT * FROM customers;

2. Show total number of customers

SELECT count(*) FROM customers;

3. Show transactions where currency is US dollars

SELECT * from sales.transactions where currency="USD";

4. Show transactions in 2020

SELECT* FROM sales.transactions ST
INNER JOIN sales.date SD ON ST.order_date= SD.date 
where SD.year=2020;

5. Show total revenue in year 2020 :
   
SELECT SUM(sales_amount) FROM sales.transactions ST
INNER JOIN sales.date SD ON ST.order_date= SD.date 
where SD.year=2020 and ST.currency="INR";

6. Show total revenue in year 2020, January Month :

SELECT SUM(transactions.sales_amount) FROM sales.transactions 
INNER JOIN sales.date ON transactions.order_date=date.date 
where date.year=2020 and date.month_name="January";

7. Show total revenue in year 2020 in Chennai :

SELECT sum(transactions.sales_amount) 
FROM sales.transactions
join sales.date ON date.date = transactions.order_date 
where date.year = 2020 and transactions.market_code = 'Mark001';

### Objective:
The primary objective is to provide stakeholders with a comprehensive view of the business's sales performance. By utilizing the dashboard, users can make data-driven decisions, identify market trends, and respond effectively to the evolving landscape.

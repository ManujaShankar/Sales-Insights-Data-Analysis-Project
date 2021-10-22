# Sales-Insights-Data-Analysis-Project
Finding insights of  Sales data using  MySql and Tableau
# Problem Statement:
The sales manager of AtliQ Hardware facing issues in tracking sales of his company. 

Hence, here we are finding the insights of salesdata  using tools like mysql and tableau and creating dashboard so one can make data driven decisions which helps to increase the sales of the Atliq company.

EDA by Mysql

Show all customer records

SELECT * FROM sales.customers;

Show total number of customers

SELECT count(*) FROM sales.customers;

Show transactions for Chennai market (market code for chennai is Mark001

SELECT * FROM sales.transactions where market_code='Mark001';

Show distrinct product codes that were sold in chennai

SELECT distinct product_code FROM sales.transactions where market_code='Mark001';

Show transactions where currency is US dollars

SELECT * from sales.transactions where currency="USD"

Show transactions in 2020 join by date table

SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where date.year=2020;

Show total revenue in year 2020,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN date ON sales.transactions.order_date=sales.date.date where date.year=2020 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";

Show total revenue in year 2020, January Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and and sales.date.month_name="January" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

Show total revenue in year 2020 in Chennai

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.market_code="Mark001";

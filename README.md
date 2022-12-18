# Sales-Insights-Data-Analysis-Project
**Purpose** : 
To unlock sales insights that are not visible before for sales team for decision support & automate them to reduced manual time spent in data gathering.

**End result** : 
An automated dashboard providing quick & latest sales insights in order to support data driven decision making.

**Success criteria** : 
1) Dashboards uncovering sales order insights with latest data available.
2) Sales team able to take better decisions & prove 10 % cost savings of total spend.
3) Sales Analysts stop data gathering manually inorder to save 20% of their business time and reinvest it value added activity.

**Data Analysis Using SQL**

***1) Show all customer records***

SELECT * FROM customers;

***2) Show total number of customers***

SELECT count(*) FROM customers;

***3) Show transactions for Chennai market (market code for chennai is Mark001*** 
 
SELECT * FROM transactions where market_code='Mark001';

***4) Show distrinct product codes that were sold in chennai*** 

SELECT distinct product_code FROM transactions where market_code='Mark001';

***5) Show transactions where currency is US dollars***

SELECT * from transactions where currency="USD"

***6) Show transactions in 2020 join by date table***

SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

***7) Show total revenue in year 2020***

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

***8) Show total revenue in year 2020, January Month***

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

***9) Show total revenue in year 2020 in Chennai***

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";

## Sales Insights Data Analysis Project

This project is based on a computer hardware business which is facing challenges in dynamically changing market. Sales director decides to invest in data analysis project and he would like to build Power BI dashboard that can give him real time sales insights.

## 1. Problem statements
AtliQ Hardware is a company which supplies computer hardware and peripherals to many of the clients. They have this client called Excel stores, normal stores across India and they supply all these equipment to them. Now AtliQ Hardware has a head office in Delhi India and then they have a lot of regional offices throughout the India now. 

      Sale director is  facing a lot of challenges so the challenge is this the market is growing dynamically and then he's facing issues in terms of tracking the sales in this dynamically growing market.

**Problems:**

-	***Conversations with local regional manager.***
If he wants to get insights in these three regions, he would call these people and on the phone. This was the sales last quarter and we are going to grow by this much in the next quarter. They're all verbal and there is this habit that all the managers have which is they try to paint a rosy picture.

-	***Seeing overall the sales by Excel files:***
 When he asked for numbers what these people will do, they will give him a lot of Excel files.  AtliQ hardware is a pretty big business and they have so many clients so that these Excel files that you get there are so many Excel files with so many rows. It is very frustrated he's like why are giving him the 69 Excel files and just tell him in simplistic terms:  how our business is doing, what are the biggest areas, where they need to focus.

## 2.	Data Discovery 
Sale Director realizes the pains and the possible solution. He will should live a meeting on how exactly we should do this data analytics project and after those people are in the room together they will brainstorm on project planning using AIMS grid now what is AIMS grid.


## 3. Data Analysis Using SQL

1. Show all customer records
```sql
SELECT * FROM customers;
```
2. Show total number of customers
```sql
SELECT count(*) FROM customers;`
```
3. Show transactions for Chennai market (market code for chennai is Mark001
```sql
SELECT * FROM transactions where market_code='Mark001';`
```
4. Show distrinct product codes that were sold in chennai
```sql
SELECT distinct product_code FROM transactions where market_code='Mark001';`
```
5. Show transactions where currency is US dollars
```sql
SELECT * from transactions where currency="USD"`
```
6. Show transactions in 2020 join by date table
```sql
SELECT transactions.*, date.* FROM transactions 
INNER JOIN date
 ON transactions.order_date=date.date where date.year=2020;`
```
7. Show total revenue in year 2020,
 ```sql
SELECT SUM(transactions.sales_amount) FROM transactions
 INNER JOIN date ON transactions.order_date=date.date 
 where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";
```

8. Show total revenue in year 2020, January Month,
 ```sql
 SELECT SUM(transactions.sales_amount) 
    FROM transactions
 INNER JOIN date 
 ON transactions.order_date =date.date
 where date.year=2020 and and date.month_name="January" 
 and (transactions.currency="INR\r" or transactions.currency="USD\r");```
```

9.  Show total revenue in year 2020 in Chennai
```sql
 SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";
```
## 4.	Data Cleaning & ETL  
I perform ETL and data cleaning operations to make it ready before build dashboard in Power BI.

## 5. Power BI Dashboard





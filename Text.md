## Sales Insights Data Analysis Project

### Instructions to setup mysql on your local computer

1. Follow Youtube any  video to install mysql/ Power BI on your local computer/Laptop.


Data Analysis Using Power BI :-


1. Formula to create Norm Sales_amount column: 

= Table.AddColumn(#"Filtered Rows", "Norm Sales_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount])





1. SQL database  Db_master.sql file above, Download `Db_master.sql` file for Data Analysis Using SQL

1. Show all customer Records

    `SELECT * FROM customers;`

2. Show total number of customers

    `SELECT count(*) FROM customers;

3. Show transactions for Mumbai market (market code for chennai is Mark002

    SELECT * FROM transactions where market_code='Mark002';`

4. Show distrinct product codes that were sold in Mumbai:

    SELECT distinct product_code FROM transactions where market_code='Mark002';

5. Show transactions where currency is US dollars :

    SELECT * from transactions where currency="USD";

6. Show transactions in 2020 join by date table

    SELECT transactions.*, date.* FROM transactions INNER JOIN date ON order_date=date.date where date.year=2020;

7. Show total revenue in year 2019,

    SELECT SUM(sales_amount) FROM transactions INNER JOIN date ON order_date=date.date where date.year=2019 and currency="INR\r" or currency="USD\r";
	
8. Show total revenue in year 2020, February Month,

    SELECT SUM(sales_amount) FROM transactions INNER JOIN date ON order_date=date.date where year=2020 and  month_name="February" and (currency="INR\r" or currency="USD\r");


9. Show total revenue in year 2019 in Mumbai :-

   SELECT SUM(sales_amount) FROM transactions INNER JOIN date ON order_date=date.date where date.year=2019 and market_code="Mark002";
      




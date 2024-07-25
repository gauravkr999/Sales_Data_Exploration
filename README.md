# Sales_data_exploration

# 1. Show all customer records

    SELECT * 
    FROM sales.customers;

# 2. Show total number of customers

    SELECT count(*) 
    FROM sales.customers;

# 3. Show transactions for Chennai market (market code for chennai is Mark001

    SELECT * 
    FROM sales.transactions 
    where market_code='Mark001';

# 4. Show distrinct product codes that were sold in chennai

    SELECT 
    distinct product_code 
    FROM sales.transactions 
    where market_code='Mark001';

# 5. Show transactions where currency is US dollars

    SELECT * 
    from sales.transactions 
    where currency="USD";

# 6. Show transactions in 2020 join by date table

    SELECT sales.transactions.*, sales.date.* FROM sales.transactions 
    INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date 
    where sales.date.year=2020;

# 7. Show total revenue in year 2020,

    SELECT SUM(sales.transactions.sales_amount) 
    FROM sales.transactions 
    INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date 
    where sales.date.year=2020;

# 8 Show total revenue in year 2020 in Chennai

    SELECT SUM(sales.transactions.sales_amount) 
    FROM sales.transactions 
    INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date 
    where sales.date.year=2020 and sales.transactions.market_code="Mark001";

# Exploring data

In this part of the OSEMN framework my goal was to explore the data for interesting patterns and statistics.

For exploring I used:
* Google sheets Pivot Tables
* Google sheets SQL queries
* Python/Pandas/Seaborn

The Notebook with calculations, stats and plots 👉🏻 [exploring.ipynb](exploring.ipynb)

<details>
  <summary>Exploring screensots</summary><br>

  All screenshots are here 👉🏻 [screenshots](https://github.com/dvstr/edu-for-git/tree/main/DA-Spreadsheets-and-SQL/screenshots)

  ![describe_columns](https://github.com/dvstr/edu-for-git/blob/main/DA-Spreadsheets-and-SQL/screenshots/describe_columns.jpg)
  
  ![category_sales_by_month_bar](https://github.com/dvstr/edu-for-git/blob/main/DA-Spreadsheets-and-SQL/screenshots/category_sales_by_month_bar.png)

  ![orders_per_customer](https://github.com/dvstr/edu-for-git/blob/main/DA-Spreadsheets-and-SQL/screenshots/orders_per_customer.png)

  ![orders_and_income_by_month](https://github.com/dvstr/edu-for-git/blob/main/DA-Spreadsheets-and-SQL/screenshots/orders_and_income_by_month.png)

  ![popularity_of_category_by_line](https://github.com/dvstr/edu-for-git/blob/main/DA-Spreadsheets-and-SQL/screenshots/popularity_of_category_by_line.png)

  ![top_products_by_line](https://github.com/dvstr/edu-for-git/blob/main/DA-Spreadsheets-and-SQL/screenshots/top_products_by_line.png)
</details><br>

While exploring, I calculated some common things:
* Totals (SUM)
* Averages and medians (AVERAGE and MEDIAN)
* Maximum and minimum values (MAX and MIN)

I added a new Total_Prise column and defined next things:
* Distribution of orders per customer
* Total number of orders by month
* Total revenue by month
* Top of all products by quantity sold
* Top of all products by revenue
* Top products by product line

Also, I made some comparsions:
* Total number of sold products in each category by month
* Category comparison by number of orders
* Category comparison by revenue
* Product line comparsions by number of orders
* Product line comparsions by revenue

## SQL query examples I used

Top 10 products by quantity sold with revenue
`=QUERY('transactions-pet_store-small_scrubbed'!A:L, "select D, sum(H), sum(L) group by D order by sum(H) desc limit 10")`

Top 10 products by revenue
`=QUERY('transactions-pet_store-small_scrubbed'!A:L, "select D, sum(H), sum(L) group by D order by sum(L) desc limit 10")`

Total number of sold products and total revenue by month
`=QUERY('transactions-pet_store-small_scrubbed'!A:L, "select K, sum(H), sum(L) group by K")`

Average price by category
`=QUERY('transactions-pet_store-small_scrubbed'!A:L, "select I, avg(F) group by I")`

Total revenue by category
`=QUERY('transactions-pet_store-small_scrubbed'!A:L, "select I, sum(L) group by I")`

Information of the orders where customer bought only one item
`=QUERY('transactions-pet_store-small_scrubbed'!A:L, "select B, K, D, H, I, J, L where H = 1 order by K asc")`

In fact, I didn't find any interesting patterns due to insufficient data. But I had good Python and querie practice.

I saved the result in the [notebook with calculations, stats and plots](exploring.ipynb).

👈🏻 [back to README](README.md) | [next to Visualizing](visualizing.md) 👉🏻
---
title: Reading and Querying CSV Files with DuckDB
date: 2025-02-07 00:00:00 -0500
categories: [Database, DuckDB]
tags: [duckdb, sql, data-analysis, python, pycharm, csv]     # TAG names should be lowercase
---

# Working with CSV Files in DuckDB

In this post, I'll read and query CSV files using DuckDB's powerful capabilities.

## Prerequisites
### Installing Pandas
With my project open, I opened the terminal in PyCharm and installed Pandas:
```bash
pip install duckdb
```
### DuckDB Code
```python
import duckdb
import pandas as pd
```

## Reading CSV Files
# Method 1: Direct SQL Query
```python
sales_data = duckdb.sql("""
    SELECT * 
    FROM read_csv('data\\cleaned_data.csv')
""")

print(sales_data.fetchdf().head())
```
# Method 2: Creating a Table
```python
duckdb.sql("""
    CREATE TABLE sales AS 
    SELECT * FROM read_csv('data\\cleaned_data.csv')
""")

 #Query the table
 result = duckdb.sql("""
    SELECT product_id, SUM(quantity) as items_sold
    FROM sales
    GROUP BY product_id
    ORDER BY items_sold DESC
""").fetchdf()
print(result)

pd.options.display.float_format = '{:,.0f}'.format
result2 = duckdb.sql("""
    SELECT category, SUM(total_amount) as total_sales
    FROM sales
    GROUP BY category
    ORDER BY total_sales DESC
""").fetchdf()
print(result2)
```

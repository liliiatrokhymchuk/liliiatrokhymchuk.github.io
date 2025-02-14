---
title: Getting Started with DuckDB
date: 2025-02-06 00:00:00 -0500
categories: [Database, DuckDB]
tags: [duckdb, sql, data-analysis, python, pycharm, setup]     # TAG names should be lowercase
---
# My First Steps with DuckDB

After deciding to dive into data analysis, I chose DuckDB as one of the tools to learn. In this post, I'll walk through my initial setup process in PyCharm.

## Setting Up the Development Environment

### Creating New Project
In PyCharm:
1. Click "Create New Project"
2. Select a location for the project
3. Create a new virtual environment

### Installing DuckDB
With my project open, I opened the terminal in PyCharm and installed DuckDB:
```bash
pip install duckdb
```
### First DuckDB Code
Here's how I got started:

```python
import duckdb

# Create a connection (this will create a new database file if it doesn't exist)
con = duckdb.connect('my_first_db.duckdb')

# Create a simple table
con.sql("CREATE TABLE test (i INTEGER)")

#Insert values
con.sql("INSERT INTO test VALUES (42), (100), (200)")

# Query the table and filter results
result = con.sql("SELECT * FROM test WHERE i > 50").show()

#Close the connection
con.close()
```

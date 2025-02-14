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

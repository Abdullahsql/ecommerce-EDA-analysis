# E-Commerce Order Data — Exploratory Data Analysis (EDA)

## Problem Statement
This project analyzes 1,200 cleaned e-commerce order records to uncover patterns in order value, identify outliers, and map relationships between key variables. The goal is to move beyond surface-level averages and understand what's actually driving order behavior, informing pricing, marketing, and inventory decisions.

## Methodology
- Dataset: 1,200 orders across 14 fields (Product, Quantity, UnitPrice, TotalPrice, OrderStatus, etc.), previously cleaned in Project 1
- Tools: Python (pandas, matplotlib, seaborn) in Google Colab
- Approach: descriptive statistics, distribution analysis, IQR-based outlier detection, correlation analysis

## Key Findings

**1. Order value is right-skewed — the average overstates the typical order**
Mean order value is $1,053.97, but the median is $823.62. A cluster of high-value orders pulls the average up by roughly 28%. For planning purposes, median is the more reliable figure for "typical" customer spend.

**2. Eight high-value outliers, all legitimate**
Using the IQR method (upper bound $3,330.41), 8 orders were flagged as outliers, ranging from $3,334 to $3,456. Each one checks out mathematically (max quantity of 5 units

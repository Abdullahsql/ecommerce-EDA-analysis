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
Using the IQR method (upper bound $3,330.41), 8 orders were flagged as outliers, ranging from $3,334 to $3,456. Each one checks out mathematically (max quantity of 5 units × high-priced items like Laptops, Printers, Monitors). These were kept in the dataset as real high-value transactions, not data errors.

**3. Nearly 40% of high-value outliers didn't convert**
Of the 8 outlier orders, 3 were Cancelled or Returned rather than Delivered/Shipped. The business's biggest-ticket transactions are disproportionately at risk of falling through.

**4. Total price is driven almost entirely by unit price and quantity — no surprise there**
UnitPrice correlates with TotalPrice at 0.72, Quantity at 0.62. Expected, since TotalPrice is calculated from both.

**5. No relationship between price and quantity purchased**
Correlation between UnitPrice and Quantity is 0.01, essentially zero. Customers aren't buying more when items are cheaper or less when they're expensive. Bulk-discount or price-sensitivity strategies aren't likely to move quantity per order based on this data.

## Recommendations
- Use median order value ($824), not mean, when setting sales targets or benchmarks — the mean is misleading here
- Investigate the cancellation/return pattern on high-value orders specifically; standard retention tactics may not be addressing why big orders fall through
- Since price doesn't influence quantity purchased, focus growth levers elsewhere (e.g. cross-sell, bundling) rather than price-based promotions to drive volume

## Files
- `eda_notebook.ipynb` — full analysis code
- `correlation_heatmap.png` — visual correlation matrix

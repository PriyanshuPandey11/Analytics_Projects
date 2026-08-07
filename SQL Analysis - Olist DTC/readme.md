# Olist Brazilian E-Commerce Analysis

An end-to-end business analysis of the Olist Brazilian e-commerce dataset — from raw relational data to a five-question SQL analysis, an Excel MIS dashboard, and a one-page executive insight report.

## Overview

Olist is a Brazilian e-commerce marketplace that connects small businesses to major online sales channels. This project works through their public order dataset (2016–2018, ~100k orders across 9 relational tables) to answer five core business questions — revenue trend, top categories, cancellations, customer value segmentation, and delivery performance — and turns the results into an executive-ready findings and recommendations report.

Tools used: MySQL Workbench (querying) · Excel (aggregation, KPIs, and charting)

- Repository Structure

```
├── Olist Raw Data/
├── Readme.md                                  # About the Project
├── olist_analysis.sql                      # all 5 analysis queries (MySQL)
├── Olist_DTC Analysis.xlsx                 # Raw_Summary + Calculations + MIS_Dashboard
└── Olist Brazillian E-Commerce Report.pdf  # 1-page findings & recommendations
```

## Analysis

Five queries in [`olist_analysis.sql`](olist_analysis.sql), run against `delivered` orders unless stated otherwise:

1. Monthly Revenue Trend — total orders and revenue by month
2. Top 10 Product Categories by Revenue — items sold and revenue per category
3. Cancellation Rate by Month — cancelled orders as a share of total orders, by month
4. Customer Segmentation by Spend — customers split into High / Mid / Low spend tiers using `NTILE(10)` deciles
5. Average Delivery Time by State — estimated delivery window by customer state

Query outputs feed into `Raw_Summary` in the Excel workbook, which rolls up into headline KPIs on the `Calculations` sheet and the `MIS_Dashboard`.

## Key Findings

1. Revenue concentration risk — the top 3 categories generate 41% of total revenue but only 37% of units sold, meaning revenue is more concentrated than volume.
2. Rising cancellations — the cancellation rate trended upward from 2017 into 2018, peaking in September 2018 at 84 cancellations — more than 3x the average month.
3. Delivery time gap — customers in AP wait ~46 days on average vs. ~19 days in SP, a 27-day gap likely to affect repeat purchase rate.

## Recommendations

1. Diversify revenue beyond the top 3 categories — grow two adjacent categories without sacrificing existing top-line revenue.
2. Target a maximum 30-day delivery window in slower states to improve repeat purchase rate.

## Data Source & Attribution

Dataset: [Olist Store — Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle, provided by Olist). Data is anonymized order-level data from real orders placed on the Olist marketplace between 2016 and 2018.

## Author
Priyanshu Pandey


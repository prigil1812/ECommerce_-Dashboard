

# E-Commerce Analytics Pipeline

## Overview

An end-to-end data analytics pipeline built using the Olist Brazilian E-Commerce public dataset (9 tables, 1M+ rows). This project covers the complete analytics workflow, including relational database design, SQL data modelling, Python-based data loading and cleaning, and interactive Power BI dashboard development.

Built independently, without following a tutorial.

## Tools Used

- **MySQL:** Database design, ETL, SQL views, data analysis and indexing
- **Python:** pandas, SQLAlchemy, data loading and cleaning
- **Power BI:** Interactive dashboard development, KPI reporting and visualisation

## Process

### 1. Data Loading

- Loaded 9 raw CSV tables into MySQL: customers, orders, order items, payments, reviews, products, sellers, category translations and geolocation.
- Used Python, pandas and SQLAlchemy to handle data loading and preparation.
- Implemented chunked loading to handle the large geolocation table efficiently.

### 2. Data Modelling and SQL Analysis

Developed SQL views for four core analytical areas:

**RFM Customer Segmentation**
- Analysed customer recency, frequency and monetary value.
- Used `NTILE(5)` window functions to generate 1–5 scores for each RFM component.
- Applied `CASE WHEN` logic to classify customers into behavioral segments, including Champions, Loyal Customers, New Customers, Potential Loyalists, At Risk, Cant Lose Them and Needs Attention.

**Cohort Retention Analysis**
- Defined customer cohorts using each customer's first-ever purchase month, rather than signup date, which is not available in the dataset.
- Used `customer_unique_id` to identify customers consistently across multiple orders.
- Tracked monthly customer activity by first-purchase cohort and customer state.
- Calculated the number of months elapsed between the cohort month and subsequent order months.

**Delivery Performance**
- Analysed late delivery rates and delay severity across customer states and product categories.
- Identified geographic and category-level patterns associated with delivery delays.

**Seller Scorecarding**
- Evaluated seller performance based on revenue and delivery reliability.
- Classified sellers into performance tiers to compare revenue contribution and delivery outcomes.

### 3. Dashboard Development

Developed a four-page interactive Power BI dashboard with coordinated styling, KPI cards and cross-filterable visuals.

| Dashboard Page | Key Analysis |
|---|---|
| Customer Segments | RFM segmentation

## Screenshots
Page1<img width="940" height="524" alt="page1-Customer_Segment" src="https://github.com/user-attachments/assets/eeb3e6ba-6c02-4013-ab3c-95397a5fd4db" />
Page2<img width="934" height="539" alt="page2-Retention" src="https://github.com/user-attachments/assets/b9ba8955-d26a-4a1c-9c1a-cd91b29de8d5" />
Page3<img width="936" height="533" alt="page3-Delivery" src="https://github.com/user-attachments/assets/57b5ed34-baed-4e22-833d-aac004405ec8" />
Page4<img width="927" height="548" alt="page4-seller_analysis" src="https://github.com/user-attachments/assets/2fc8a2f9-cc48-4215-92cb-87f7e22b2471" />

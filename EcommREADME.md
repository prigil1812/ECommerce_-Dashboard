# E-Commerce Analytics Pipeline

## Overview
An end-to-end data analytics pipeline built on the Olist Brazilian E-Commerce public dataset (9 tables, 1M+ rows). This project covers the full analytics workflow: relational database design, SQL data modeling, and interactive dashboard development — built independently, not from a tutorial.

## Tools Used
- MySQL (database design, ETL, SQL views)
- Python (pandas, SQLAlchemy — data loading/cleaning)
- Power BI (dashboard development)

## Process
1. **Data Loading**: Loaded 9 raw CSV tables (customers, orders, order items, payments, reviews, products, sellers, category translations, and geolocation — 1M+ rows) into MySQL using Python, including chunked loading to handle the large geolocation table
2. **Data Modeling**: Built SQL views for four core analyses:
   - **RFM Customer Segmentation** — recency/frequency/monetary scoring using NTILE window functions, segmenting customers into 7 behavioral groups (Champions, At Risk, Loyal Customers, etc.)
   - **Cohort Retention Analysis** — monthly cohort tracking by signup month and region
   - **Delivery Performance** — late delivery rates and delay severity by state and product category
   - **Seller Scorecarding** — seller performance tiering based on revenue and delivery reliability
3. **Dashboard Development**: Built a 4-page interactive Power BI dashboard (Customer Segments, Retention, Delivery Performance, Seller Scorecard) with a coordinated color system, KPI cards, and cross-filterable visuals

## Key Findings
- **Customer retention**: Only a **1.99% repeat-purchase rate** — indicating an acquisition-heavy rather than retention-heavy marketplace
- **Value concentration**: A small "Champions" segment (1,067 customers, ~1% of the base) generates disproportionately high revenue per customer
- **Delivery lateness has two distinct root causes**: geography (certain states like AL and MA had significantly higher late rates) and product category (electronics-adjacent categories like audio and tablets had the highest late %) — independent problems requiring different fixes
- **Seller reliability isn't tied to revenue scale**: top-revenue sellers were generally well-controlled on delivery, while reliability risk concentrated more among smaller-volume sellers

## Screenshots
Page1<img width="940" height="524" alt="page1-Customer_Segment" src="https://github.com/user-attachments/assets/eeb3e6ba-6c02-4013-ab3c-95397a5fd4db" />
Page2<img width="934" height="539" alt="page2-Retention" src="https://github.com/user-attachments/assets/b9ba8955-d26a-4a1c-9c1a-cd91b29de8d5" />
Page3<img width="936" height="533" alt="page3-Delivery" src="https://github.com/user-attachments/assets/57b5ed34-baed-4e22-833d-aac004405ec8" />
Page4<img width="927" height="548" alt="page4-seller_analysis" src="https://github.com/user-attachments/assets/2fc8a2f9-cc48-4215-92cb-87f7e22b2471" />

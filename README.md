1. Business Problem
Modern investors, analysts, and financial teams struggle to evaluate and compare company performance across multiple organizations because financial, leadership, and historical data is scattered across different external APIs and systems. 
Core Problem Statement:
Investors lack a unified, analytics-ready platform to evaluate multiple company performance, financial health, and risk due to fragmented and inconsistent data sources.
2. Business Goals
The platform aims to enable:
Identification of high-growth investment opportunities
Detection of financially risky or underperforming companies
Tracking company leadership (directors and officers)
Monitoring financial performance over time
Industry-wise comparison of companies
3. Business Questions
The system is designed to answer:
Which companies show consistent revenue and profit growth?
Which companies are financially declining or high-risk?
How do leadership changes impact company performance?
Which industries generate the highest returns?
How frequently do companies change structure or leadership?

4. KPIs (Key Performance Indicators)
Revenue Growth Rate (%)
Profit Trends over time
Company Risk Score (derived metric)
Active vs Inactive Company Ratio
Director Influence Score (based on company success association)
Industry Performance Index
Advanced KPIs we can add 
Risk score (composite metric)
Volatility score
Director influence score
Industry benchmark comparison
Financial health score


5. Data Sources
Data is collected from multiple external APIs:
Companies house API (basic details, industry, status)
Companies house_Officers / Directors API (leadership data)
Yfinancial Data API (revenue, profit, assets)
Companies house _Company History / Filing API (events, changes over time)

6. Data Product Overview
Data Product Name:
Investment Intelligence Platform
Domain:
Financial Analytics / Investment Intelligence

7. Data Contract
Ownership
Business Owner: Investment / Strategy Team/ financial analyst
Technical Owner: Data Engineering Team
Data Steward: Data Governance Team
Source System
Type: REST APIs
Ingestion: Batch + Incremental

8. Data Architecture Layers
Bronze Layer (Raw Data)
bronze_companies
bronze_directors
bronze_financials
bronze_company_history
bronze_stock_prices
bronze_company_news
bronze_financial_ratios
bronze_industry_metrics
bronze_risk_events 
Silver Layer (Cleaned Data)

Gold Layer (Analytics Ready)


9. Data Model Design
9.1 Conceptual Model


9.2 Logical Model

10. Star Schema
       11. Data Pipeline Design
Step 1: Ingestion (Bronze)
Pull data from APIs
Store raw JSON responses
Step 2: Transformation (Silver)
Flatten nested structures
Normalize schemas
Clean missing values
Step 3: Modeling (Gold)
Build dimensions
Build fact table
Apply business rules

12. Data Quality Rules
company_id must not be null
financial values must be >= 0
revenue = valid numeric field
all foreign keys must exist in dimension tables
duplicate company records must be removed

13. Data Refresh Strategy
Frequency: Daily batch processing
Latency: T+1 (data available next day)
Pipeline Orchestration: Databricks / ADF

14. Security & Governance
Role-based access control (RBAC)
Column-level masking for sensitive data
Encryption at rest and in transit
Financial data classified as confidential

15. BI & Consumption Layer
Tools:
Power BI
Tableau
SQL Analytics
Use Cases:
Investment dashboards
Risk analysis reports
Company performance tracking
Industry benchmarking
16. Final Outcome
The platform delivers a unified, analytics-ready investment dataset that enables stakeholders to:
Evaluate company performance
Identify investment opportunities
Detect financial risks
Analyze leadership impact on business growth

17. Summary
This project transforms fragmented API data into a structured Investment Intelligence Platform using a modern data warehouse architecture (Bronze, Silver, Gold) and star schema modeling to support BI and investment decision-making.

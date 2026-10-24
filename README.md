# E-Commerce Customer Intelligence & Risk Analytics

**Cross-Platform Data Integration | Customer Segmentation | Retention Risk | Business Intelligence**

An end-to-end analytics project developed during a real-world e-commerce initiative in China, focused on turning fragmented transaction data into useful business insights.

The project connects customer behavior, product performance, and transaction history to help businesses better understand their customers, identify potential risks, and make more informed decisions.

**The goal:** Turn scattered data into a clearer picture of the business — and make that information useful.

---

## Project Overview

Working with data from multiple e-commerce platforms comes with a challenge: different formats, inconsistent customer identifiers, incomplete records, and no single view of business performance.

This project explored how to bring those pieces together into a unified analytics system.

Three key business questions guided the work:

- **Customer Value:** Who are our most valuable customers, and what drives their purchasing behavior?
- **Retention & Risk:** Which customers may be disengaging, and which products show unusually high refund rates?
- **Business Performance:** How can transaction and product data support better marketing, retention, and product decisions?

## Dashboard Showcase

The project includes interactive Power BI reports and a web-based analytics dashboard.

*Original dashboards were developed in Chinese during the internship. Selected views are presented below.*

### 1. Customer Segmentation — RFM Analysis

![Customer Segmentation](dashboards/01.%20customer_segmentation.png)

Used Recency, Frequency, and Monetary metrics to analyze purchasing behavior and organize customers into actionable segments.

The segmentation supports customer prioritization, retention planning, and differentiated engagement strategies.

### 2. Customer Profile & Purchase Behavior

![Customer Profile](dashboards/02.%20customer_profile.png)

Explored customer-level spending patterns, purchase frequency, product preferences, and purchasing history through interactive Power BI views.

### 3. Retention Risk Monitoring

![Retention Risk](dashboards/03.%20retention_risk.png)

Developed rule-based monitoring views to identify potentially inactive high-value customers and products with elevated refund rates.

These indicators support business risk review and retention prioritization rather than statistical predictions of churn.

### 4. Product Performance & ABC Analysis

![Product Analytics](dashboards/04.%20product_analytics.png)

Analyzed product performance across revenue contribution, transaction volume, customer engagement, and refunds.

ABC classification helped distinguish key revenue contributors from supporting and long-tail products.

### 5. Product Selection & Recommendations

![Product Recommendations](dashboards/05.%20product_recommendations.png)

Combined purchasing activity, revenue contribution, and refund indicators to support product selection and review decisions.

### 6. Geographic Business Insights

![Geographic Analytics](dashboards/06.%20geographic_analytics.png)

Examined geographic distributions of customer activity and sales performance across provinces and cities.

### 7. Interactive Analytics Interface

![Web Dashboard](dashboards/07.%20web_dashboard.png)

Developed a web-based analytical interface with multiple business modules, interactive filtering, drill-down views, and risk monitoring features.

The original interactive application is not publicly hosted because it contains embedded business data.

---

## Data Architecture & Integration

A significant part of this project involved organizing fragmented data into a consistent analytical framework.

The original technical documentation is preserved in Chinese, reflecting the project's development environment.

### 1. End-to-End Data Architecture

![System Architecture](architecture/01.%20system_architecture.png)

The overall design connects source data, standardization, dataset integration, feature engineering, business metrics, and visualization.

### 2. Unified Data Model

![Data Model](architecture/02.%20data_model.png)

The analytical framework centers on three core datasets:

- **Transactions:** Orders, payments, refunds, and purchasing activity.
- **Customers:** Customer-level attributes, purchasing history, and behavioral metrics.
- **Products:** Product identifiers, categories, and performance indicators.

The objective was to make information from different platforms consistent enough for cross-platform analysis.

### 3. Cross-Platform Customer Matching

![Entity Matching](architecture/03.%20entity_matching.png)

One of the main data challenges was identifying customers across platforms with inconsistent or incomplete identifiers.

The documented entity resolution framework uses multiple matching levels, confidence considerations, and manual review for ambiguous records.

The diagram includes design-stage matching rules, not all of which are independently verifiable from the surviving project files.

---

## Analytical Methods

| Area | Methods & Concepts |
|---|---|
| Data Integration | Field mapping, data standardization, entity resolution |
| Customer Analytics | RFM segmentation, purchasing patterns, customer value |
| Retention Risk | Purchase recency, inactivity signals, rule-based alerts |
| Product Analytics | ABC classification, revenue contribution, refund analysis |
| Business Intelligence | Power BI, interactive dashboards, KPI reporting |
| Decision Support | Customer prioritization, product review, retention strategies |

## Business Applications

The project was designed to support several practical business decisions:

**Customer Retention:** Prioritize high-value customers showing signs of inactivity.

**Marketing Strategy:** Develop more targeted engagement approaches based on customer segments and purchasing behavior.

**Product Optimization:** Identify high-performing products and flag products with elevated refund indicators for further investigation.

**Operational Visibility:** Provide a consistent view of customer activity, product performance, and regional transaction trends.

These are analytical applications and recommended decision pathways; they should not be interpreted as independently verified improvements in revenue or retention.

---

## Project Availability & Data Privacy

This repository is a portfolio case study based on work carried out during an internship in China.

The original project involved real business transactions, customer information, and internal operational data. To respect confidentiality and data privacy, the underlying datasets, customer-level records, and certain internal project materials are not publicly available.

The original development environment has since been decommissioned, and some historical processing scripts and intermediate files are no longer available.

This repository therefore focuses on selected architecture documentation, analytical methods, and dashboard screenshots rather than providing a fully reproducible application.

Additional documentation or privacy-safe materials may be added as they become available.

---

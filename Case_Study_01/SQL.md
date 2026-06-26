# SQL Documentation

## Overview

This document describes the SQL queries used to transform raw Google Analytics 4 event data into datasets for executive dashboards.

All queries were written in Google BigQuery using the Google Merchandise Store (GA4 Public Sample Dataset).

The SQL workflow focuses on three primary objectives:

- Executive KPI reporting
- Marketing performance analysis
- Funnel and conversion analysis

---

# SQL Architecture

```text
GA4 Event Data
        │
        ▼
SQL Transformation
        │
        ▼
Business Metrics
        │
        ▼
Dashboard Visualizations
```

---

# Query Structure

The project consists of twelve SQL queries organized by business function.

| Query | Purpose |
|--------|---------|
| 01 | Executive KPIs |
| 02 | Revenue Trend |
| 03 | Users Trend |
| 04 | Users by Traffic Source |
| 05 | Revenue by Traffic Source |
| 06 | Users by Device |
| 07 | Purchases by Device |
| 08 | Marketing Channel Performance |
| 09 | Revenue vs Users |
| 10 | Funnel Overview |
| 11 | Funnel KPIs |
| 12 | Funnel Conversion Rates |

---

# Executive Dashboard Queries

## 01 — Executive KPIs

### Purpose

Generate the primary KPI cards displayed on the Executive Overview dashboard.

### Metrics

- Revenue
- Purchases
- Users
- Conversion Rate
- Average Order Value
- Revenue per Visitor

### Business Value

Provides executives with an immediate summary of business performance.

---

## 02 — Revenue Trend

### Purpose

Calculate daily revenue over time.

### Output

- Date
- Revenue

### Business Value

Supports trend analysis and identifies growth patterns.

---

## 03 — Users Trend

### Purpose

Calculate daily active users.

### Output

- Date
- Users

### Business Value

Measures acquisition performance over time.

---

# Marketing Dashboard Queries

## 04 — Users by Traffic Source

### Purpose

Aggregate users by acquisition channel.

### Output

- Traffic Source
- Users

### Business Value

Identifies which marketing channels generate the highest traffic.

---

## 05 — Revenue by Traffic Source

### Purpose

Aggregate revenue by acquisition channel.

### Output

- Traffic Source
- Revenue

### Business Value

Measures revenue contribution by marketing channel.

---

## 06 — Users by Device

### Purpose

Calculate user distribution across device categories.

### Output

- Device
- Users

### Business Value

Provides insight into customer browsing behavior.

---

## 07 — Purchases by Device

### Purpose

Measure completed purchases by device.

### Output

- Device
- Purchases

### Business Value

Evaluates purchasing behavior across platforms.

---

## 08 — Marketing Channel Performance

### Purpose

Combine user acquisition, revenue, and conversion metrics into a single marketing performance dataset.

### Output

- Users
- Purchases
- Revenue
- Conversion Rate
- Revenue per Visitor

### Business Value

Supports channel performance evaluation and budget allocation.

---

## 09 — Revenue vs Users

### Purpose

Compare acquisition volume with revenue generation.

### Output

- Users
- Revenue

### Business Value

Helps identify high-value and low-value traffic sources.

---

# Funnel Analysis Queries

## 10 — Funnel Overview

### Purpose

Measure customer progression through the purchasing journey.

### Funnel Stages

- Session Start
- Product View
- Add to Cart
- Begin Checkout
- Purchase

---

## 11 — Funnel KPIs

### Purpose

Generate KPI cards for funnel performance.

### Metrics

- Sessions
- Product Views
- Add to Cart
- Checkout
- Purchases

---

## 12 — Funnel Conversion Rates

### Purpose

Calculate conversion rates between funnel stages.

### Metrics

- Add-to-Cart Rate
- Checkout Rate
- Purchase Rate

### Business Value

Identifies customer journey bottlenecks and optimization opportunities.

---

# SQL Design Principles

The SQL queries were designed using the following principles:

- Readability
- Reusability
- Performance
- Business-focused metrics
- Modular query design

Where appropriate, Common Table Expressions (CTEs) were used to improve readability and simplify transformations.

---

# Data Modeling Approach

Rather than querying raw GA4 event data directly in dashboards, SQL transformations were used to create reporting-ready datasets.

Benefits include:

- Improved dashboard performance
- Consistent business metrics
- Easier maintenance
- Simplified visualization development

---

# Future Improvements

Future versions of this project may include:

- Parameterized SQL
- Incremental models
- Scheduled queries
- BigQuery Views
- Data quality validation
- Automated reporting tables

---

# Summary

This SQL layer serves as the foundation of the reporting solution, transforming raw event-level data into business-ready datasets that support executive reporting, marketing analytics, and customer funnel analysis.


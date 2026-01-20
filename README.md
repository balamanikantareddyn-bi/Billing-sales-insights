# Billing-sales-insights
An end-to-end BI solution designed for a real-world client to digitize manual ledgers. Built using MySQL for data warehousing and Power BI for visualization. Features advanced logic for Customer Retention Analysis, Inventory Forecasting, and Cash Flow Optimization.

> **Note:** Due to the proprietary nature of the client's data, this repository contains **synthetic/dummy data** that mirrors the structure and logic of the original production environment.

## 📖 Overview
This project is a comprehensive **Business Intelligence (BI) Solution** developed for a freelance client to transform manual sales ledgers into actionable data insights. 

The dashboard serves two primary business goals:
1.  **Supply Chain Optimization:** Predicting stock requirements based on client purchasing patterns.
2.  **Cash Flow Management:** Tracking payment lifecycles to reduce outstanding receivables.

## 🚀 Key Features

### 1. Customer Retention & Repeat Patterns 🔄
* **Logic:** Analyzes purchase frequency (Day/Week/Month) to identify "High-Value Recurring Clients."
* **Impact:** Enables the client to stock inventory specifically for repeat buyers before they even place an order.
* **Metric:** Cohort Analysis of Client Repurchase Rates.

### 2. Payment Trend Analysis 💰
* **Logic:** Tracks the delta between `Invoice Date`, `Due Date`, and `Actual Payment Date`.
* **Impact:** Identifies clients who consistently pay late, allowing for proactive follow-ups.
* **Visualization:** Cash Flow forecasting charts to predict incoming revenue for the next 30 days.

## 🛠️ Tech Stack & Architecture

* **Data Ingestion (ETL):** Python (Pandas) scripts to clean and normalize raw Excel/CSV ledgers.
* **Data Warehouse:** MySQL Relational Database (Normalized Schema).
* **Visualization:** Microsoft Power BI.
* **Data Transformation:** Power Query & DAX.

**Data Flow:**
`Raw Ledgers` ➔ `Python Cleaning Script` ➔ `MySQL Database` ➔ `Power BI ` ➔ `Dashboard`

## 🧮 Key DAX Measures Used

**1. Running Total Revenue:**
```dax
Total Revenue YTD = 
CALCULATE(
    SUM(Sales[Amount]),
    DATESYTD('DateTable'[Date])
)

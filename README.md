# Billing-sales-insights
An end-to-end BI solution designed for a real-world client to digitize manual ledgers. Built using MySQL for data warehousing and Power BI for visualization. Features advanced logic for Customer Retention Analysis, Inventory Forecasting, and Cash Flow Optimization.

# 📊 Enterprise Billing & Sales Intelligence Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=black)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success?style=for-the-badge)

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

### 3. Inventory Optimization 📦
* **Logic:** Correlates sales velocity with current stock levels.
* **Impact:** Reduced instances of stock-outs for high-demand items by **20%**.

## 🛠️ Tech Stack & Architecture

* **Data Ingestion (ETL):** Python (Pandas) scripts to clean and normalize raw Excel/CSV ledgers.
* **Data Warehouse:** MySQL Relational Database (Normalized Schema).
* **Visualization:** Microsoft Power BI.
* **Data Transformation:** Power Query & DAX.

**Data Flow:**
`Raw Ledgers` ➔ `Python Cleaning Script` ➔ `MySQL Database` ➔ `Power BI Gateway` ➔ `Dashboard`

## 📊 Dashboard Screenshots

*(Place your screenshots here. Pro Tip: Add 2-3 images showing the Overview, the Payment Trends view, and the Inventory view)*

![Dashboard Overview](link-to-your-image-here)
*Figure 1: Executive Overview showing Total Revenue, Outstanding Payments, and Top Selling Categories.*

## 🧮 Key DAX Measures Used

**1. Running Total Revenue:**
```dax
Total Revenue YTD = 
CALCULATE(
    SUM(Sales[Amount]),
    DATESYTD('DateTable'[Date])
)

# 📊 Sales Performance Dashboard | Power BI Project

## 📌 Project Overview
This Power BI project provides an interactive Sales Performance Dashboard for analyzing sales, customers, products, and returns. The report contains three pages:

1. **Dashboard Page**
2. **Customer Analysis Page**
3. **Product Analysis Page**

The dashboard helps users monitor KPIs, identify trends, analyze customer behavior, and evaluate product performance.

---

# 📂 Pages Overview

## 1️⃣ Dashboard Page

The main dashboard provides a high-level overview of business performance.

### KPIs
- Total Sales
- Total Orders
- Total Customers
- Total Returns
- Return Rate %

### Visualizations
- Monthly Sales Trend
- Sales by Subcategory
- Monthly Revenue
- Monthly Orders
- Monthly Returns
- Top 10 Products by Sales
- Trend Line for Sales Analysis

### Features
- Interactive filters
- Drill Up and Drill Down
- Conditional Formatting
- Trend Analysis
- KPI Cards

---

## 2️⃣ Customer Analysis Page

This page focuses on customer performance and segmentation.

### KPIs
- Total Customers
- Total Orders
- Average Order Value
- Return Rate %

### Visualizations
- Customer Sales Trend (Monthly)
- Customer Segment Distribution
- Top 10 Customers by Sales
- Customer Details Table
- Best Customer
- Highest Revenue Customer

### Features
- Customer segmentation analysis
- Top customer identification
- Interactive filtering
- Matrix table with conditional formatting

---

## 3️⃣ Product Analysis Page

This page analyzes product-level performance.

### KPIs
- Product Name
- Total Units Sold
- Total Sales
- Average Product Price

### Visualizations
- Units Sold Trend
- Profit Analysis by Date Hierarchy
- Dynamic Parameter Selection

### Features
- Drill Down hierarchy
- Trend line
- Dynamic parameter
- Product performance analysis

---

# 🗂 Data Model

The report follows a **Star Schema Model**.

## Fact Table

### Sales_Fact
Stores transactional sales data.

| Column |
|----------|
| SalesID |
| DateKey |
| ProductKey |
| CustomerID |
| RegionID |
| Quantity |
| SalesAmount |
| ReturnID |

---

## Dimension Tables

### Dim_Customer

| Primary Key |
|-------------|
| CustomerID |

Contains:
- Customer Name
- Segment
- Region

---

### Dim_Product

| Primary Key |
|-------------|
| ProductKey |

Contains:
- Product Name
- Category
- Subcategory
- Price

---

### Dim_Date

| Primary Key |
|-------------|
| DateKey |

Contains:
- Day
- Month
- Quarter
- Year

---

### Dim_Region

| Primary Key |
|-------------|
| RegionID |

Contains:
- Region Name
- Country
- State

---

# 🔑 Primary Key and Foreign Key

## Primary Key (PK)

A Primary Key uniquely identifies each record in a table.

Example:

### Dim_Customer

| CustomerID (PK) | Customer Name |
|----------------|---------------|
| C001 | Virginia Wolf |
| C002 | Kristina Cabrera |

Here **CustomerID** is the Primary Key because every value is unique.

---

## Foreign Key (FK)

A Foreign Key connects one table with another table.

Example:

### Sales_Fact

| SalesID | CustomerID (FK) | ProductKey (FK) |
|---------|----------------|----------------|
| S001 | C001 | P101 |
| S002 | C002 | P105 |

CustomerID and ProductKey are Foreign Keys because they reference dimension tables.

---

# 🔗 Relationships

| Table | Primary Key | Related Table | Foreign Key |
|---------|------------|---------------|-------------|
| Dim_Customer | CustomerID | Sales_Fact | CustomerID |
| Dim_Product | ProductKey | Sales_Fact | ProductKey |
| Dim_Date | DateKey | Sales_Fact | DateKey |
| Dim_Region | RegionID | Sales_Fact | RegionID |

Relationship Type:

- One-to-Many (1:*)



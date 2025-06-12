# ☕ Coffee Orders Analysis Dashboard 📊

This repository contains a data analysis and interactive Excel dashboard project built using coffee order data. The aim of this project is to extract insights about customer behaviour, sales trends, and product performance using Excel formulas and dashboarding tools.

---

## 📁 Project Structure

- **Raw Data**: Coffee order data stored in Excel worksheets  
- **Processed Data**: Cleaned and enriched using Excel formulas such as `XLOOKUP` and `INDEX-MATCH`  
- **Dashboard**: An interactive Excel dashboard displaying KPIs and visual insights  

---

## 🧰 Tools & Techniques Used

- **Microsoft Excel**
  - `XLOOKUP` to retrieve related values from the `Products` worksheet
  - `INDEX-MATCH` for dynamic data lookup across rows and columns
  - `IFS` statements for data classification
  - PivotTables and Slicers for interactive filtering
  - Custom dashboard design for intuitive visualisation

---

## 🔍 Key Formulas

### `INDEX-MATCH` Example
```excel
=INDEX(Products!$A$1:$G$49, MATCH(orders!$G3, Products!$A:$A, 0), MATCH(L$1, Products!$A$1:$G$1, 0))

Purpose: Retrieves information (e.g., coffee type, roast type, size, unit price) from the Products sheet.
```

How it works:

MATCH(orders!$G3, Products!$A:$A, 0) finds the row where the Product ID from the order matches.

MATCH(L$1, Products!$A$1:$G$1, 0) finds the correct column based on the header in row 1.

INDEX pulls the intersecting value.

### `IFS` Example
```excel
=IFS(
  LEFT(CoffeeType,3)="rob", "Robusta",
  LEFT(CoffeeType,3)="exc", "Excelsa",
  LEFT(CoffeeType,3)="lib", "Liberica",
  LEFT(CoffeeType,3)="ara", "Arabica"
)
```
Roast levels were mapped as follows:

M → Medium

L → Light

D → Dark

### `Sales Calculations` Example
Sales were calculated using a simple formula:

```excel
=Unit Price * Quantity
```
This allows accurate tracking of revenue per order.

## 📊 Dashboard Features
The final Excel dashboard includes the following visual components:

📅 Total Sales Over Time: Displays trends in revenue by day or month

🌍 Sales by Country: Shows how sales are distributed across different countries

🧑‍💼 Top 5 Customers: Highlights the highest spending customers

🔎 Interactive Filters (Slicers):

  - Loyalty Card Status

  - Roast Type

  - Coffee Size (kg)

These slicers allow users to dynamically explore different segments and drill down into the data.
![image](https://github.com/user-attachments/assets/b10d7c56-d6db-47d4-a6f6-2a83f9a10292)


## 📌 How to Use
Open the Excel file from the repository.

Go to the Dashboard sheet.

Use the slicers to filter by loyalty card status, roast type, and coffee size.

Review charts and metrics to understand sales and customer trends.

## 📈 Project Goals
This project demonstrates how Excel can be used to:

Perform advanced data transformation using functions like XLOOKUP, INDEX, MATCH, and IFS

Build interactive dashboards with slicers and PivotTables

Derive business insights from sales and product-level data


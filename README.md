# Chiadika Elue 280
## OLAP_Assignment

# Mini OLAP system using SQLite + Pandas (ROLAP, MOLAP, HOLAP) with demonstrations of Slice, Dice, Roll-Up, Drill-Down.

## Overview
This repository contains a Jupyter Notebook `OLAPAssignment.ipynb` implementing a small data warehouse (star schema) in SQLite, performing OLAP operations as ROLAP SQL queries, building a MOLAP cube with pandas pivot tables, and demonstrating HOLAP (hybrid) by mixing SQL detail retrieval with pandas aggregation. The notebook also includes visualizations.

## Schema

### Fact table
- sales (sale_id, date, product_id, quantity, revenue)

### Dimension tables
- products (product_id, category, name, price)
- dates (date, year, quarter, month)

## Files
- olap_assignment.ipynb — main notebook with code, SQL, pandas code, visualizations.
- cube_category_year.csv — optional exported cube.
- holap_summary.csv — optional exported HOLAP summary.
- README.md — this documentation.

## Implementation Notes

### ROLAP (Relational OLAP)
- Performed using SQL aggregations on the sales fact table joining products and dates.
- Example queries included: average revenue by category, total sales by year, best-selling product in each category.

### MOLAP (Multidimensional OLAP)
- Implemented by loading sales into pandas and creating a pivot table to represent a cube: Revenue × Category × Year.

### HOLAP (Hybrid OLAP)
- Demonstrated by selecting detailed rows from SQL (e.g., all 2024 sales), then computing aggregates in pandas (e.g., per product/category totals).

### OLAP Operations
- ### Slice:
  Filtered the cube to year = 2024.
- ### Dice:
  Filtered rows to year = 2024, quarter = 1, category = 'Electronics'.
- ### Roll-Up:
  Aggregated from product → category → year.
- ### Drill-Down:
  Expanded aggregates from year → quarter → month.

## Visualizations
Included:
- Bar chart: Total revenue by category.
- Heatmap: Category × Year revenue.

## How to run
1. Clone the repository.
2. Open olap_assignment.ipynb in Jupyter Notebook / JupyterLab.
3. Run cells in order. The notebook uses sqlite3, pandas, matplotlib.

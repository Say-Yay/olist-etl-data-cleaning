# Olist ETL Pipeline – Data Cleaning & Integration

### By: Sayeh Nelson | Data Analyst

Hi, I’m Sayeh Nelson, a data analyst with a strong focus on end-to-end analytics, especially in e-commerce and product analysis.
I enjoy breaking down messy, multi-table datasets and transforming them into clean, structured, analysis-ready pipelines. This project reflects how I approach data: organized, thoughtful, and built with clarity in mind.

---

## Project Overview

This repository contains a full ETL (Extract, Transform, Load) workflow built using the Brazilian Olist e-commerce dataset. The purpose of this project is to demonstrate how multiple raw datasets can be:

- cleaned,
- validated,
- merged,
- documented,
- and prepared as one unified master analytic dataset.

This serves as the foundation for multiple downstream analytics projects, including:

- Customer Behavior Analysis
- Product Performance Analysis
- Funnel Analysis
- Delivery & Review Insights

---

## Repository Structure

olist-etl-data-cleaning/
│
├── data/
│    ├── raw/                # Empty placeholder (no raw Kaggle files included)
│    ├── clean/              # Optional: cleaned tables
│    └── processed/          # Final master_olist_dataset.csv
│
├── notebooks/
│    ├── 01_data_cleaning.ipynb
│    └── 02_master_dataset_build.ipynb
│
├── reports/
│    └── pipeline_flowchart.png   
│
└── README.md

---

## Notebooks Included

### 1. 01_data_cleaning.ipynb

Cleans and prepares each individual table:
- customers
- orders
- order_items
- products
- sellers
- geolocation
- payments
- reviews

Key tasks performed include:
- fixing encoding issues
- standardizing city/state names
- removing invalid values
- handling missing values
- validating keys
- exploratory checks for each cleaned table

---

### 2. 02_master_dataset_build.ipynb

Builds the final master dataset using a structured merge order:
1. customers → orders
2. orders → order_items
3. order_items → products
4. order_items → sellers
5. customers → geolocation
6. orders → payments
7. orders → reviews (cleaned version)

Validation includes:
- row count consistency
- key integrity
- missing value analysis
- schema confirmation
- removal of orders containing no items

---

### Final Master Dataset Summary

After completing all merges and removing incomplete orders, the final dataset contains:
- Rows: 117,963
- Columns: 50
- Unique Orders: 99,441
- Unique Customers: 99,441
- Unique Sellers: 3,095
- Unique Products: 32,951
- Unique Reviews: 98,410

This dataset is now analysis-ready and will be used in upcoming EDA and dashboard projects.

---

### Saving the Final Dataset

The master dataset is saved using:
master.to_csv("../data/clean/master_olist_dataset.csv", index=False)

This ensures the clean, combined dataset is reproducible and ready for downstream analysis.

---

### Next Steps (Future Repositories)

This ETL pipeline is the foundation for several standalone analytics projects:

- Customer Behavior EDA
- Product Performance & Category Insights
- Marketplace Funnel Analysis
- Delivery Delay Modeling (Predictive Analytics)

These will be published as separate repositories to highlight different analytical skill sets.

---

Thank you for reading! 🌞

Connect with me!
LinkedIn: www.linkedin.com/in/sayeh-nelson-814941349









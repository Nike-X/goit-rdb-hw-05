# Homework 5 — CTE and Materialized Views

This homework uses the **Olist Brazilian E-Commerce** dataset to practice PostgreSQL CTE pipelines, recursive queries, Materialized Views, and execution-plan analysis.

## Dataset

- **Source:** [Olist on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

- **Size:** 99,441 orders and 112,650 order items (full dataset)

- **Tables:** customers, orders, order items, products, and sellers; reviews loaded to raw only

- **Download:** `kagglehub.dataset_download("olistbr/brazilian-ecommerce")`

## Data and Pipeline

Six raw tables are loaded from CSV; five typed tables use PK, FK, and constraints. The CTE chain calculates RFM, cohort quarter, rolling 30-day AOV, cancellation rate, and preferred category. A synthetic referral table demonstrates recursive CTEs. Customer features are cached in a Materialized View with a unique index and concurrent refresh. `EXPLAIN (ANALYZE, BUFFERS)` compares recalculation with cached reads.

## Repository Structure

- `hw5_olist_CTE_Kalashnikov_Mykola.ipynb` — notebook with SQL queries, outputs, and explanations

- `README.md` — project information and run instructions

- `data/olist/` — optional copy of the six source CSV files

## How to Run

1. Open the notebook in **Google Colab** (tested with runtime **2026.07**).

2. Select **Runtime → Restart session and run all**.

3. The notebook installs dependencies, downloads Olist, starts local PostgreSQL via `pgserver==0.1.4`, and runs the analysis.

Internet access is required for installation and download. No external PostgreSQL server is needed.

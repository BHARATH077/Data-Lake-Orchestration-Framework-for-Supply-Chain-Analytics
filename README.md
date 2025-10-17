# Data-Lake-Orchestration-Framework-for-Supply-Chain-Analytics

# Supply Chain Analytics Project 

## On Step 1, we set up the environment for the project in **Google Colab** and generated **mock datasets** to simulate supply chain data.

## Goals Achieved
- Installed required Python packages: `pyspark`, `duckdb`, `plotly`, `faker`, `pandas`.
- Created folder structure to simulate a **data lake**.
- Generated mock datasets:
1. **ERP Orders** (1000 rows)
   - Columns: order_id, product_id, quantity, order_date, customer_id
2. **IoT Shipments** (1000 rows)
   - Columns: shipment_id, product_id, location, temperature, timestamp
3. **Vendor Shipments** (500 rows)
   - Columns: shipment_id, vendor_id, expected_delivery, actual_delivery
- Previewed datasets to ensure realistic structure.


## On Step 2, we performed **ETL transformations** on the raw datasets and stored them in **Parquet format** to simulate a data lake.

## Goals Achieved
- Loaded raw CSV datasets into **PySpark DataFrames**:
  - ERP Orders
  - IoT Shipments
  - Vendor Shipments
- Converted string dates/timestamps to **date types** for analytics.
- Saved all datasets as **Parquet files** in `data_lake/processed/`:
  - `erp/`
  - `iot/`
  - `vendor/`


## On Step 3, we built the **data warehouse layer** using **DuckDB**. This enables efficient querying and analytics over the processed Parquet files from our data lake.

## Goals Achieved
- Connected to DuckDB and created a persistent database: `data_lake/supply_chain.duckdb`
- Created three main tables:
  1. **erp_orders** (partitioned by year/month)
  2. **iot_shipments**
  3. **vendor_shipments** (includes derived field `delay_days`)
- Computed the first analytical metric: **average shipment delay per vendor**.
  

## On Step 4, we performed **analytical queries and KPI calculations** using the data warehouse. These insights form the foundation for dashboards and business reporting.

## Goals Achieved
- Queried **ERP and vendor datasets** to extract:
  - Top 10 products by total orders (potential stockout risk)
  - Top 10 products with the most delayed/backordered shipments
  - Average shipment delay trends over time
- Visualized monthly shipment delay trends using **Matplotlib**.


## Step 5 concludes the project with a fully functional **interactive analytics dashboard** using Plotly in Google Colab.

## Goals Achieved
- Connected to DuckDB to retrieve analytics data.
- Created three interactive visualizations:
  1. **Stockout Risk:** Top 10 products with highest total orders.
  2. **Backorders:** Products affected by delayed shipments.
  3. **Shipment Delay Trend:** Average delay per month.
- Completed the full end-to-end pipeline:
  - Data Lake (Parquet)
  - ETL (PySpark)
  - Data Warehouse (DuckDB)
  - Analytics (SQL)
  - Dashboard (Plotly)

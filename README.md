# Data-Lake-Orchestration-Framework-for-Supply-Chain-Analytics

# Supply Chain Analytics Project 

## Overview
On Step 1, we set up the environment for the project in **Google Colab** and generated **mock datasets** to simulate supply chain data.

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


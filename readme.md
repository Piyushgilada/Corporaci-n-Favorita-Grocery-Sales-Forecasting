🏪 Overview

This project uses the Corporación Favorita Grocery Sales Forecasting dataset from Kaggle to build an end-to-end data engineering + machine learning workflow.
The dataset contains multi-store, multi-item daily sales along with rich contextual features such as holidays, oil prices, promotions, and item metadata — ideal for realistic forecasting systems.

Kaggle Competition:
https://www.kaggle.com/competitions/favorita-grocery-sales-forecasting

🎯 Project Goals

Build a medallion architecture (Bronze → Silver → Gold) data lake

Perform feature engineering on economic, holiday, and item-level attributes

Train traditional and ML models for forecasting

Prepare scalable pipelines for use in tools like Databricks Fabric, Spark, or cloud environments

🗂 Dataset Files
File	Description
train.csv	Daily unit sales per store & item
items.csv	Product hierarchy & metadata
stores.csv	Store location & cluster metadata
holidays_events.csv	National, regional & local holidays
oil.csv	Daily oil prices (economic proxy)
transactions.csv	Store transaction counts
sample_submission.csv	Kaggle submission template

📝 Dataset

The project uses the public Corporación Favorita Grocery Sales Forecasting
dataset:

125M+ rows

5 years of daily sales

54 stores

~4000 items

Oil prices, holidays, transactions

# 🛒 Retail Demand Forecasting using Microsoft Fabric (End-to-End)

This project builds a full **Retail Demand Forecasting Pipeline** using the
[Corporación Favorita Grocery Sales Forecasting](https://www.kaggle.com/competitions/favorita-grocery-sales-forecasting)
dataset, implemented entirely in **Microsoft Fabric** with a
**Bronze → Silver → Gold** medallion architecture.

The system supports:
- Data ingestion into **Fabric Lakehouse**
- Data cleaning & transformations (Bronze → Silver)
- Automated feature engineering
- Training **per store–item forecasting models**
- Saving models, predictions, metrics to Gold layer
- Visualizing forecasts in **Power BI**
- Scalable execution using Fabric Spark

---

## 📂 Project Architecture

### Medallion Layers
| Layer | Description |
|-------|-------------|
| **Bronze** | Raw Kaggle CSVs |
| **Silver** | Cleaned + merged + enriched data |
| **Gold** | Features, ML models, predictions, metrics |

### Microsoft Fabric Tools Used
- **OneLake / Lakehouse**
- **Fabric Notebooks (PySpark + Python)**
- **Fabric Spark**
- **Power BI Semantic Model**
- **MLflow-compatible model saving**

---

## 🚀 Pipeline Overview

1. **Ingest Raw Files → Bronze**
2. **Clean + Transform → Silver**
3. **Feature Engineering**
   - Lag features (1, 7, 14, 28)
   - Rolling windows
   - Holidays, oil price, transactions
4. **Train LightGBM for each store-item pair**
5. **Save results:**
   - `/gold/models/`
   - `/gold/predictions/`
   - `/gold/metrics/`
6. **Publish Power BI dashboard**

---

## 🧪 Model Summary

Each store-item series trains an individual LightGBM regression model.

Metrics captured:
- **MAE**
- **RMSE**
- **MAPE**

Example output:
```text
Completed store 29 item 874990 | MAE=1.19 RMSE=1.47

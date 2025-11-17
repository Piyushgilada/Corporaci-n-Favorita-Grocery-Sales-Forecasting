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

favorita-forecasting/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── bronze/
│   │   ├── train.csv
│   │   ├── items.csv
│   │   ├── stores.csv
│   │   ├── holidays_events.csv
│   │   └── oil.csv
│   │
│   ├── silver/
│   │   ├── cleaned_train.parquet
│   │   ├── merged_data.parquet
│   │   └── features_intermediate.parquet
│   │
│   └── gold/
│       └── modeling_ready_features.parquet
│
├── notebooks/
│   ├── 01_exploration.ipynb
│   ├── 02_cleaning_and_joining.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_model_training.ipynb
│   └── 05_evaluation.ipynb
│
├── src/
│   ├── data_prep/
│   │   ├── load_data.py
│   │   ├── clean_data.py
│   │   ├── join_data.py
│   │   └── feature_engineering.py
│   │
│   ├── models/
│   │   ├── xgboost_model.py
│   │   ├── prophet_model.py
│   │   └── evaluation.py
│   │
│   └── utils/
│       └── helpers.py
│
└── outputs/
    ├── model_artifacts/
    ├── plots/
    └── submissions/

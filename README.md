# Smart Inventory Analytics and Demand Forecasting System

End-to-end **Data Analytics + Machine Learning** project for retail inventory planning.

## Dataset
**Retail Store Inventory Forecasting Dataset — Kaggle**  
https://www.kaggle.com/datasets/anirudhchauhan/retail-store-inventory-forecasting-dataset

Supplied data: **73,100 rows × 15 columns**, covering 2022-01-01 to 2024-01-01.

> The dataset is synthetic. 

## Features
- Data validation and cleaning
- Exploratory data analysis
- Sales/inventory visualization
- Leakage-safe time-series features
- HistGradientBoosting demand forecasting
- Lag-7 baseline comparison
- MAE, RMSE and R² evaluation
- HIGH/MEDIUM/LOW stock-risk classification
- Transparent reorder recommendations
- Business insights and limitations

## Structure
```text
smart-inventory-analytics/
├── data/retail_store_inventory.csv
├── notebooks/smart_inventory_system.ipynb
├── report/Smart_Inventory_Report.docx
├── report/reorder_recommendations.csv
├── requirements.txt
├── README.md
└── .gitignore
```

## Run
```bash
pip install -r requirements.txt
jupyter notebook
```
Open `notebooks/smart_inventory_system.ipynb` and run all cells.

## ML design
`Demand Forecast` is excluded because it is extremely correlated with `Units Sold` and may be target-derived. Lag/rolling features are shifted before calculation, and the train/test split is chronological.

## Reorder formula
```text
Recommended Order
= Predicted Demand × Planning Horizon
  + Safety Stock
  − Current Inventory
```
The planning horizon is 3 days, an explicit analytical assumption because supplier lead time is unavailable.

## Limitations
The dataset is synthetic and lacks supplier lead time, MOQ, capacity and procurement cost constraints. Recommendations are educational/internship outputs, not real procurement instructions.

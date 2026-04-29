# london-bike-share-analysis
Demand forecasting and surge detection for TfL Santander Cycles using clustering and XGBoost — August 2023

## London Bike Share Demand Analysis

### Problem
TfL operates 800+ Santander Cycles stations across London.
Predicting demand surges enables proactive rebalancing —
reducing empty stations and improving customer experience.

### Dataset
769,000 trip records from August 2023 (TfL Open Data)
Enriched with hourly weather data (Open-Meteo API)
and UK public holidays.

### Approach
1. Data cleaning and feature engineering
2. Unsupervised clustering (KMeans k=4) to identify 
   station behavioural types
3. Regression models (Linear, Random Forest, XGBoost) 
   per cluster for demand forecasting
4. Binary surge classifier (XGBoost, AUC=0.826) 
   with recall-optimised threshold for High Volume stations

### Key Results
- 4 station clusters identified: Office District, 
  Mixed Use, High Volume, Neighbourhood
- XGBoost outperforms across all clusters
- Surge detection achieves 90% recall at optimised 
  threshold — catching 476 of 528 surge events
- demand_lag_1h is the strongest predictor at 
  High Volume stations — confirming momentum-driven 
  surge dynamics

### Files
notebooks/london_bikes_analysis.ipynb
London_Bike_Share_Presentation.pptx

### How to run
pip install -r requirements.txt
jupyter notebook notebooks/london_bikes_analysis.ipynb

## Data
The dataset used in this project is 
Transport for London (TfL) Open Data sourced from Kaggle:
**Download:** 
https://www.kaggle.com/datasets/kalacheva/london-bike-share-usage-dataset

**File needed:** 
Journey Data Extract — August 2023
Filename: LondonBikeJourneyAug2023.csv

Place the CSV file in this /data folder before 
running the notebook.

Note: The CSV is not included in this repository 
due to file size (approx. 150MB).

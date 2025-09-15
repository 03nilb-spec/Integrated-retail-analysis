# Retail Sales Forecasting & Store Optimization

This project applies **data science techniques** to a retail sales dataset to uncover insights and provide actionable strategies for **inventory management, sales forecasting, anomaly detection, and personalized store planning**.

---

## Project Objectives
- Detect **anomalies** in sales patterns and investigate causes (holidays, markdowns, economic factors).
- Analyze **time-based trends** and seasonal effects on sales.
- Perform **store segmentation** using clustering to identify groups of similar stores.
- Explore **department-level correlations** to identify cross-selling opportunities.
- Build **demand forecasting models** (Prophet) to predict future weekly sales.
- Provide **personalized strategies** for different store segments.

---

## Dataset Overview
Three datasets were provided:
1. **Sales data** → Store, Dept, Date, Weekly Sales, Holiday flag  
2. **Features data** → Temperature, Fuel Price, CPI, Unemployment, MarkDowns, Holiday flag  
3. **Store data** → Store Type (A, B, C), Store Size  

Merged on `Store` and `Date` to create a unified dataset.

---

## Methods & Techniques
- **Data Preprocessing**  
  - Handling missing values (especially in markdowns)  
  - Feature engineering (Month, Year, WeekOfYear, Store Size Category, Holiday indicator)  

- **Exploratory Data Analysis (EDA)**  
  - Sales trends over time  
  - Holiday vs Non-holiday sales comparison  
  - Store and department-level breakdowns  

- **Anomaly Detection**  
  - Rolling mean & standard deviation method  
  - Time-series decomposition (trend + seasonality + residuals)  

- **Store Segmentation (Clustering)**  
  - Features: average sales, volatility, markdowns, size, store type  
  - K-Means clustering → best k=2 (silhouette ~0.47)  
  - Cluster 0: Small, B-type, lower sales  
  - Cluster 1: Large, A-type, higher sales, markdown-driven  

- **Market Basket / Department Correlation**  
  - Correlation heatmap of department sales  
  - Identified pairs of departments with strong demand correlation → cross-sell potential  

- **Demand Forecasting**  
  - Prophet model (weekly & yearly seasonality, holiday effects)  
  - ARIMA model for comparison  
  - Forecasted future weekly sales and captured holiday spikes  


---

## Results & Insights
- Holiday weeks generate **significant sales spikes**.  
- Stores naturally fall into **two performance clusters** (small vs large).  
- **High correlations** found between several departments → cross-sell opportunities.  
- Forecasts show stable baseline sales with **major spikes in Nov–Dec holidays**.   

---

## ✅ Business Recommendations
- **Cluster 0 (Small, B-type stores):**  
  - Maintain **lean inventory** to avoid overstocking.  
  - Apply **targeted markdowns** only during holiday periods.  

- **Cluster 1 (Large, A-type stores):**  
  - Maintain **inventory buffers** before holidays.  
  - Run **aggressive promotions & markdowns** to maximize holiday sales.  
  - Use **cross-selling strategies** between correlated departments.  

- **Company-wide:**  
  - Align **inventory, staffing, and promotions** with demand forecasts.  
  - Continuously monitor anomalies for unexpected demand shifts or data errors.  

---

## Tools & Libraries
- Python (Pandas, NumPy, Matplotlib, Seaborn)  
- Scikit-learn (clustering, metrics)  
- Statsmodels (time-series decomposition)  
- Prophet (forecasting)  

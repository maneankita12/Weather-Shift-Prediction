# Weather-Shift-Prediction

# 🌦️ Weather Shift Prediction

## 📌 Project Overview
This project focuses on **predicting temperature at specific latitude/longitude coordinates and times** using climate datasets and machine learning models. The primary aim is to evaluate uncertainty estimates and robustness under distributional shifts in weather data.

Weather prediction plays a crucial role in planning, safety, and disaster management. By leveraging advanced forecasting models, we aim to improve accuracy in long-term temperature and climate predictions.

---

## 🔍 Problem Statement
The goal is to **predict the temperature** at a given latitude, longitude, and time, using historical measurements and climate model predictions.  

Challenges include:
- Non-uniform training data across different climate zones  
- Highly non-stationary nature of weather systems  

---

## 📂 Dataset Description
We utilized large-scale weather datasets (`.csv` files):

- **Train.csv** → 3,129,592 rows × 129 columns (5.03 GB)  
- **Dev-in.csv & Dev-out.csv** → 50,000 rows each × 129 columns (~80 MB each)  
- **Eval.csv** → 1,137,731 rows × 123 columns (1.71 GB)  

### Key Attributes
- **Meta-data:**  
  - `fact-time` → timestamp  
  - `fact-latitude`, `fact-longitude` → location  
  - `fact-temperature` → observed temperature  
  - `climate` → climate zone classification  

- **Climate Models:**  
  - **CMC** (Canadian Meteorological Center) – 56 attributes  
  - **WRF** (Weather Research & Forecasting) – 13 attributes  
  - **GFS** (Global Forecast System) – 50 attributes  

---

## ⚙️ Preprocessing
- Removed rows with missing values  
- Dropped irrelevant columns  
- Worked with a **reduced dataset (1,000,000 rows × 113 columns)**  
- Feature selection performed using **F-score**  

---

## 🤖 Machine Learning Models
We experimented with multiple regression and ensemble models:

| Model              | RMSE Score |
|--------------------|------------|
| Linear Regression  | 2.168      |
| Elastic Net        | 2.178      |
| XGBoost            | 1.948 – 4.49 |
| CatBoost Regressor | 1.9745 – 2.717 |

**Best Performing Model:**  
✅ **XGBoost (with feature selection)** → **RMSE: 1.948**

---

## 🏆 Results & Ranking
1. **XGBoost (F-score feature selection)** – RMSE: 1.948  
2. **CatBoost Regressor** – RMSE: 1.9745  
3. **Linear Regression** – RMSE: 2.168  
4. **Elastic Net** – RMSE: 2.178  

---

## 🚀 Future Scope
- Incorporating **deep learning architectures** (LSTMs, Transformers) for time-series forecasting  
- Handling **multi-climate generalization** with improved robustness  
- Real-time weather monitoring and adaptive learning  

---

# Abstract
This project applies a supervised machine learning approach to predict hourly bike rental demand using the Bike Sharing Dataset. The study focuses on forecasting the total rental count (cnt) by leveraging time-related, seasonal, and weather-based features, while carefully removing leakage variables such as casual and registered. The PyCaret regression framework was used to automate preprocessing, model selection, and evaluation across multiple algorithms. After comparing a wide range of regression models, the Extra Trees Regressor achieved the best performance, demonstrating strong predictive capability with an R² of approximately 0.945 and a low RMSE of around 42. These results indicate that tree-based ensemble models effectively capture nonlinear patterns in bike rental behavior, making the final model suitable for demand forecasting and operational planning. The completed pipeline was finalized, evaluated, and saved for future deployment, confirming the practicality and robustness of the chosen model.
# Bike Sharing Demand Prediction using PyCaret  
A Machine Learning Regression Project – Fall 2025

This project focuses on predicting hourly bike rental demand using the **Bike Sharing Dataset** (UCI Machine Learning Repository). The goal is to build an accurate regression model that can estimate the number of bikes rented (`cnt`) using time-based, seasonal, and weather-related features.

The project uses **PyCaret**, a low-code machine learning library, to test multiple regression models, compare their performance, and identify the best-performing model with minimal manual tuning.

---

## 📌 Project Overview

Bike-sharing systems generate valuable usage data that can be used to forecast demand. Accurate demand forecasting helps improve:

- Resource allocation  
- Bike distribution  
- Maintenance scheduling  
- Operational planning  

This project replicates the workflow of the official PyCaret Regression Tutorial, using the hourly Bike Sharing dataset (`hour.csv`) as the input.

---

## 🧠 Objectives

- Load and clean the Bike Sharing Dataset  
- Remove leakage features (`casual`, `registered`)  
- Use PyCaret to preprocess data  
- Compare multiple regression algorithms  
- Tune and finalize the best model  
- Save and load the trained model pipeline  
- Evaluate performance using R² and RMSE  

---

## 📂 Dataset

The dataset used in this project is:

- **hour.csv** from the Bike Sharing Dataset  
- Source: UCI ML Repository  
- Contains 17,379 hourly records with features such as:  
  - Season, weather, temperature  
  - Hour of the day, weekday  
  - Working day flag, humidity, windspeed  
  - Total bike rentals (`cnt`)  

---

## 🛠️ Technologies Used

- **Python 3.11+**
- **PyCaret (Regression Module)**
- **Pandas**
- **NumPy**
- **Matplotlib / Seaborn**
- **Jupyter Notebook / VS Code**

---

## 🔍 Feature Engineering

Features used for training:

- `instant`: numerical  
- `dteday`: categorical  
- `season`: numerical  
- `yr`: numerical  
- `mnth`: numerical  
- `hr`: numerical  
- `holiday`: numerical  
- `weekday`: numerical  
- `workingday`: numerical  
- `weathersit`: numerical  
- `temp`: numerical  
- `atemp`: numerical  
- `hum`: numerical  
- `windspeed`: numerical  

**Dropped Columns:**

- `casual`  
- `registered`  

Reason:  
These directly sum to the target variable `cnt` and would cause **data leakage**.

---

## 📊 Model Training & Evaluation

PyCaret's `compare_models()` function was used to test algorithms such as:

- Linear Regression  
- Ridge / Lasso / ElasticNet  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- Extra Trees Regressor  
- LightGBM / XGBoost (if available)  

**Best Model: Extra Trees Regressor**

**Performance:**

| Metric | Score |
|--------|--------|
| **R² Score** | **~0.945** |
| **RMSE** | **~42** |

This model captured nonlinear patterns extremely well and performed consistently better than linear and boosted models.

---

## 📁 Saving & Loading the Model

**Save:**
```python
save_model(final_model, "bike_sharing_model")

loaded_model = load_model("bike_sharing_model")

```
## Key Results

Ensemble models performed best on the hourly dataset.

Extra Trees achieved the highest accuracy with low error.

PyCaret significantly simplified the entire workflow.

Predictions align with patterns found in previous research.


MIT License

Copyright (c) 2025 Gurvir

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.




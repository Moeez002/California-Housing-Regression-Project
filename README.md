# 🏡 California Housing Regression Project

**Author:** Abdul Moeez  
**Goal:** Predict the median house value in California using regression models.  

---

## 📂 Project Overview
This project analyzes the California Housing dataset and predicts the **median house value**. It demonstrates a full data science workflow, including:

- Data exploration & visualization
- Handling missing values
- Feature engineering & scaling
- Categorical encoding
- Outlier detection and removal
- Feature selection
- Model building, hyperparameter tuning, and ensemble methods

---

## 📊 Dataset
The dataset `housing.csv` contains housing data from California with features like:

- `longitude`, `latitude` — Geographical location
- `housing_median_age` — Age of the houses
- `total_rooms`, `total_bedrooms`, `population`, `households` — Housing details
- `median_income` — Median income of households
- `ocean_proximity` — Categorical feature representing proximity to the ocean
- `median_house_value` — Target variable  

Missing values are handled, and new ratio-based features were engineered:

- `rooms_per_household`
- `bedrooms_per_room`
- `population_per_household`

---

## 🛠 Data Preprocessing

1. **Missing Values:** Filled `total_bedrooms` with the mean.  
2. **Encoding:** One-hot encoding for `ocean_proximity`.  
3. **Outliers:** Removed using a 3*IQR threshold due to skewed data.  
4. **Scaling:**  
   - StandardScaler for features like `total_rooms`, `median_income`, etc.  
   - MinMaxScaler for `longitude`, `latitude`, `housing_median_age`.  

---

## 🔎 Feature Selection

- **Sequential Feature Selector (SFS):** Forward selection for Linear Regression and Decision Tree models.
- **Lasso Regression:** Used to identify features with highest importance.

---

## 🤖 Models Implemented

- **Linear Regression**
- **Polynomial Regression (degree 3)**
- **Decision Tree Regressor** (RandomizedSearchCV for hyperparameter tuning)
- **Random Forest Regressor** (GridSearchCV for hyperparameter tuning)
- **Voting Regressor**: Ensemble of Linear, Polynomial, and Decision Tree models  

---

## ⚡ Results

| Model | Train R² | Test R² |
|-------|----------|---------|
| Linear Regression | ~0.72 | ~0.71 |
| Polynomial Regression | ~0.80 | ~0.76 |
| Decision Tree (tuned) | ~0.72 | ~0.74 |
| Random Forest (tuned) | ~0.97 | ~0.82 |
| Voting Regressor | ~0.82 | ~0.76 |

> **Best Test Accuracy:** 82%  
> **Best Train Accuracy:** 94%  

This indicates a slight overfitting, typical with complex models like Random Forest and Polynomial Regression.

---

## 📈 Visualizations

- Correlation heatmap of all features
- Feature importance using Lasso regression

---

## 💻 How to Run

1. Clone the repo:  
```bash
git clone https://github.com/Moeez002/california-housing-regression.git

2. Install dependencies:

pip install -r requirements.txt

3. Open the file PROJECT2.ipynb



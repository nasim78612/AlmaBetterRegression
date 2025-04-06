

# 🚲 Yulu Bike Demand Prediction 📈

### 🌟 Project Summary: Predictive Modeling for Yulu Bike Rentals

Welcome to a data-driven journey into the future of urban mobility! This project harnesses the power of machine learning to predict **Yulu Bike rental demand**, supporting eco-friendly transportation with smarter, data-backed decision-making.

---

### 🔍 Introduction:

**Yulu Bike**, a pioneer in sustainable urban commuting, aims to **optimize fleet operations** and **enhance rider experience**. Using **Exploratory Data Analysis (EDA)** and advanced **regression modeling**, we forecast hourly bike rental demand based on variables such as temperature, humidity, time, season, and holidays.

---

### 📊 Exploratory Data Analysis (EDA):

- **⏰ Hourly Trends:** Rentals peak between **7–9 AM** and **4–7 PM**, aligning with commuting hours.  
- **🍂 Seasonal Patterns:** Summer ☀️ and Autumn 🍁 have the highest demand, Winter ❄️ the lowest.  
- **📅 Weekday vs. Weekend:** Weekdays (especially Tuesday & Wednesday) see higher demand.  
- **🎉 Holiday Impact:** Rentals remain steady but are more spread out across the day.  
- **🌡️ Weather Influence:** Rentals increase with higher temperatures and lower rainfall/snowfall.  
- **📈 Growth:** Clear increase in rentals from 2017 to 2018.

---

### 🤖 Model Selection & Hyperparameter Tuning:

We evaluated several models, tuning hyperparameters using **RandomizedSearchCV** and **Optuna** for optimal performance.

#### ✅ Final Tuned Models:

---

#### 1. **XGBoost Regressor (Best Model)**  
- ⭐ **R² Score:** `0.947 (Test)` | `0.972 (Train)`  
- 📉 **MAE:** ~64  
- ⚙️ **Tuned with:** Optuna  
- 🔧 **Key Parameters:**  
  - `n_estimators=500`  
  - `learning_rate=0.03`  
  - `max_depth=8`  
  - `subsample=0.8`  
  - `colsample_bytree=0.8`  
  - `reg_alpha=0.01`, `reg_lambda=1.0`  
- 🧠 **Best for:** High performance and scalable predictions

---

#### 2. **LightGBM Regressor**  
- ⭐ **R² Score:** `0.944 (Test)` | `0.966 (Train)`  
- 📉 **MAE:** ~67  
- ⚙️ **Tuned with:** RandomizedSearchCV  
- 🔧 **Key Parameters:**  
  - `num_leaves=31`  
  - `learning_rate=0.05`  
  - `n_estimators=400`  
  - `boosting_type='gbdt'`  
- ⚡ **Best for:** Fast training on large datasets

---

#### 3. **Random Forest Regressor**  
- ⭐ **R² Score:** `0.936 (Test)` | `0.989 (Train)`  
- 📉 **MAE:** ~70  
- ⚙️ **Tuned with:** RandomizedSearchCV  
- 🔧 **Key Parameters:**  
  - `n_estimators=300`  
  - `max_depth=30`  
  - `min_samples_split=5`  
- 🌲 **Best for:** Interpretability & robustness

---

#### 4. **Gradient Boosting Regressor**  
- ⭐ **R² Score:** `0.897 (Test)` | `0.904 (Train)`  
- 📉 **MAE:** ~88  
- ⚙️ **Tuned with:** RandomizedSearchCV  
- 🔧 **Key Parameters:**  
  - `n_estimators=250`  
  - `learning_rate=0.1`  
  - `max_depth=6`  
  - `subsample=0.8`  
- 🔁 **Best for:** Stable and consistent performance

---

### 📌 Additional Notes:
- **Feature Engineering:** One-hot encoding, PowerTransform for skewed variables, removal of highly correlated features, and datetime decomposition were applied.  
- **Train-Test Split:** 80-20 ratio (6772 train, 1693 test samples).  
- **Evaluation Metrics:** R² Score, MAE, RMSE used across all models.

---

### 🏁 Conclusion & Recommendations:

By blending **EDA** with robust machine learning, we empower Yulu to:

✅ Accurately forecast bike rental demand  
✅ Plan fleet deployment based on time, weather, and user behavior  
✅ Optimize operations and reduce idle bikes  
✅ Scale this model to other cities with confidence

---

### 🚀 Real-World Impact:

With predictive analytics at the core, Yulu can:
- 🎯 Meet user demand efficiently  
- 🔄 Optimize resource and energy use  
- 😊 Enhance customer satisfaction  
- 🌍 Champion sustainable urban mobility

---

Let’s ride into a smarter, data-driven future! 🌿📊  
**Project by Nasim Aalam**

---

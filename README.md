Here's your updated **Markdown summary** incorporating all the work you've done, including transformations, outlier handling, feature engineering, and modeling. This version is more comprehensive and aligned with your project pipeline:

---

# 🚲 **AlmaBetterRegression Project – Seoul Bike Sharing Demand Prediction**

## **📌 Project Summary: Predictive Modeling for Bike Rentals**

### **📍 Introduction:**
Bike-sharing systems have become a vital component of urban mobility, offering an eco-friendly, affordable, and flexible transportation mode. This project aims to **predict hourly bike rental demand** using comprehensive **exploratory data analysis (EDA)**, **data preprocessing**, and **machine learning models**. The dataset encompasses **weather, temporal, and seasonal variables** from Seoul's public bike-sharing service.

---

## **🔎 Exploratory Data Analysis (EDA):**

### **Hourly Trends:**
- Rentals surge during **commute hours** – 7–9 AM and 4–7 PM.
- Demand is lowest during **late nights and early mornings**, aligning with typical work-life schedules.

### **Seasonal Patterns:**
- **Summer and Autumn** see the highest bike rentals due to pleasant weather.
- **Winter** records the lowest usage, affected by cold, snowfall, and reduced daylight.

### **Weekday vs Weekend:**
- **Weekdays**, especially **Tuesday and Wednesday**, show higher demand.
- Slight dip on **weekends**, particularly on **Sundays**.

### **Holiday Impact:**
- **Minimal difference** in rentals during holidays.
- Holidays show **smooth and steady demand**, unlike sharp weekday peaks.

### **Weather Variables:**
- **Temperature(°C)** has a strong positive correlation with rentals.  
- **Rainfall and Snowfall** negatively impact rentals, especially during heavy precipitation.
- **Humidity** is moderately negatively correlated with visibility and sunlight.

### **Yearly Growth:**
- A noticeable increase in total rentals from **2017 to 2018**, indicating a **growing user base and adoption**.

---

## **🧹 Data Preprocessing & Transformation**

### **Outlier Detection:**
- Outliers were found in **Wind Speed**, **Rainfall**, **Snowfall**, and **Solar Radiation**.
- Visualized using **boxplots** and handled using transformations.

### **Skewness Reduction (Transformations Applied):**
- Compared different transformations: **Log1p**, **Square Root**, **Cube Root**.
- Applied **Yeo-Johnson Transformation** to key features:  
  `['Wind speed (m/s)', 'Solar Radiation (MJ/m2)', 'Rainfall(mm)', 'Snowfall (cm)', 'Rented Bike Count']`.

### **Variable Normalization:**
- QQ plots and histograms confirmed **normalization success** post-transformation.

### **Encoding Categorical Features:**
- Applied **One-Hot Encoding** to variables like `Seasons` and `Holiday`.

---

## **🧠 Feature Engineering & Multicollinearity Handling**

### **Dropped Features:**
- `Date`, `Year`, and `Dew point temperature(°C)` removed due to **redundancy or high correlation**.

### **Multicollinearity Analysis (VIF):**
- `Temperature(°C)` (VIF = 5.10) → High correlation with Seasons & Humidity  
- `Seasons_Winter` (VIF = 3.92) → Overlaps with `Temperature(°C)`
- `Humidity(%)` (VIF = 2.79) → Moderately multicollinear, retained after review

### ✅ **Final Feature Set:**
- Includes **Hour, Weekday, Month, Visibility, Wind Speed, Rainfall, Snowfall**, and **Encoded Season/Holiday Columns**.

---

## **📊 Hypothesis Testing & Correlation Insights**

- 📈 **Rentals vs Temperature:**  
  Correlation Coefficient = **0.56**, p-value = **0.0** → **Significant positive correlation**

- 🏖️ **Holidays vs Non-Holidays:**  
  T-Statistic = **-7.17**, p-value = **3e-12** → **Significant difference in rentals**

- ❄️ **Summer vs Winter Rentals:**  
  T-Statistic = **53.75**, p-value = **0.0** → **High seasonal variation**

---

## **🤖 Predictive Modeling**

### ✅ **RandomForestRegressor**
- **R² Score (Test)**: **0.914**
- **RMSE**: Low, predictions closely aligned with actuals
- Excellent model for **deployment and real-time predictions**

### 🌳 **DecisionTreeRegressor (Tuned)**
- **R² Score (Test)**: **0.894**
- Performed well, but slightly less accurate than Random Forest
- Useful for **model interpretability and quick inferences**

---

## **📈 Visual Analysis**

- ✅ **Correlation Heatmap** revealed strong relationships between weather variables.
- ✅ **Pairplots** exposed seasonal effects and variable interactions.
- ✅ **Boxplots** visualized outlier reduction after transformation.
- ✅ **Transformation plots (QQ/Histograms)** confirmed normalization success.

---

## **📌 Conclusion & Recommendations**

- Combined **EDA, feature engineering**, and **modeling** to uncover **user behavior** and **optimize predictions**.
- Recommend **RandomForestRegressor** for its high accuracy and robustness.
- **Use insights for real-time demand forecasting**, targeted promotions during peak hours, and adaptive resource allocation.
- Future scope includes integrating **live weather APIs**, optimizing fleet management, and **expanding the model** to other cities.


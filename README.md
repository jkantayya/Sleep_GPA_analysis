# team-nap-navigators-fa24
# Sleep_GPA_analysis

This project explores how college students' sleep patterns affect academic performance. Using a dataset of 634 first-year students from CMU, UW, and Notre Dame, we performed exploratory analysis and built predictive models to examine how sleep behaviors influence GPA.

---

## 📌 Objective
To identify which sleep-related features best predict student GPA and evaluate the performance of regression models built from those features.

---

## 🧠 Data Overview
- **Universities:** CMU, UW, Notre Dame  
- **Participants:** 634 first-year students  
- **Data Source:** Fitbit devices tracking sleep behavior  
- **Variables analyzed:**
  - Cumulative GPA, Term GPA  
  - Average sleep duration (nighttime)  
  - Daytime sleep (naps)  
  - Bedtime variability (mssd)

---

## 🔍 Key Features & Methods

### 📊 Feature Selection: Sequential Backward Selection
We applied **sequential backward feature selection** to identify the most predictive combination of variables for GPA.

We tested models with:
- **2 best features:** `cum_gpa`, `bedtime_mssd`
- **3 best features:** `cum_gpa`, `bedtime_mssd`, `daytime_sleep`
- **4 best features:** `cum_gpa`, `bedtime_mssd`, `daytime_sleep`, `TotalSleepTime`

### 🧮 Best Model Equation (4 features)
ŷ = 0.9878 + 0.6808(cum_gpa) - 0.0798(bedtime_mssd) - 0.0020(daytime_sleep) + 0.0005(TotalSleepTime)

yaml
Copy
Edit

---

## 📈 Model Performance
We compared **R², Adjusted R²**, and **RMSE** on both training and testing data:

| Feature Set | R² Train | R² Test | Adj. R² Test | RMSE Test |
|-------------|----------|---------|--------------|-----------|
| 4 Features  | 0.478    | 0.346   | 0.315        | 0.385     |
| 3 Features  | 0.475    | 0.335   | 0.314        | 0.388     |

### 🔍 Residuals Plots
All models showed fairly tight residual distributions, but the **4-variable model** offered slightly better generalization based on test metrics.

---

## ✅ Takeaways
- **Cumulative GPA** is the strongest predictor, but sleep patterns provide meaningful additional insights.
- More **consistent bedtimes** and **shorter daytime sleep** (indicating better rest at night) are correlated with higher GPA.
- Sleep behavior is a viable input in predictive models for academic success.

---

## 📁 What's Inside
- `visualization.ipynb` – EDA on GPA vs. sleep patterns  
- `regression.ipynb` – Model creation, performance comparison  
- `cmu-sleep.csv` – Raw data from Fitbit and student records

---

## 🛠️ Tools Used
- Python, Jupyter Notebook  
- Pandas, NumPy  
- Seaborn, Matplotlib  
- Scikit-learn

# 🔋 Early Prediction of Battery Life using Machine Learning

This project predicts the **cycle life of lithium-ion batteries** using early-cycle data and machine learning models. The goal is to estimate when a battery will degrade to **80% of its original capacity** — a key threshold for end-of-life. The project leverages **100 initial cycles** to predict full life, improving **preventive maintenance** and reliability in battery-powered systems.

---
## 📂 Dataset

* **Source:** [MIT Battery Dataset (GitHub - Battery DataSet by Severson et al., 2019)](https://github.com/wanderine/BatteryDataSet)
* **Format:** Time-series sensor data (voltage, current, temperature, capacity) for \~124 commercial batteries.
* **Label:** Actual cycle life (number of cycles until capacity drops to 80%).

---

## 🎯 Objective

Predict battery life using data from only the **first 100 cycles**, enabling:

* Early-stage decision-making for battery use or replacement.
* Accurate and low-cost predictions without needing full lifetime data.

---

## 🛠️ Tools & Skills

**Language:** Python
**Libraries:** `scikit-learn`, `NumPy`, `Pandas`, `Matplotlib`, `Seaborn`
**Skills:** Feature Engineering, Supervised Learning, Model Tuning, RMSE Optimization, Feature Selection

---

## 🔍 Workflow Overview

### 1. 🧪 **Data Preprocessing**
Understanding Big Raw DataSet file
https://yellow-gopher-f46.notion.site/Understanding-DataSet-95a729ede66b4133bc155bb4f4b9140b?pvs=73 
Contains all dataq about Features extraction
https://yellow-gopher-f46.notion.site/Creating-Features-19fac7cfe10043e688cd38d7f1ba7047?pvs=74 
* Cleaned and interpolated raw battery charge-discharge curves.
* Standardized measurements across batteries.
* Extracted data from the **first 100 cycles only**.

### 2. 🧬 **Feature Engineering**

* Extracted **42 features** including:

  * Capacity curve slopes
  * Variance in internal resistance
  * Voltage differentials
  * Cycle-wise degradation patterns
* Features chosen to reflect early degradation signals.

### 3. 📈 **Model Training and Evaluation**

#### A. **Baseline Models**

* Trained initial models on all 42 features using:
  * **Support Vector Machine (SVM)**
  * **Random Forest Regressor**
* **Performance:** RMSE \~ **157**

#### B. **Wrapper-Based Feature Selection**

* Optimized model hyperparameters via **Grid Search**.
* **Performance:** RMSE reduced to **133**

#### C. **Embedded Feature Selection**

* Used algorithms with built-in feature importance:
  * **Tree-Based Methods** (Random Forest)
* Auto-selected key predictive 12 features.
* **Performance:** RMSE further reduced to **122**

---

## 📊 Final Results Summary

| Model Type                 | Method                  | RMSE |
| -------------------------- | ----------------------- | ---- |
| Baseline                   | All features (SVM / RF) | 157  |
| Wrapper Selection          | RFE + Hyperparam Tuning | 133  |
| Embedded Feature Selection | RandomForest+ Hyperparam Tuning | 122  |


---

## 📈 Future Enhancements

* Use **LSTM** or **1D-CNN** models for deep sequential modeling.
* Create an interactive dashboard using **Streamlit**.
* Integrate with IoT devices for **real-time health prediction**.

---

## 🧠 Key Learnings

* High-quality feature engineering can significantly improve model performance on limited data.
* Early cycles contain rich information for degradation modeling.
* Combining feature selection with Features Selection methods leads to robust generalization.

---

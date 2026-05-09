# 🚀 Machine Learning Projects

Welcome to my **Machine Learning Projects** repository!

## 🎯 About This Repository
This repository serves as my personal sandbox and portfolio. I created this space specifically for **training, practicing, and upskilling** in various Machine Learning, Data Science, and Computer Vision concepts. 

By building end-to-end mini-projects, I aim to bridge the gap between theoretical knowledge and practical implementation.

## 🧠 What I'm Learning & Practicing
* **Data Processing:** Cleaning, transforming, and exploring datasets.
* **Computer Vision:** Image processing, feature extraction, and object classification.
* **Machine Learning Algorithms:** Implementing classic models (Regression, KNN, SVM, Random Forest, XGBoost, etc.) and understanding their mechanics.
* **Model Evaluation:** Using metrics like RMSE, MAE, R-squared, accuracy, confusion matrices, and F1-scores to assess performance.
* **Python Ecosystem:** Mastering tools like Scikit-Learn, Pandas, NumPy, OpenCV, and Matplotlib.

## 📂 Projects Directory

| Project Name | Domain | Description |
| :--- | :--- | :--- |
| **[Rice Grain Classification](#)** | Computer Vision / ML | Classifying rice grain varieties (Arborio vs. Basmati) using geometric features and KNN. |
| *(More coming soon...)* | | |

---

## 🏃‍♂️ Featured Project: Athlete Recovery Score Predictor

### The Goal
Predict an athlete’s `Recovery_Score` (a continuous target variable) for the following day. By analyzing daily metrics, coaches and sports scientists can proactively manage athlete fatigue, prevent overtraining, and optimize performance.

### Methodology

**1. Data Collection & Variables**
* **Features:** `Athlete_ID`, `Sleep_Hours`, `Training_Duration_Min`, `Training_Intensity` (RPE), `Resting_Heart_Rate`, `Diet_Quality`.
* **Target:** `Recovery_Score` (e.g., 1-100 scale).

**2. Feature Engineering**
* **Training Load:** `Training_Duration_Min * Training_Intensity`
* **Sleep Deficit:** `8 - Sleep_Hours` (Capped at 0 if negative).
* **Rolling Averages:** Creating 7-day or 3-day averages of training loads to account for cumulative fatigue.

**3. Data Preprocessing**
* Handling missing values via median imputation or forward-filling.
* Splitting data into 80% Training and 20% Testing sets.
* Applying `StandardScaler` to normalize numerical features.

**4. Model Selection & Training**
* **Linear Regression:** Baseline model for establishing simple linear relationships.
* **Random Forest Regressor:** Ensemble method to capture non-linear relationships (e.g., optimal vs. excessive sleep).
* **XGBoost Regressor:** Optimized gradient boosting for high performance on tabular features.

**5. Model Evaluation**
* Measured using Regression metrics: **Mean Absolute Error (MAE)**, **Root Mean Squared Error (RMSE)**, and **R-Squared ($R^2$)**.

---

## 🛠️ Tech Stack & Tools

* **Languages:** Python
* **Libraries:** `scikit-learn`, `pandas`, `numpy`, `xgboost`, `opencv-python`, `matplotlib`, `kagglehub`
* **Environments:** Jupyter Notebooks, Google Colab, VS Code

## 🤝 Let's Connect

Feel free to explore the code, use it for your own learning, or reach out if you have feedback or suggestions!

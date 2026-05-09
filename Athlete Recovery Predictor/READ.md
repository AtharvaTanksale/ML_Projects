# Athlete Recovery Score Predictor

## 🎯 Overview
This project applies machine learning regression techniques to predict an athlete's `Recovery_Score` for the following day. By analyzing daily metrics such as sleep, training duration, and training intensity, coaches and sports scientists can proactively manage athlete fatigue, prevent overtraining, and optimize performance.

---

## 🧠 Step-by-Step Methodology

### Step 1: Data Collection & Understanding
To predict recovery, we first need historical data containing daily logs of athlete activities and their subsequent recovery scores. 

**Expected Input Variables (Features):**
* `Athlete_ID`: Unique identifier for the athlete.
* `Sleep_Hours`: Total hours slept the previous night.
* `Training_Duration_Min`: Time spent training in minutes.
* `Training_Intensity`: Rate of Perceived Exertion (RPE) on a scale of 1-10.
* `Resting_Heart_Rate`: Morning resting heart rate (bpm).
* `Diet_Quality`: Subjective score of nutritional intake (1-10).

**Target Variable:**
* `Recovery_Score`: The actual measured recovery score the next morning (e.g., 1-100 scale, perhaps derived from Heart Rate Variability or a readiness questionnaire).

### Step 2: Feature Engineering
Raw data rarely tells the whole story. We create new, calculated columns (features) to help the algorithms find deeper patterns.

* **Training Load:** How hard did the athlete actually work?
  * *Formula:* `Training_Load = Training_Duration_Min * Training_Intensity`
* **Sleep Deficit:** How much rest is the athlete missing? Assuming an optimal 8 hours:
  * *Formula:* `Sleep_Deficit = 8 - Sleep_Hours` (If the result is negative, we can cap it at 0).
* **Rolling Averages:** Athletes don't just feel yesterday's workout; they feel the whole week's.
  * *Example:* `7_Day_Avg_Training_Load`

### Step 3: Data Preprocessing
Before feeding data to a model, it must be cleaned and formatted:
1. **Handling Missing Values:** Fill missing sleep or heart rate data using median values or forward-filling (carrying the previous day's number forward).
2. **Train/Test Split:** Divide the dataset. We'll use 80% of the data to *train* the models and 20% to *test* them on unseen data.
3. **Scaling:** Algorithms like Linear Regression perform better when all numbers are on a similar scale. We apply a `StandardScaler` to normalize features like duration and heart rate.

### Step 4: Model Selection & Training
We test multiple regression algorithms to see which learns the patterns best:

1. **Linear Regression:** The baseline model. It draws a straight line through the data. It assumes a simple, direct relationship (e.g., more sleep = strictly higher recovery).
2. **Random Forest Regressor:** An ensemble method that builds hundreds of "decision trees" and averages their predictions. It's excellent for capturing non-linear relationships (e.g., 8 hours of sleep is good, but 14 hours might indicate illness, not better recovery).
3. **XGBoost Regressor:** A highly optimized gradient boosting algorithm. It builds trees sequentially, with each new tree trying to correct the errors of the previous one. Often the highest performer in tabular data.

### Step 5: Model Evaluation
To know if our model is actually useful to a coach, we measure its errors using standard regression metrics:
* **Mean Absolute Error (MAE):** The average difference between the predicted score and the actual score. *(e.g., An MAE of 4 means our model's predictions are usually off by about 4 points on the 1-100 scale).*
* **Root Mean Squared Error (RMSE):** Similar to MAE, but heavily penalizes massive errors.
* **R-Squared ($R^2$):** Measures how much of the variance in the recovery score is explained by our inputs. A score closer to 1.0 is better.

---

## 🚀 How to Run the Project (Future Implementation)
*(Note: Update this section once your code is finalized)*

1. Clone the repository.
2. Install required packages: `pip install pandas scikit-learn xgboost matplotlib`
3. Place your raw data in the `data/` folder.
4. Run the preprocessing and training script: `python train_model.py`
5. View the output metrics and feature importance graphs in the `results/` folder.

## 📊 Business Value (Why this matters)
By deploying this model:
* **Coaches** can receive a morning dashboard predicting which athletes are in the "red zone."
* **Athletes** can adjust their daily load based on objective data rather than just "pushing through."
* **Teams** can reduce injury rates linked to cumulative fatigue.

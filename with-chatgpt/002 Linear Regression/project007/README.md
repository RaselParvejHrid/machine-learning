# Project 007 | Understanding Regression Metrics

Started on July 08, 2026

Completed on July 08, 2026

## Problem Statement

Using a small regression dataset (the built-in Diabetes dataset from scikit-learn is an excellent choice):

1. Load the dataset.
2. Split into training and testing sets.
3. Train a basic LinearRegression model.
4. Evaluate it using:
   * Mean Squared Error (MSE)
   * Root Mean Squared Error (RMSE)
   * Mean Absolute Error (MAE)
   * R² Score
5. In your README, explain:
   * What each metric measures.
   * Why MSE and RMSE penalize large errors more than MAE.
   * Which metric you think would matter most in a real-world application of your choice, and why.

Don't worry about fully understanding R² yet. We'll study it in depth in a later session. For now, simply compute it and observe its value.

# Solution

Taken from Gemini.

## 1. Understanding the Metrics

When evaluating a regression model, we want to know how close our predictions ($\hat{y}$) are to the actual targets ($y$). We use four core metrics to quantify this:

* **Mean Absolute Error (MAE)**
    * **What it measures:** The average absolute distance between predicted and actual values. It treats all errors linearly.
    * **Interpretation:** If your MAE is 42, your model's predictions are, on average, 42 units off from the actual values.
* **Mean Squared Error (MSE)**
    * **What it measures:** The average of the *squared* differences between predicted and actual values. 
    * **Interpretation:** Because it squares the errors, it is harder to interpret in the original units of your data, but it is highly sensitive to outliers.
* **Root Mean Squared Error (RMSE)**
    * **What it measures:** The square root of the MSE.
    * **Interpretation:** This brings the squared error metric back down to the original units of your target variable (like MAE), making it much easier to intuitively understand while retaining a sensitivity to large errors.
* **$R^2$ Score (Coefficient of Determination)**
    * **What it measures:** The proportion of the variance in the dependent variable that is predictable from the independent variables.
    * **Interpretation:** Ranging from $-\infty$ to $1$, a score of $1.0$ means the model perfectly predicts the data, while a score of $0.0$ means the model performs no better than a baseline model that always guesses the mean of the target variable.

---

## 2. Why MSE and RMSE Penalize Large Errors More Than MAE

The fundamental difference lies in the **mathematical operations** applied to the error terms. MAE treats errors linearly, while MSE and RMSE treat them quadratically.

Let's look at a quick comparison of how a small error versus a large error impacts MAE and MSE:

| Actual Value | Predicted Value | Absolute Error ($|y - \hat{y}|$) | Squared Error ($(y - \hat{y})^2$) |
| :--- | :--- | :--- | :--- |
| 100 | 98 (Small error) | **2** | **4** |
| 100 | 90 (Large error) | **10** | **100** |

### The Takeaway:
* In **MAE**, the large error (10) is exactly **5 times** worse than the small error (2).
* In **MSE**, the large error (100) becomes **25 times** worse than the small error (4). 

Because RMSE is simply the square root of MSE, the underlying mathematical penalization of outliers carries over. If your dataset contains rare but highly disruptive anomalies, MSE and RMSE will spike dramatically, forcing your model to prioritize fixing those large misses during training.

---

## 3. Real-World Application: Healthcare & Diabetes Monitoring

In a real-world application using this dataset—such as a clinical decision support tool predicting a patient's **blood glucose progression** over a year—the metric that matters most is **RMSE**.

### Why RMSE is the Priority Here:
In medicine, small errors are acceptable and expected, but **large errors can be catastrophic**. 

* If the model predicts a patient's blood sugar progression will be stable, but it actually spikes drastically (a huge prediction error), the patient might miss out on life-saving preventative treatment.
* Because **RMSE** heavily penalizes these massive misses, optimizing our model to minimize RMSE ensures the algorithm actively avoids making dangerous, far-off predictions.
* While MSE also penalizes large errors, **RMSE is preferred by clinicians** because its output is in the exact same units as the target variable (e.g., mg/dL), making the model's average expected risk transparent and easily understood by medical professionals.

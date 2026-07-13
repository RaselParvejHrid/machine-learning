# Project 008 | Exploring Linear Regression

Started on July 08, 2026

Completed on July 08, 2026

## Problem Statement

Using the built-in Diabetes dataset:

1. Train a LinearRegression model.
2. Display the learned coefficients (coef_) and intercept (intercept_).
3. Match each coefficient to its corresponding feature name.
4. Reflect on an important point:
   * Does a larger coefficient always mean a feature is more "important"? Why or why not? (Hint: think about feature scaling and correlation. We'll revisit this later.)

This project introduces an essential habit: don't stop after training a model— inspect what it learned.

## Solution
Taken from Gemini.

### Reflection: Feature Coefficients vs. Importance

#### Does a larger coefficient always mean a feature is more "important"?
**No, a larger coefficient does not inherently mean a feature is more important.** Two critical data characteristics alter or distort this relationship:

#### 1. The Effect of Feature Scaling
Coefficients are tied directly to the scale and units of the input features. If a feature is measured in large units (e.g., kilometers), its corresponding coefficient will be small. If the same feature is measured in small units (e.g., millimeters), the coefficient must scale up significantly to yield the same physical effect. 
* *Note on this dataset:* The scikit-learn diabetes dataset features are already mean-centered and scaled by the standard deviation times the number of samples. Because they are on a comparable scale, we can roughly compare magnitudes *within this specific model*. However, in unscaled real-world datasets, coefficient magnitude is completely arbitrary without proper standardization (like `StandardScaler`).

#### 2. Correlation and Multicollinearity
Linear regression models calculate the effect of an independent variable assuming all other variables are kept perfectly constant. When features are highly correlated with one another (as is common with blood serum measurements like `s1` through `s6`), the model struggles to determine which variable is actually driving the change. 
* This can cause coefficients to become highly unstable, throwing off massive opposing positive and negative weights (e.g., the high positive weight of `s5` and high negative weight of `s2`) purely to optimize the mathematical fit. Consequently, a large coefficient might just be an artifact of multicollinearity rather than a sign of true physical or clinical importance.

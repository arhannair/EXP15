# Experiment 15: Data Normalization and Standardization Using Python

**Name:** Arhan Nair  
**PRN:** 25070123169  


---

## 1. Theory

### Feature Scaling
Feature scaling is a critical preprocessing step used to normalize the range of independent variables or features of data. In machine learning, scaling ensures that features with large numerical ranges do not dominate those with smaller ranges, allowing algorithms to converge faster and perform more accurately.

### Key Scaling Techniques
The following methods were implemented in this experiment using the `scikit-learn` library:
* **Min-Max Scaling (Normalization)**: Rescales the data to a fixed range, usually 0 to 1. It is sensitive to outliers but useful when you know the distribution is not Gaussian.
    * Formula: $x_{new} = \frac{x - x_{min}}{x_{max} - x_{min}}$
* **Standard Scaling (Standardization)**: Rescales data so that it has a mean ($\mu$) of 0 and a standard deviation ($\sigma$) of 1. This technique is more robust to outliers and is preferred for algorithms that assume a normal distribution.
    * Formula: $z = \frac{x - \mu}{\sigma}$

---

## 2. Implementation Overview

### Academic Performance Dataset
The experiment utilized a student dataset containing numeric features such as **Age**, **Study_Hours**, and **Marks**.
* **Min-Max Scaling Implementation**: The "Marks" column was transformed using `MinMaxScaler`. For example, original marks like 85 and 92 were rescaled to a range between 0 and 1 (e.g., 0.44 and 0.83).
* **Standard Scaling Implementation**: The "Study_Hours" and "Marks" were processed using `StandardScaler`, centering the values around zero.

### E-commerce Order Dataset
A second implementation focused on order data with features like **Order_Value**, **Delivery_Time**, and **Distance_km**.
* **Normalization**: The "Order_Value" (ranging from 120 to 600) was normalized to the 0–1 range.
* **Standardization**: Distance and delivery times were standardized to have a unit variance, making them comparable despite having different original units.

---

## 3. Conclusion

This experiment highlights the importance of scaling numerical data to ensure that every feature contributes proportionately to the final analysis or model. Choosing between Normalization and Standardization depends on the specific requirements of the data distribution and the intended machine learning algorithm.

**Key Takeaways:**
* **Unit Uniformity**: Scaling allows for the direct comparison of features with different units, such as "Age" in years and "Marks" in percentages.
* **Algorithmic Performance**: Most machine learning estimators (like K-Means or SVM) require scaled features to avoid biased results toward larger magnitude numbers.
* **Tool Proficiency**: Utilizing `sklearn.preprocessing` provides an efficient, industry-standard way to handle these transformations through the `fit_transform()` method.

---

# Abalone Age Prediction

This project predicts the **age of abalone (rings)** using physical measurements from the Abalone dataset (~4,177 samples). Two models were evaluated: **Linear Regression** and **Random Forest**, with and without cross-validation.  

---

## Model Performance

| Model                        | Train / CV R²      | Validation R²       | Test R²  |
|-------------------------------|------------------|-------------------|---------|
| Linear Regression (length + height) | 0.587            | 0.158             | 0.261   |
| Random Forest (no CV)         | 0.587            | -0.377            | 0.261   |
| Random Forest (5-fold CV)     | 0.558 (mean CV)  | -                 | 0.551   |

---

## Insights

- **Linear Regression**:
  - Underperformed due to **limited features** and **linear assumptions**.  
  - Validation R² was low (0.158), showing underfitting.  

- **Random Forest without CV**:
  - High variance caused **unstable validation scores** (R² = -0.377).  
  - Test score similar to Linear Regression, not reliable.  

- **Random Forest with CV**:
  - Cross-validation stabilized performance (mean CV R² = 0.558).  
  - Test R² improved to 0.551, capturing **non-linear relationships** and **feature interactions** effectively.  
  - Using all relevant features (length, diameter, height, weights, sex) allows the model to exploit important patterns while handling correlated features.

**Conclusion:**  
Random Forest with cross-validation is the best-performing model for this dataset, while Linear Regression serves as a baseline. Cross-validation is essential to assess model stability and generalization, especially on small datasets.

---

**Author:** Ezekiel Ozimi  
[LinkedIn](https://www.linkedin.com/in/ezekiel-ozimi-05845193)

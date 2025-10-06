# 🍽️ Restaurant Menu Price Prediction (Texas)

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Regression-brightgreen.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

## 📘 Project Overview
This project aims to **predict the menu price of restaurant items** within the **State of Texas** using machine learning techniques.  
The analysis leverages detailed restaurant data — including customer ratings, cuisine types, price ranges, and regional demographics — to help businesses and investors make data-driven decisions about restaurant pricing and strategy.

Although the current analysis focuses on Texas due to computational efficiency, the same predictive framework can be **extended to other U.S. states** for wider market insights.

---

## 🎯 Business Objective
To empower restaurant owners and entrepreneurs with insights on:
- **Key factors influencing menu pricing**
- **Competitive pricing dynamics across Texas**
- **Opportunities for new restaurant ventures based on data-driven price predictions**

---
## Jupyter Notebook Link
- https://github.com/vijesh-mlai/MLAI_Mod_24/blob/main/prompt_III.ipynb
---

## 🧠 Methodology

### 1. Data Preparation
- Original dataset: ~5M rows (nationwide)
- Texas State subset: ~1.2M rows (Texas-focused)
- Sample Subset for Validating the Model: ~30K rows
- Preprocessing included:
  - Regex extraction for item quantities and units
  - Text normalization and cleaning
  - Feature derivation (`item_qty`, `item_unit`, `item_size_label`, `zip3`)
  - Mapping price ranges (`$`, `$$`, `$$$`, `$$$$` → numeric codes)

### 2. Feature Engineering
- **Numeric:** `score`, `review`, `price_range`, `item_qty`, `item_size_inch`
- **Categorical:** `restaurant_category`, `zip_code`, `item_unit`, `item_size_label`
- **Text:** TF-IDF transformation on `item_name`

### 3. Modeling
| Model | Description |
|:------|:-------------|
| **Linear Regression** | Baseline model with basic feature relationships |
| **Ridge Regression** | Regularized model to handle mild multicollinearity |
| **Lasso Regression** | Sparse model with higher regularization |
| **Random Forest** | Non-linear ensemble method with strong generalization |
| **XGBoost** | Gradient-boosted trees, best performance overall |

Evaluation metrics: RMSE, MSE, and R²  
Target variable (`menu_price`) was **log-transformed** for variance stabilization.

---

## ⚙️ Model Performance Summary

| Model | Key Characteristics | Test RMSE | R² (Test) | Remarks |
|:------|:--------------------|:----------|:-----------|:--------|
| Linear Regression | Moderate bias, limited ability to capture non-linear patterns | 6.33 | 0.36 | Serves as baseline |
| Ridge Regression | Similar to Linear Regression — minor improvement | 6.35 | 0.36 | Low multicollinearity |
| Lasso Regression | Strong underfitting due to high regularization | 7.78 | 0.04 | Coefficient shrinkage |
| Random Forest | Captures non-linear relations well; slight overfitting | 5.75 | 0.47 | Balanced performance |
| XGBoost | Best performing model — captures complex interactions | 5.06 | 0.59 | Mild overfitting observed |

---

## 🏁 Results

### 1️⃣ Main Takeaway
Machine learning models — particularly **XGBoost** and **Random Forest** — can effectively predict menu prices using both structured and text-based restaurant features.  
Text signals (from `item_name`) combined with categorical and numeric context significantly improved predictive accuracy.

### 2️⃣ Conclusions
- Combining structured and unstructured data improves prediction reliability.
- Log-transformation stabilized price skewness and boosted accuracy.
- Tree-based models outperformed linear ones due to non-linear relationships.
- The methodology is **scalable and generalizable** beyond Texas.

### 3️⃣ Business Recommendations
For customers and entrepreneurs exploring restaurant opportunities in Texas:
- **Cuisine Strategy:** Invest in cuisines showing strong customer retention and value alignment (e.g., fast casual, coffee, local comfort food).
- **Regional Pricing:** Assess ZIP-code clusters; urban and high-density areas support premium pricing.
- **Menu Planning:** Use model insights to price competitively without undervaluing popular items.
- **Market Gaps:** Identify categories with low supply but high predicted price stability.

### 4️⃣ Future Enhancements
- Expand model application to **nationwide data** for cross-state comparison.
- Integrate **time-series or seasonal features** for dynamic pricing.
- Upgrade text modeling using **BERT or Word2Vec embeddings**.
- Build an **interactive dashboard (Streamlit/Power BI)** for visualization.
- Incorporate **socioeconomic and delivery trend data** for better contextual pricing.

---

## 🧩 Tech Stack
- **Python:** pandas, NumPy, scikit-learn, XGBoost, matplotlib, seaborn  
- **Environment:** Jupyter Notebook / Google Colab / Anaconda 
- **Frameworks:** Scikit-learn Pipelines & ColumnTransformer  

---

## 📈 Impact
This project provides a **data-driven decision framework** to help restaurant owners, investors, and analysts:
- Predict item-level prices with improved accuracy  
- Identify profitable restaurant categories  
- Optimize menu pricing based on local market factors  

The approach delivers **scalable, interpretable, and actionable insights** applicable to any food delivery market.

---

## 👨‍💻 Author
**Vijeshkumar Vijayan**  
Capstone Project – Restaurant Menu Price Prediction


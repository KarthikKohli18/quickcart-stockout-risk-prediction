# QuickCart Stockout Risk Prediction

## 📌 Project Overview

QuickCart is an online grocery platform that needs to proactively identify products and store locations that are at risk of stockouts.

This project develops a supervised Machine Learning classification system that predicts daily stockout risk for each Store-SKU combination.

The model classifies inventory records into three categories:

- 🟢 Safe
- 🟡 At-Risk
- 🔴 Imminent

The main objective is to identify imminent stockout cases early enough for inventory teams to take preventive replenishment actions.

---

## 🎯 Objectives

- Predict daily stockout risk.
- Identify high-risk Store-SKU combinations.
- Analyze important factors affecting stockout risk.
- Compare multiple Machine Learning models.
- Generate actionable inventory alerts.
- Support proactive replenishment decisions.

---

## 📊 Dataset

The project uses information from:

- Stores
- SKUs
- Suppliers
- Daily inventory
- Events and festivals

Important variables include:

- Opening stock
- Units demanded
- Units sold
- Closing stock
- Reorder point
- Expected lead time
- Sales velocity
- Days of cover
- Supplier reliability
- Shelf life
- Perishability
- Festival relevance

---

## 🔧 Feature Engineering

Several additional features were created:

- Reorder Gap
- Days of Cover Ratio
- Stock-Demand Ratio
- Demand Gap
- Festival Flag
- Weekend Flag
- Day of Month
- Day of Week
- Perishable Indicator

---

## 🤖 Machine Learning Models

The following models were evaluated:

1. Dummy Classifier
2. Logistic Regression
3. Random Forest Classifier

A time-based train-validation-test methodology was used to avoid future-data leakage.

### Data Split

- Training: October 1–18, 2026
- Validation: October 19–23, 2026
- Final Test: October 24–30, 2026

---

## 🏆 Final Model

Logistic Regression was selected as the final operational model because the project prioritizes detecting **Imminent stockouts**.

### Final Test Performance

| Metric | Score |
|---|---:|
| Accuracy | 91.0% |
| Balanced Accuracy | 86.6% |
| Imminent Precision | 71.7% |
| Imminent Recall | 88.1% |
| Imminent F1-score | 79.1% |

The model correctly identified **674 out of 765 actual Imminent stockout cases**.

---

## 🔍 Important Risk Factors

The model indicates that stockout risk is strongly associated with factors such as:

- Lower days of inventory cover
- Perishable products
- Longer supplier lead times
- Festival relevance
- Higher demand pressure
- Lower supplier reliability

These insights can help inventory teams prioritize replenishment.

---

## 🚨 Business Impact

The prediction system can help QuickCart:

- Detect imminent stockouts earlier.
- Prioritize critical inventory.
- Improve replenishment decisions.
- Monitor unreliable suppliers.
- Prepare for increased demand during festivals.
- Reduce potential lost sales caused by stockouts.

---

## 📁 Repository Structure

```text
quickcart-stockout-risk-prediction/
│
├── data/
├── notebooks/
│   └── QuickCart_Stockout_Risk.ipynb
│
├── outputs/
│   ├── QuickCart_Final_Stockout_Predictions.csv
│   ├── QuickCart_Priority_Alerts.csv
│   ├── QuickCart_Urgent_Alerts.csv
│   ├── QuickCart_Store_Risk_Summary.csv
│   └── QuickCart_SKU_Risk_Summary.csv
│
├── README.md
└── requirements.txt

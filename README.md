# Telco Customer Churn Analysis & Prediction

## 1. Project Overview

Customer churn is a major challenge for telecommunications companies. Understanding churn patterns and identifying customers at risk of leaving can help businesses improve retention strategies.

This project explores customer churn, investigates factors associated with customer attrition, and compares machine learning models for churn prediction.

## 2. Business Objectives

- Identify customer characteristics associated with higher churn.
- Analyze relationships between contract type, tenure, internet service, and additional services.
- Build and compare classification models.
- Translate analytical findings into business recommendations.

## 3. Dataset

The dataset contains 7,043 customer records and 21 original columns.

- **Target variable:** `Churn`
- **Task:** Binary classification (`Yes` / `No`)
- **Churn rate:** 26.54%
- **Training set:** 80%
- **Validation set:** 20%

## 4. Tools & Technologies

- Python
- pandas
- scikit-learn
- Jupyter Notebook
- Exploratory Data Analysis (EDA)
- Data preprocessing and feature engineering
- Classification model evaluation

## 5. Exploratory Data Analysis

The analysis identified several patterns:

| Factor | Observed churn rate |
|---|---:|
| Month-to-month contract | 42.71% |
| One-year contract | 11.27% |
| Two-year contract | 2.83% |
| Fiber-optic internet | 41.89% |
| DSL internet | 18.96% |

The median tenure was 10 months for customers who churned and 38 months for customers who stayed.

Customers without Online Security also showed a higher churn rate.

These findings describe associations, not proven causes of churn.

## 6. Machine Learning Models

Three classification algorithms were evaluated:

1. Logistic Regression
2. Decision Tree
3. Random Forest

The preprocessing pipeline handled missing values, scaled numerical features, and encoded categorical features.

Models were evaluated using Accuracy, Precision, Recall, F1-score, and ROC-AUC.

## 7. Model Comparison

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.806 | 0.657 | 0.559 | 0.604 | 0.842 |
| Random Forest | 0.803 | 0.663 | 0.521 | 0.584 | 0.841 |
| Decision Tree | 0.798 | 0.635 | 0.567 | 0.599 | 0.830 |

Logistic Regression achieved the highest ROC-AUC and F1-score on the initial validation split. The results were relatively close, so further validation would be needed before selecting a final production model.

## 8. Overfitting Analysis

Random Forest performance was compared on the training and validation sets.

| Dataset | Accuracy | F1-score | ROC-AUC |
|---|---:|---:|---:|
| Train | 0.873 | 0.741 | 0.953 |
| Validation | 0.803 | 0.584 | 0.841 |

The performance gap, particularly in F1-score and ROC-AUC, suggests that the Random Forest model may be overfitting the training data. Its validation performance remains reasonable, but the results indicate that model generalization could be improved.

## 9. Business Insights & Recommendations

**Contract retention**

Customers with month-to-month contracts showed substantially higher churn. The company could investigate whether suitable long-term contract offers improve retention.

**Fiber-optic customers**

The higher observed churn rate among fiber-optic customers warrants further investigation into pricing, service quality, customer expectations, and technical support.

**Additional services**

The relationship between Online Security, Tech Support, and churn suggests investigating whether relevant service offerings could improve customer retention.

**Early customer lifecycle**

The shorter median tenure among churned customers suggests reviewing onboarding and early customer experiences.

These recommendations are hypotheses for further investigation, not proven causal effects.

## 10. Limitations

- The dataset is observational; associations do not establish causality.
- Validation results may vary across different data splits.
- Model performance on historical data does not guarantee performance on future customers.
- Business-specific decision thresholds and retention campaign economics have not yet been evaluated.

## 11. Conclusion

This project demonstrates an end-to-end customer churn analysis workflow, from exploratory data analysis and preprocessing to model comparison, overfitting assessment, and business interpretation.

The analysis identifies customer segments associated with higher churn and establishes baseline predictive models. Future work could focus on robust validation, business-specific prediction thresholds, and measuring the impact of retention interventions.

## Dataset Source

IBM Telco Customer Churn dataset, available through Kaggle.

The dataset is used

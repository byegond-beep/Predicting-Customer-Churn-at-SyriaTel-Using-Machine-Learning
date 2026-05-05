# Predicting Customer Churn at SyriaTel Using Machine Learning

## Overview
Customer churn is a critical challenge for telecommunications companies, as losing customers directly impacts revenue and growth. This project develops a machine learning classification model to predict whether a customer is likely to churn.

Using customer usage, billing, and service interaction data, the model identifies at-risk customers and key drivers of churn. With a strong focus on minimizing missed churners, this project supports proactive retention strategies to reduce revenue loss.

## Business Understanding
SyriaTel is experiencing customer churn, leading to revenue loss and increased acquisition costs. A key challenge is identifying customers who are likely to leave before they churn.

The goal of this project is to build a predictive model that enables early identification of at-risk customers, allowing the business to take timely action through targeted retention strategies.

A primary focus is minimizing missed churners, as these represent lost opportunities for intervention.

## Data Understanding
The dataset contains customer-level information, including:

- Account details (account length, service plans)  
- Usage patterns (day, evening, night, and international calls)  
- Billing information (charges across different periods)  
- Customer service interactions  

The target variable is 'churn', a binary indicator of whether a customer has left the service.

### Key Observations
- 3,333 records with no missing values  
- Approximately 14% churn rate (class imbalance)  
- Features capture both behavioral and service-related drivers of churn  


## Data Preparation
- Removed irrelevant features ('phone number', 'state')  
- Encoded categorical variables into numeric format  
- Split data into training and testing sets  
- Applied feature scaling for Logistic Regression  
- Prevented data leakage by fitting transformations only on training data  


## Modeling Approach

### Logistic Regression (Baseline)
- Simple and interpretable  
- High accuracy but poor churn detection  

### Decision Tree (Improved Model)
- Captures non-linear relationships  
- Significantly improved recall and overall performance  

### Tuned Decision Tree
- Reduced complexity through hyperparameter tuning  
- Did not significantly improve churn detection  

## Evaluation

Models were evaluated using:
- Accuracy  
- Precision  
- Recall (primary metric)  
- F1-score
- Confusion Matrix

**Why Recall Matters:**  
Missing a churner means losing a customer without intervention, directly impacting revenue.

### Model Comparison

| Model                | Accuracy | Precision | Recall | F1 Score |
|---------------------|----------|----------|--------|----------|
| Logistic Regression | 0.86     | 0.60     | 0.18   | 0.27     |
| Decision Tree       | 0.92     | 0.73     | 0.73   | 0.73     |
| Tuned Decision Tree | 0.92     | 0.73     | 0.71   | 0.72     |

## Key Insights
- Customers with frequent customer service calls are more likely to churn  
- High usage (minutes and charges) is associated with increased churn risk  
- Customer dissatisfaction is a major driver of churn  

## Conclusion
The Decision Tree model outperformed the Logistic Regression baseline, particularly in identifying churners.

- Logistic Regression missed over 80% of churners  
- Decision Tree correctly identified 73% of churners  
- Hyperparameter tuning did not provide meaningful improvement  

The Decision Tree model offers the best balance between performance and business value.

## Business Recommendations
SyriaTel can leverage the Decision Tree model to:

- Identify customers at high risk of churn  
- Implement targeted retention strategies such as:
  - Personalized offers  
  - Proactive customer support  
  - Service or pricing adjustments  

By focusing on early identification of churners, the company can reduce customer attrition and protect revenue.

## Next Steps
- Explore advanced models (e.g., Random Forest, Gradient Boosting)  
- Address class imbalance  
- Enhance feature engineering  
- Deploy the model for real-time prediction  
- Continuously retrain as customer behavior evolves  

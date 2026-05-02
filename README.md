# Predicting-Customer-Churn-at-SyriaTel-Using-Machine-Learning

## Overview

Customer churn is a critical challenge for telecommunications companies, as losing customers directly impacts revenue and growth. This project develops a machine learning classification model to predict whether a customer is likely to churn.

Using customer usage, billing, and service interaction data, the model identifies at-risk customers and key drivers of churn. With a strong focus on minimizing missed churners, this project enables proactive retention strategies to reduce revenue loss and improve customer satisfaction.

## Business Understanding

SyriaTel is experiencing customer churn, leading to revenue loss and increased costs associated with acquiring new customers. A major challenge for the company is the inability to accurately identify customers who are likely to leave before they churn.

The goal of this project is to develop a predictive model that identifies at-risk customers early, allowing SyriaTel to take timely action through targeted marketing, improved customer service, and personalized retention strategies.

A key focus is minimizing missed churners, as failing to identify these customers represents lost revenue and missed opportunities for intervention.

## Data Understanding

The dataset contains customer-level information, including:

- Account details (e.g., account length, service plans)
- Usage patterns (day, evening, night, and international calls)
- Billing information (charges across different periods)
- Customer service interactions

The target variable is `churn`, a binary variable indicating whether a customer has left the service.

### Key Observations

- The dataset contains 3,333 records with no missing values  
- The data is slightly imbalanced, with ~14% churners  
- Features include both behavioral and service-related variables, which are highly relevant for churn prediction  

## Data Preparation

To prepare the data for modeling:

- Removed irrelevant features such as `phone number` and `state`  
- Encoded categorical variables (e.g., international plan, voicemail plan) into numeric format  
- Split the dataset into training and testing sets  
- Applied feature scaling for Logistic Regression  
- Prevented data leakage by fitting transformations only on training data  



## Modeling Approach

An iterative modeling approach was used:

### 1. Logistic Regression (Baseline Model)
- Simple and interpretable  
- Provided a performance benchmark  
- High accuracy but poor recall for churners  

### 2. Decision Tree (Improved Model)
- Captures non-linear relationships  
- Significantly improved recall and overall performance  
- Better balance between precision and recall  

### 3. Tuned Decision Tree
- Hyperparameters adjusted to control complexity  
- Aimed to reduce overfitting  
- Did not significantly improve recall over the base Decision Tree  



## Evaluation

Models were evaluated using:

- Accuracy  
- Precision  
- Recall (primary metric)  
- F1-score  

**Why Recall Matters:**  
Missing a churner means losing a customer without intervention, which directly impacts revenue.

### Model Comparison

| Model                | Accuracy | Precision | Recall | F1 Score |
|---------------------|----------|----------|--------|----------|
| Logistic Regression | 0.86     | 0.60     | 0.18   | 0.27     |
| Decision Tree       | 0.92     | 0.73     | 0.73   | 0.73     |
| Tuned Decision Tree | 0.92     | 0.73     | 0.71   | 0.72     |


## Conclusion

The Decision Tree model outperformed the Logistic Regression baseline, particularly in identifying churners.

- Logistic Regression missed over 80% of churners  
- Decision Tree correctly identified 73% of churners  
- Hyperparameter tuning did not significantly improve performance  

The Decision Tree model provides the best balance between accuracy and recall, making it the most suitable model for this business problem.



## Business Recommendations

SyriaTel can use the Decision Tree model to:

- Identify customers at high risk of churn  
- Implement targeted retention strategies such as:
  - Personalized offers  
  - Proactive customer support  
  - Service or pricing adjustments  

By focusing on early identification of churners, the company can reduce customer attrition and protect revenue.

## Key Insights

- Customers with frequent customer service calls are more likely to churn  
- Usage patterns (minutes and charges) are strong indicators of churn  
- Customer dissatisfaction plays a major role in retention  

## Limitations

- Based on historical data; may not capture future behavior changes  
- Some relevant factors (e.g., customer satisfaction, competitor pricing) are not included  
- Slight class imbalance may affect model performance  

## Next Steps

- Explore advanced models (e.g., Random Forest, Gradient Boosting)  
- Perform feature engineering to improve predictions  
- Incorporate additional data sources  
- Deploy model for real-time churn monitoring  
- Continuously retrain model as customer behavior evolves  

## Repository Structure

- `notebook.ipynb` → Full analysis and modeling  
- `presentation.pdf` → Non-technical presentation  
- `README.md` → Project overview  

## Conclusion

This project demonstrates how machine learning can be used to identify at-risk customers early, enabling businesses to take proactive steps to reduce churn and improve customer retention.
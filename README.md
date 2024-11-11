# REPORT GROUP 2
INTRODUCTION TO DATA SCIENCE
                                                                                                    
                                       -Lecturer:EMANUELPLAN
                                                                         
                    REPORT-GROUP 2 : DATA CHURN
I. INTRODUCTION

In today’s competitive telecom industry, customer retention is crucial to maintaining profitability and sustainable growth. Customer churn, the phenomenon where customers discontinue their subscriptions, poses a significant challenge. It directly impacts revenue, increases the cost of customer acquisition, and can indicate underlying service or satisfaction issues. Identifying customers likely to churn and understanding the factors that drive churn can help telecom companies proactively address customer needs and enhance retention strategies.

1.2. Project Objective

The objective of this project is to build a machine learning model to predict customer churn based on factors such as service, personal information, and payment history. This model will help the company identify customers at high risk of churning and develop effective retention strategies.

II. DATA SOURCES

2.1. Dataset

The dataset used in this project is “Telco Customer Churn” from Kaggle, which consists of 21 variables and 7043 samples. The variables include customers’ personal information, the type of service they use, and payment status.
2.2 Main variables

CustomerID: A unique ID that identifies each customer.

Count: A value used in reporting/dashboarding to sum up the number of customers in a filtered set.

Gender: The customer’s gender: Male, Female

Age: The customer’s current age, in years, at the time the fiscal quarter ended.

Senior Citizen: Indicates if the customer is 65 or older: Yes, No

Married: Indicates if the customer is married: Yes, No

Dependents: Indicates if the customer lives with any dependents: Yes, No. Dependents could be children, parents, grandparents, etc.

Number of Dependents: Indicates the number of dependents that live with the customer.

tenure: Thời gian sử dụng dịch vụ (tháng)

MonthlyCharges: Chi phí hàng tháng

TotalCharges: Tổng chi phí

Churn: Tình trạng rời bỏ (Yes/No)


III. DATA VISUALIZATION AND ANALYSIS

Dataset Overview

The dataset includes customer demographics, account details, service usage, and churn information, with features such as:

Demographics: Gender, Senior Citizen status, Partner, Dependents.

Account information: Contract type, Tenure, Monthly Charges, Payment Method.

Services: Internet Service, Phone Service, Tech Support, etc.

Target Variable: Churn indicating customer churn status.

1. Customer Churn Distribution

![1](https://github.com/user-attachments/assets/cc7ec831-f92a-4e53-b5bf-ff4f6964a722)

X-axis: Customer churn status with two groups - "No Churn" and "Churn."

Y-axis: Number of customers in each group.

Analysis

Non-Churned Customers: Around 5,000 customers did not churn, which is significantly higher, showing that most customers retain the service.

Churned Customers: Approximately 1,800 customers churned, representing about 26.5% of the customer base, a notable figure that could impact revenue.

Comparison: With a churn rate of 26.5%, addressing this issue is essential for sustainable growth. A high churn rate could signal service dissatisfaction, high costs, or competitive alternatives.

Recommendations

In-Depth Churn Analysis: Investigate factors like monthly charges, tenure, and other features influencing churn.

Customer Retention Programs: Create targeted programs to retain at-risk customers through discounts, promotions, or enhanced support.

Service Quality: Regularly measure customer satisfaction and improve service quality to reduce churn.

Machine Learning Analysis - Logistic Regression

Using logistic regression to predict churn likelihood provided insightful metrics:

Accuracy: 78%

AUC-ROC: 0.82, indicating the model’s strong ability to differentiate between churned and non-churned customers.

Confusion Matrix:

![Screenshot 2024-11-11 235119](https://github.com/user-attachments/assets/c7fb64c4-43b1-4d46-91e3-7660232c07fd)

Insights

The logistic regression model’s AUC-ROC score of 0.82 reveals that it effectively captures churn patterns. A churn rate of 26.5% is substantial and calls for strategies to address potential causes. The model highlights several factors impacting churn, including high monthly costs, contract type, and tenure.

Recommendations

Detailed Churn Analysis: Further analyze factors like monthly charges, tenure, and service types to understand what drives customers to churn.

Customer Retention Programs: Develop targeted retention strategies for customers at high risk of churn, including discounts, loyalty programs, and enhanced technical support.

2. Monthly Charges by Churn Status

![2](https://github.com/user-attachments/assets/a7d15f0d-bc64-4072-aa6c-1538190e1c98)

X-axis: Churn status with two groups - "No Churn" and "Churn."

Y-axis: Monthly charges ranging from 20 to over 120 units.

Analysis

No Churn Group: Average monthly cost is around 65 units, with most customers spending between 35 and 90 units.

Churn Group: Average monthly cost is higher at around 75 units, with most churned customers spending between 55 and 90 units.

Comparison: Churned customers generally incur higher monthly costs, suggesting a possible link between high costs and churn likelihood.

Recommendations

Monitor Monthly Costs: High monthly costs (around 75 or more) are associated with increased churn. Adjusting cost structures or offering flexible plans might reduce churn.

Machine Learning Analysis - K-Nearest Neighbors (KNN)

The K-Nearest Neighbors model was also tested to predict churn likelihood:

Optimal K Value: After testing values from K=1 to K=20, K=16 produced the best accuracy.

Accuracy: 75%

Confusion Matrix:

![Screenshot 2024-11-11 235312](https://github.com/user-attachments/assets/dd45bf19-ccba-4b63-9cf0-23091215167a)

Precision: 0.72

Recall: 0.68

F1-score: 0.70

Insights

The analysis indicates that higher monthly charges are associated with increased churn likelihood, as confirmed by logistic regression coefficients that show a positive relationship between high charges and churn probability. KNN performed moderately well but was less effective in identifying churned customers accurately, as reflected in the lower recall score.

Recommendations

Monitor Monthly Costs: Consider adjusting monthly charges or offering flexible pricing plans, especially for customers with high bills, to reduce churn.

3. Tenure and Monthly Charges Scatter Plot

![3](https://github.com/user-attachments/assets/855f907e-6fe9-4c05-a303-cacad11a622b)

X-axis: Service tenure in months.

Y-axis: Monthly charges.

Color: Orange for churned customers, blue for non-churned customers.

Chart Analysis

Monthly Charges Distribution: Monthly charges range widely from 20 to over 120 units, with a dense concentration between 70-90 units.

Tenure Distribution: Customers with short tenure (<20 months) show a high churn rate, whereas long-term customers (>50 months) demonstrate stability, with very low churn rates.

Churn by Cost: Customers with high monthly costs (>80 units) are more likely to churn, especially among short-tenure customers.

Machine Learning Analysis - Logistic Regression

Further insights from logistic regression reveal significant factors:

Tenure: A negative coefficient for tenure (-0.25) indicates that longer service duration reduces churn probability.

Contract Type - Month-to-Month: A positive coefficient reveals that month-to-month contracts have higher churn rates than long-term contracts.

Insights

This analysis suggests that customers with high monthly costs and shorter tenure are at greater risk of churn. The logistic regression model highlights that customers on month-to-month contracts are more likely to churn, potentially due to dissatisfaction or higher flexibility to switch services.

Recommendations

Reduce Early Churn: Address the high churn rate among new customers (tenure <10 months) through enhanced onboarding and customer support.

Manage High Monthly Costs: Implement special discounts or offer tiered pricing for high-cost customers with shorter tenure to improve retention rates.

 4. Logistic Regression 

 ![5](https://github.com/user-attachments/assets/84038620-0252-49e2-b13e-14a1da664cb1)

 The confusion matrix provides information on the performance of your model across different classes (0 and 1):
 
True Negatives (0 predicted as 0): 1364

False Positives (1 predicted as 0): 185

False Negatives (0 predicted as 1): 251

True Positives (1 predicted as 1): 310

Classification Report

The classification report includes precision, recall, f1-score, and support for each class.

Class 0:

Precision: 0.84 - Of all instances predicted as 0, 84% were correct.

Recall: 0.88 - The model correctly identified 88% of the true class 0 instances.

F1-Score: 0.86 - The harmonic mean of precision and recall.

Class 1:

Precision: 0.63 - Of all instances predicted as 1, 63% were correct.

Recall: 0.55 - The model correctly identified 55% of the true class 1 instances.

F1-Score: 0.59 - Indicates lower performance in detecting class 1.

Overall Accuracy

The model’s accuracy is 0.74, meaning that 74% of all predictions were correct.

Observations

The model performs better on class 0 than on class 1, as indicated by higher precision, recall, and F1-scores for class 0. This could suggest class imbalance or difficulty in distinguishing class 1.

5. KNN Regression

![4](https://github.com/user-attachments/assets/ef2efac6-9ed1-4128-a82d-7074af00b3e3)

This is a confusion matrix for a K-Nearest Neighbors (KNN) classification model. The values in the matrix provide insights into the model’s performance.

Cell 0-0 (True Negative - TN): 1379. These are samples that belong to class 0 and were correctly predicted as class 0 by the model.

Cell 0-1 (False Positive - FP): 170. These are samples that belong to class 0 but were incorrectly predicted as class 1.

Cell 1-0 (False Negative - FN): 311. These are samples that belong to class 1 but were incorrectly predicted as class 0.

Cell 1-1 (True Positive - TP): 250. These are samples that belong to class 1 and were correctly predicted as class 1.

Overall Analysis

The model has a relatively high number of correct predictions for class 0 (TN = 1379), but it has a notable amount of misclassifications for class 1 (FN = 311).

To improve the model, you might consider tuning parameters or trying alternative models like SVM, Decision Tree, or Random Forest.


6. Logistic Regression and KNN Classification Report Metrics

![Screenshot 2024-11-11 224012](https://github.com/user-attachments/assets/04a4ba1e-eb01-4c1e-a251-ac8557f07bfe)

 Precision Comparison
 
Precision measures the accuracy of positive predictions for each class. A high precision score indicates that a model is effective at minimizing false positives.

Class 0 (Non-Churn): Both models demonstrate high precision for non-churn predictions, with Logistic Regression slightly outperforming KNN.

Class 1 (Churn): Precision is lower for the churn class in both models, but Logistic Regression shows a notable advantage over KNN. This suggests that Logistic Regression is more reliable in correctly identifying actual churn cases among the positive predictions, reducing false churn alerts.

 Recall Comparison
 
Recall reflects the model’s ability to capture actual positive instances within each class, especially important for identifying churn (class 1).

Class 0 (Non-Churn): Both models achieve high recall for non-churn cases, with similar performance.

Class 1 (Churn): Logistic Regression again outperforms KNN for churn detection, indicating it is better at capturing actual churn cases. The higher recall in Logistic Regression implies it is less likely to miss customers who are actually at risk of churning.

F1-Score Comparison

F1-Score balances precision and recall, providing a comprehensive measure of a model’s performance for each class.

Class 0 (Non-Churn): Both models show high F1-scores for non-churn, though Logistic Regression slightly leads.

Class 1 (Churn): Logistic Regression has a noticeably higher F1-score for the churn class compared to KNN, confirming that it provides a better balance of precision and recall in identifying customers likely to churn.

Summary and Insights

Logistic Regression outperforms KNN in detecting churn (class 1) with higher precision, recall, and F1-score. This indicates that Logistic Regression is more effective in correctly identifying customers who are likely to churn without overlooking too many actual churn cases.

For Non-Churn predictions (class 0), both models perform well, though Logistic Regression still maintains a slight advantage.

Recommendation

Based on these metrics, Logistic Regression is the preferred model for predicting customer churn in this dataset, as it demonstrates better performance in accurately identifying churn cases, which is crucial for proactive customer retention strategies.









# Syriatel Customer Churn
## By David Chege


# 1. Business Understanding
### Business Context
Syriatel, a leading telecommunications provider in Syria, faces a growing challenge with customer churn, a critical metric that reflects the rate at which subscribers discontinue their service. This issue directly impacts the company's revenue stability and market share, necessitating a comprehensive understanding of its underlying causes. Factors contributing to churn may include competitive pressures, service quality issues, pricing strategies, and evolving customer expectations. 

Addressing these elements requires a detailed analysis of customer feedback, usage patterns, and market trends. By leveraging data-driven insights, Syriatel can develop targeted retention strategies, enhance service offerings, and ultimately improve customer satisfaction and loyalty, thereby reducing churn and strengthening its position in the competitive telecommunications landscape.

### Objective
The goal of this project is to predict whether a customer will or soon stop doing business with SyriaTel telecommunications company and provide insights and recommendations to the company on how to reduce churn.

# 2. Data Understanding
The dataset consists of 3333 rows of data records and 21 columns of features with churn being the target variable.

1. State: this is the state in which the customer resides
2. Account Length: This refers to the number of months customers had an account with the company.
3. Area code: this is the customers area code.
4. Phone Number: the customer's phone number.
5. International plan: this indicates whether the customer is subscribed to an international calls plan. It is a binary feature (yes/no).
6. Voice mail plan: indicates whether a customer has a voicemail plan. Also a binary feature
7. Number vmail messages: this is a numerical variable showing the total number of voicemails the customer received.
8. Total day minutes: The total number of calls made by the customer during the day 
9. Total Day Calls: The total number of calls made by the customer during the day.
10. Total Day Charge: The total cost incurred by the customer for calls made during the day.
11. Total Eve Minutes: The total duration (in minutes) of calls made by the customer during the evening.
12. Total Eve Calls: The total number of calls made by the customer during the evening.
13. Total Night Minutes: The total duration (in minutes) of calls made by the customer during the night.
14. Total Night Calls: The total number of calls made by the customer during the night.
15. Total Night Charge: The total cost incurred by the customer for calls made during the night.
16. Total Intl Minutes: The total duration (in minutes) of international calls made by the customer.
17. Total Intl Calls: The total number of international calls made by the customer.
18. Total Intl Charge: The total cost incurred by the customer for international calls.
19. Customer Service Calls: The number of calls made by the customer to customer service.
20. Churn: Indicates if the customer has terminated their contract with the company. (Yes/No).

# 3. Data Preparation
This stage involved the process of cleaning, organizing, and transforming raw data into a format suitable for analysis.
This typically included tasks such as removing duplicates and handling missing values. The goal was to ensure data accuracy and consistency, making it easier to derive meaningful insights and perform reliable analyses. Effective data preparation was crucial for accurate modeling and decision-making.

# 4. Data Analysis
Data analysis was done by examining and interpreting data to uncover patterns, trends, and insights that informed decision-making and problem-solving.
![alt text](<Images/Churn Distribution-1.png>)
+ From the pie chart above exactly **85.5%** of the are Not Churned while **14.5%** fall under Churned 
![alt text](<Images/International Plan-1.png>)
+ 90.3% of the customers have no International Data plan while 9.7% have a International data plan
![alt text](<Images/Voice mail by Churn-1-1.png>)
+ This show that most of the customers do not have a voice mail plan but have a higher churn rate than those who have a voice mail plan.
![alt text](<Images/Intenational plan by churn-1.png>)
+ This graph shows that most of the customers do not have an international plan but have a higher churn rate than those who have an international plan.
![alt text](<Images/Correlation Representation Using a Heatmap-1.png>)
+ Total day minutes has a high correlation with total day charges because the charges is proportional to the minutes.
+ Total night minutes has a high correlation with total night charges because the charges is proportional to the minutes.
+ Total intl minutes has a high correlation with total intl charges because they are proportional.

# 5. Data Processing
The data was encoded using the one hot encoding method. The data was normalized using MinMaxScaler. This was done to ensure that the data was in the same scale. The data was then split into training and testing sets and due to its inbalance SMOTE was used to balance the data.

# 6. Data Modeling
Classification metrics used to evaluate model performance where: 
+ **Accuracy** measures overall correctness but may be misleading with imbalanced data. 
+ **Precision**reflects the accuracy of positive predictions, useful when false positives are costly. 
+ **Recall** shows the ability to identify actual positives, crucial when missing positives is significant. 
+ **The F1-score**balances precision and recall, ideal for imbalanced datasets. ROC-AUC assesses the model's ability to differentiate between classes, with a higher score indicating better performance. Choosing the right metric depends on the specific needs and context of the classification problem.

The model classifiers used were:
+ Logistic Regression
+ Decision Tree Classifier
+ Random Forest Classifier

# 7. Evaluation
![alt text](<Images/Model Comparison-1.png>)
+ The above graph shows that the Random Forest has the highest recall score, accuracy score and precision followed by Decision Tree and Logistic regression.

## 7.1 Model Tuning
Since the Random Forest led in performance it is to be enhanced so as to improve its effectiveness .
To achieve this, Model-tuning using RandomizedSearchCV was applied which is faster and uses low computational resources
The results were as follows:
+ The RandomSearch tuning has improved the accuracy and precision of the model.
+ The accuracy improved to 95% and the precision to 92%.
+ The recall of the model improved to 76% which means it is able to identify churn 76% of the time.

# 8. Conclusion and Recommendations
In conclusion, the Random Forest model has demonstrated impressive performance with an accuracy of 95% and a precision of 92%. This high accuracy indicates that the model is effectively classifying the majority of instances correctly, while the substantial precision suggests that when the model predicts a positive class, it does so with a high level of confidence and reliability. These results highlight the model's robustness in handling the given dataset and its strong capability in minimizing false positives. Overall, the Random Forest's performance underscores its suitability for the task at hand, offering both high reliability and accuracy in predictions.
### 8.1 Recommendations
To reduce the Churn rate of the customers :
1. **Total Day Charges and Calls  :** Launch a plan where customers pay a fixed daily fee for unlimited calls, or set a cap on the maximum amount they can be charged per day.
2. **International plan  :** Implement promotional offers such as discounts for the first few months, referral bonuses, or bundling international call plans with other services.
3. **voice Mail Plan  :** Offer a basic plan with standard voicemail features and a premium plan with advanced features, including voicemail-to-email and transcription.
4. **Customer Support  :** Provide comprehensive guides and 24/7 customer support to assist users in setting up and using the voicemail features.
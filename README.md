# Telco Customer Churn

## Introduction
Churn prediction is the process of identifying which consumers are most likely to stop using a service or to cancel their subscription.
It is important to be able to predict customers churn because it is actually expensive to get new customers than keeping existing ones.
Once we pinpointed the clients who are most likely to churn, we could find marketing strategy to increase the likelihood that the client will stay.

## Objective
Predict customers churn and analyze the factors that cause customer churn in the company. 

## Data Understanding
The raw data contains 7043 rows (customers) and 21 columns (features), which are:
1. customerID: Customer ID
2. gender: Whether the customer is a male or a female 
3. SeniorCitizen: Whether the customer is a senior citizen or not (1, 0)
4. Partner: Whether the customer has a partner or not (Yes, No)
5. Dependents: Whether the customer has dependents or not (Yes, No)
6. tenure: Number of months the customer has stayed with the company 
7. PhoneService: Whether the customer has a phone service or not (Yes, No)
8. MultipleLines: Whether the customer has multiple lines or not (Yes, No, No phone service)
9. InternetService: Customer’s internet service provider (DSL, Fiber optic, No)
10. OnlineSecurity: Whether the customer has online security or not (Yes, No, No internet service)
11. OnlineBackup: Whether the customer has online backup or not (Yes, No, No internet service)
12. DeviceProtection: Whether the customer has device protection or not (Yes, No, No internet service)
13. TechSupport: Whether the customer has tech support or not (Yes, No, No internet service)
14. StreamingTV: Whether the customer has streaming TV service or not (Yes, No, No internet service)
15. StreamingMovies: Whether the customer has streaming Movies service or not (Yes, No, No internet service)
16. Contract: Type of contract (Month-to-month, One year, Two year)
17. PaperlessBilling: Whether the customer use paperless billing or not (Yes, No)
18. PaymentMethod: Type of payment method (Electronic check, Mailed check, Bank transfer (automatic), and Credit card (automatic))
19. MonthlyCharges: How much is their monthly charges 
20. TotalCharges: How much is their total charges 
21. Churn: Our target feature, whether the customers churn or not (Yes, No)

## Methods
We will use various methods such as random forest with and without SMOTE (Synthetic Minority Oversampling Technique) 
and also XGBoost to make the classification modeling. Due to imbalance distribution on feature targets, we cannot use accuracy as evaluation metrics.
We use recall (sensitivity) because we want to know which customer who most likely to churn.

## Conclusion
1. The data does not contain major issues. There is no NULL values and duplicated rows. Overall, the minimum and maximum values make sense for each column. 
2. Most of the columns with continuous numerical values are asymmetric and from the boxplot we can not found any outlier in any numerical columns.
3. In terms of the target variable, there is an imbalance distribution. 
4. There are several tendency of customers who are more likely to churn:
- they don't have partner 
- they don't have dependants 
- they has phone service and use fiber optic as internet service 
- they didn't subscibe to any extra services 
- they has contract month-to-month basis
- they chose Paperless Billing 
- they used Electronic check 
- they are non senior citizen 
- they have shorter time subscribe the service (smaller tenure) 
- they have higher MonthlyCharges 
- they have lower TotalCharges
5. After doing the modeling, we can see that XGBoost is the most appropriate model for imbalanced data. 
But it should be noted, we have not done feature selection here at all. With feature selection, the result could be improved.
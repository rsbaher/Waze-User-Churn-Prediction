# Waze User Churn Prediction
The goal of this project is to create a prediction model that would be able to accurately predict which Waze users churn (ie. leave). 
The best model would be one that minimizes False Negatives, i.e. high recall score.

## Models Created
The following models were trained on the same training data set:
- Logistics Regression (LR)
- Random Forest Classifier (RFC)
- XGBClassifier (XGBC)

## Training Results
| **Model** |	**Accuracy** | **Precision** |	**Recall** |	**F1**	| 
| --------- | ------------ | ------------- | ----------- | -------- | 
| **LR** |	82.38 | 51.79 |	9.15 |	0.16	| 
| **RFC** |	81.86 | 46.17 |	13.55 |	20.92	|
| **XGBC** | 79.54 | 36.69 |	21.14 |	26.79	|

The XGBoost Classifier (XGBC) has the best Recall score during training.  

## Validation Results
| **Model** |	**Accuracy** | **Precision** |	**Recall** |	**F1**	| 
| --------- | ------------ | ------------- | ----------- | -------- | 
| **RFC** |	91.33 | 98.87 |	51.68 |	67.88	| 
| **XGBC** |	85.84 | 66.67 |	40.24 |	50.18	|	

The XGBoost Classifier (XGBC) had higher testing scores than validation scores.    

## Final Results
The XGBoost Classifier model was selected to see if their test scores improved or dropped.
The model's test scores were lower:  
- Accuracy: 78.78%
- Precision: 33.33%
- Recall: 19.72%
- F1: 24.78%


The top 5 Features involved in making the decisions for the model are shown in the table below with their importance scores.
|**Features**|**Importance Score**|
| ---------- | ------------------ |
| km_per_hour*	| 2779 |
| total_navigations_fav1	| 2098 |
| n_days_after_onboarding	| 2045 |
| percent_sessions_in_last_month*	| 2007 |
| km_per_driving_day* | 1947 |
*3 of the top 5 features were engineered.
 
### Next Steps  

The XGBC model could be improved. To do this we could try the following:
- Conduct feature engineering.
  _*Note: This is a more realistic next step_ 
- Improve Class Imbalance: Get more data where `label = churned` since most of the data is where `label = retained`.
- Get more data:
  - on the users such as demographic data and data regarding their trips.
  - multiple months to interpret
- Try other predictive models. _*Note: This is a more realistic next step_ 
  

# Task 3 – Customer Churn Prediction  

This project predicts **customer churn** (whether a customer will exit or stay) using machine learning models.  

## Dataset  
- File used: `Churn_Modelling.csv`  
- Target variable: `Exited` (1 = Churn, 0 = Not Churn)  
- Features: Customer demographics, account balance, tenure, credit score, etc.  

## Steps Followed  
1. **Data Preprocessing**  
   - Dropped irrelevant columns: `RowNumber`, `CustomerId`, `Surname`.  
   - Converted categorical features (`Geography`, `Gender`) using one-hot encoding.  
   - Scaled numerical features for consistency.  

2. **Model Training**  
   - Models trained:  
     - Logistic Regression  
     - Random Forest Classifier  
     - Gradient Boosting Classifier  
   - Hyperparameter tuning applied on **Random Forest** using GridSearchCV.  

3. **Evaluation Metrics**  
   - Accuracy  
   - F1-score (focus on churned customers = minority class)  
   - Classification report  

## Results  
- **Logistic Regression**: Accuracy = 0.7195, F1 = 0.4996 (weak on churn detection).  
- **Random Forest**: Accuracy = 0.8685, F1 = 0.5765 (better recall, strong for majority class).  
- **Gradient Boosting**: Accuracy = 0.8675, F1 = 0.5917 (balanced, but slightly weak recall).  
- **Tuned Random Forest (Best Model)**:  
  - Accuracy = 0.8470  
  - F1 = 0.6357  
  - Best Parameters: `{class_weight: balanced, max_depth: 10, min_samples_split: 5, n_estimators: 300}`  

### 🔥 Final Model  
The **Tuned Random Forest** performed best with an **F1 Score of 0.6357** and was saved as:  
```bash
final_churn_model.pkl



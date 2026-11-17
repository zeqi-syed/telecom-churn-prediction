# Telecom Customer Churn Prediction

Predicting which customers of a telecom operator will leave, and explaining why.

## The question
Out of about 2,850 customers, 15.7% left (churned). Can we spot them in advance from their usage data, and which factors matter most?

## What I did
- Cleaned the data: removed 300 duplicate rows and 2 rows with missing values
- Explored the data with correlation charts, histograms, box plots and churn rates by group
- Trained and tuned four models with 5-fold stratified cross-validation: Decision Tree, KNN, Random Forest and XGBoost
- Compared them on F1 and ROC-AUC, because the classes are imbalanced and accuracy alone would be misleading
- Explained the predictions with TreeInterpreter to see which features push a customer towards leaving

## Results
- **Complaints are the strongest signal:** customers who complained churned at 83%, compared with 10% for those who didn't.
- **Best model: Random Forest**, with a test F1 of 0.875, ROC-AUC of 0.98 and accuracy of 96%.

| Model | Test F1 | Test ROC-AUC | Test accuracy |
|---|---|---|---|
| Decision Tree | 0.80 | 0.89 | 0.94 |
| KNN | 0.87 | 0.95 | 0.96 |
| Random Forest | **0.875** | 0.98 | 0.96 |
| XGBoost | 0.84 | 0.98 | 0.95 |

## Files
- `churn_prediction.ipynb`: the full analysis, with outputs
- `data/customer_churn.csv`: the dataset

## Run it
```bash
pip install -r requirements.txt
jupyter notebook churn_prediction.ipynb
```

## Data
Iranian Churn Dataset, UCI Machine Learning Repository: https://archive.ics.uci.edu/dataset/563/iranian+churn+dataset

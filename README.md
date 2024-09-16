**Credit Card Fraud Detection Project**
**Project Overview:**

This project aims to build an accurate and reliable model for detecting fraudulent credit card transactions. With the imbalance between fraudulent and non-fraudulent 
transactions, this project utilizes advanced machine learning techniques, ensemble methods, and feature engineering to tackle the challenge.

**Table of Contents:**

1. Project Overview
2. Dataset
3. Problem Statement
4. Key Features
5. Libraries Used
6. Modeling and Pipeline
7. Evaluation Metrics
8. Why These Approaches?
9. Installation
10. Run the Project
11. Summary
12. Visualizations
13. Dataset
    
The dataset used for this project consists of transactional data with 23 columns and approximately 1.29 million entries.
The target column, is_fraud, indicates whether a transaction is fraudulent. 

**Problem Statement :**
The goal is to detect fraudulent transactions accurately while minimizing false negatives (undetected frauds). This requires:
1. Utilizing advanced classification models.
2. Optimizing the recall for detecting fraud while maintaining precision.
   
**Key Features:**
Some key features engineered to improve model performance include:

1. **Transaction Time Features**: Extracting hour, day, dayofweek, and weekend indicators from the trans_date_trans_time.
2. **Geographical Features:** The Haversine distance between the customer's location and the merchant's location.
3. **Log-transformed Transaction Amount:** Log transformation of the amt to reduce skewness.
4. **Transaction Frequency:** Calculating the number of transactions per credit card.
5. **Customer Age:** Calculating the customer's age based on their date of birth (dob).
   
**Libraries Used**
1. **Pandas, Numpy:** For data manipulation and analysis.
2. **Seaborn, Matplotlib:** For data visualization.
3.**Sklearn:** For building models and preprocessing data.
4. **XGBoost, RandomForest:** Ensemble learning classification methods.

 
 **Modeling and Pipeline**
 
1. **XGBoost:** Gradient boosting method, well-suited for handling complex non-linear relationships in data and imbalanced datasets.
2. **RandomForest**: A bagging method that reduces overfitting by training multiple decision trees.
3. **Decision Trees** : A basic classification Algorithm, to test out the lazy approach.

 **Handling Outliers**
The dataset has many Outliers, with very few false positives. To deal with this Z-Score was used.

 **Feature Engineering**
Several new features were created to improve the model’s ability to detect fraud:

1. **Transaction time-related features** like hour, day, month, and day of the week.
2. **Geographical distance between customer and merchant calculated** using the Haversine formula.
3. **Transaction frequency** by calculating how many transactions have been made using a credit card.
4. **All these engineered features were then passed through a preprocessing pipeline** to standardize numerical features and one-hot encode categorical features.

**Hyperparameter Tuning**
Used parameters such as max_depth, n_estimators, and regularization strengths.

**Evaluation Metrics**
The key metrics used for evaluating the models include:

1. **Accuracy:** Overall correctness of the model’s predictions.
2. **Precision:** Proportion of predicted frauds that are actually fraudulent.
3. **Recall:** Proportion of actual frauds that were correctly predicted (focuses on minimizing false negatives).
4. **F1-Score:** A balanced measure that considers both precision and recall.
5. **ROC AUC Score:** Evaluates the model’s ability to discriminate between fraudulent and non-fraudulent transactions.

   

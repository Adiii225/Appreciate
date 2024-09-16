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

**Problem Statement:**
The goal is to detect fraudulent transactions accurately while minimizing false negatives (undetected frauds). This requires:
1. Utilizing advanced classification models.
2. Optimizing the recall for detecting fraud while maintaining precision.
   
**Key Features and EDA:**
Some key features engineered to improve model performance include:

1. **Transaction Time Features**: Extracting hour, day, day week, and weekend indicators from the trans_date_trans_time.
2. **Customer to Merchant distance:** The Haversine distance between the customer's location and the merchant's location.
3. **Log-transformed Transaction Amount:** Log transformation of the amt to reduce skewness.
4. **Transaction Frequency:** Calculating the number of transactions per credit card.
5. **Customer Age:** Calculating the customer's age based on their date of birth (dob).

Correlation Matrix showcasing relationships between key features and fraud status:

<img width="823" alt="Screenshot 2024-09-16 at 10 41 52 AM" src="https://github.com/user-attachments/assets/59ccf9aa-975a-4e18-99c8-d645c2397218">

Transaction Amount Distribution by Fraud Status (KDE Plot):

1. This image shows the distribution of transaction amounts for both fraudulent and non-fraudulent transactions. It visually demonstrates that fraud transactions typically have different patterns from non-fraudulent ones.
   
<img width="825" alt="Screenshot 2024-09-16 at 10 42 27 AM" src="https://github.com/user-attachments/assets/370a48e4-a465-4a75-918e-a6da10faaa7c">

Amt Skewness before and after Log transformation:
<img width="855" alt="Screenshot 2024-09-16 at 10 49 02 AM" src="https://github.com/user-attachments/assets/af825cab-b67c-42e0-a25f-e8eec9339168">

After:
<img width="939" alt="Screenshot 2024-09-16 at 10 48 51 AM" src="https://github.com/user-attachments/assets/82b4184b-0fc8-4dd4-83a5-05e900720a53">


**Libraries Used**
1. Pandas, Numpy: For data manipulation and analysis.
2. Seaborn, Matplotlib: For data visualization.
3. Sklearn: For building models and preprocessing data.
4. XGBoost, RandomForest: Ensemble learning classification methods.

 
 **Modeling and Pipeline**
 
1. **XGBoost:** Gradient boosting method, well-suited for handling complex non-linear relationships in data and imbalanced datasets.
2. RandomForest: A bagging method that reduces overfitting by training multiple decision trees.
3. Decision Trees: A basic classification Algorithm, to test out the lazy approach.
How the decision tree works:
<img width="622" alt="Screenshot 2024-09-16 at 10 51 17 AM" src="https://github.com/user-attachments/assets/e6f5780a-1a6f-40a4-a13c-45e450e43507">

 **Handling Outliers**
The dataset has many Outliers, with very few false positives. To deal with this Z-Score was used.

<img width="593" alt="Screenshot 2024-09-16 at 10 52 18 AM" src="https://github.com/user-attachments/assets/4a0ca120-2ad7-4ba0-8640-bdca6aaf81b5">


**Hyperparameter Tuning**
Used parameters such as max_depth, n_estimators, and regularization strengths.

**Evaluation Metrics**
The key metrics used for evaluating the models include:

1. Accuracy: Overall correctness of the model’s predictions.
2. Precision: Proportion of predicted frauds that are fraudulent.
3. Recall: Proportion of actual frauds that were correctly predicted (focuses on minimizing false negatives).
4. F1-Score: A balanced measure that considers both precision and recall.
5. ROC AUC Score: Evaluate the model’s ability to discriminate between fraudulent and non-fraudulent transactions.


**Conclusion**
In a world where fraudulent transactions are always lurking, our model aspires to be the superhero, leveraging advanced machine learning and ensemble techniques to spot the bad guys (frauds) with accuracy! 🦸‍♂️💳 From clever feature engineering to stacking powerful models like XGBoost and RandomForest, we’ve turned raw transaction data into a fraud-busting machine. While handling the innocent outliers, with the help of the Z-score, we made sure our model caught fraudsters even when they try to blend in. 🔍💥

With precision, recall, and some funky visualizations, this project proves that when it comes to fraud detection, we aim to get it covered! 🌟

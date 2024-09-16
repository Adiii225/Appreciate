# **Credit Card Fraud Detection Project**

## **Project Overview** 📊

This project aims to build an accurate and reliable model for detecting fraudulent credit card transactions. Given the imbalance between fraudulent and non-fraudulent transactions, we utilize advanced machine learning techniques, ensemble methods, and feature engineering to tackle the challenge efficiently.

---

## **Table of Contents** 📑

1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Problem Statement](#problem-statement)
4. [Key Features](#key-features-and-eda)
5. [Libraries Used](#libraries-used)
6. [Modeling and Pipeline](#modeling-and-pipeline)
7. [Evaluation Metrics](#evaluation-metrics)
8. [Why These Approaches?](#why-these-approaches)
9. [Installation](#installation)
10. [Run the Project](#run-the-project)
11. [Summary](#summary)
12. [Visualizations](#visualizations)
13. [Dataset](#dataset)

---

## **Problem Statement** 📝

The goal is to detect fraudulent transactions accurately while minimizing false negatives (undetected frauds). This requires:
1. Utilizing advanced classification models.
2. Optimizing the recall for detecting fraud while maintaining precision.

---

## **Key Features and EDA** 🔍

Some key features engineered to improve model performance include:

1. **Transaction Time Features**: Extracting `hour`, `day`, `dayofweek`, and `weekend` indicators from `trans_date_trans_time`.
2. **Customer to Merchant Distance**: The Haversine distance between the customer's location and the merchant's location.
3. **Log-Transformed Transaction Amount**: Log transformation of the `amt` to reduce skewness.
4. **Transaction Frequency**: Calculating the number of transactions per credit card.
5. **Customer Age**: Calculating the customer's age based on their date of birth (`dob`).

---

**Correlation Matrix** showcasing relationships between key features and fraud status:

<img width="823" alt="Screenshot 2024-09-16 at 10 41 52 AM" src="https://github.com/user-attachments/assets/59ccf9aa-975a-4e18-99c8-d645c2397218">

**Transaction Amount Distribution by Fraud Status (KDE Plot)**:

This image shows the distribution of transaction amounts for both fraudulent and non-fraudulent transactions, demonstrating that fraud transactions typically have different patterns from non-fraudulent ones.

<img width="825" alt="Screenshot 2024-09-16 at 10 42 27 AM" src="https://github.com/user-attachments/assets/370a48e4-a465-4a75-918e-a6da10faaa7c">

**Amt Skewness Before and After Log Transformation**:
- Before:

<img width="855" alt="Screenshot 2024-09-16 at 10 49 02 AM" src="https://github.com/user-attachments/assets/af825cab-b67c-42e0-a25f-e8eec9339168">

- After:

<img width="939" alt="Screenshot 2024-09-16 at 10 48 51 AM" src="https://github.com/user-attachments/assets/82b4184b-0fc8-4dd4-83a5-05e900720a53">

---

## **Libraries Used** 📚

1. Pandas, Numpy: For data manipulation and analysis.
2. Seaborn, Matplotlib: For data visualization.
3. Sklearn: For building models and preprocessing data.
4. XGBoost**, RandomForest: Ensemble learning classification methods.

---

## **Modeling and Pipeline** ⚙️

1. **XGBoost**: A gradient boosting method, well-suited for handling complex non-linear relationships in data and imbalanced datasets.
2. **RandomForest**: A bagging method that reduces overfitting by training multiple decision trees.
3. **Decision Trees**: A basic classification algorithm, to test out the lazy approach.

**How the decision tree works**:

<img width="622" alt="Screenshot 2024-09-16 at 10 51 17 AM" src="https://github.com/user-attachments/assets/e6f5780a-1a6f-40a4-a13c-45e450e43507">

---

## **Handling Outliers** 🚨

The dataset has many outliers, with very few false positives. To deal with this, the **Z-Score** method was used.

<img width="593" alt="Screenshot 2024-09-16 at 10 52 18 AM" src="https://github.com/user-attachments/assets/4a0ca120-2ad7-4ba0-8640-bdca6aaf81b5">

---

## **Hyperparameter Tuning** 🔧

The models were fine-tuned using parameters such as `max_depth`, `n_estimators`, and regularization strengths to optimize performance.

---

## **Evaluation Metrics** 📏

The key metrics used for evaluating the models include:

1. Accuracy: Overall correctness of the model’s predictions.
2. Precision: Proportion of predicted frauds that are actually fraudulent.
3. Recall: Proportion of actual frauds that were correctly predicted (minimizing false negatives).
4. F1-Score: A balanced measure that considers both precision and recall.
5. ROC AUC Score: Evaluate the model’s ability to discriminate between fraudulent and non-fraudulent transactions.

---

## **Conclusion** 📘

In a world where fraudulent transactions are always lurking, our model aspires to be the superhero, leveraging advanced machine learning and ensemble techniques to spot the bad guys (frauds) with accuracy! 🦸‍♂️💳 From clever feature engineering to stacking powerful models like XGBoost and RandomForest, we’ve turned raw transaction data into a fraud-busting machine. While handling the innocent outliers with the help of the Z-Score, we made sure our model caught fraudsters even when they tried to blend in. 🔍💥

With precision, recall, and some funky visualizations, this project proves that when it comes to fraud detection, we aim to get it covered! 🌟

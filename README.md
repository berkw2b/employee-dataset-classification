# Employee Dataset Prediction & Classification

This repository contains a comprehensive data science project aimed at predicting employee attrition (whether an employee will leave the company) using various machine learning algorithms.

##  Project Overview
The goal of this project is to analyze demographic and professional attributes to predict the `LeaveOrNot` target variable. The study involves extensive Exploratory Data Analysis (EDA), dimensionality reduction using PCA, and a comparison of 8 different classification models.

##  Dataset
The dataset is sourced from Kaggle: [Employee Dataset](https://www.kaggle.com/datasets/tawfikelmetwally/employee-dataset/data).
It consists of **4,653 observations** and **9 features**, including:
* **Education**: Bachelor's, Master's, etc.
* **Joining Year**: The year the employee joined the company.
* **City**: Office location.
* **Payment Tier**: Salary level categorization.
* **Experience in Current Domain**: Years of experience in the current field.
* **LeaveOrNot**: Target variable (0: **Stayed**, 1: **Left**).

##  Key Steps
1. **Exploratory Data Analysis (EDA):** Visualizing distributions, handling categorical variables, and checking for missing values.
2. **Preprocessing:** Feature scaling using `StandardScaler` and encoding categorical data.
3. **Dimensionality Reduction:** Applying **Principal Component Analysis (PCA)** to handle feature complexity.
4. **Modeling:** Implementing and comparing the following algorithms:
    * Logistic Regression
    * Support Vector Machines (SVM)
    * Decision Tree
    * Random Forest
    * Gradient Boosting 
    * Neural Networks
    * Catboost
    * LightGBM

##  Results & Performance
After a comprehensive comparison, **Random Forest** was selected as the final model due to its superior performance in both accuracy and stability.

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **Random Forest** | **0.8711** | **0.8878** | **0.7150** | **0.7928** |
| CatBoost | 0.8625 | 0.8404 | 0.7406 | 0.7873 |
| SVM | 0.8582 | 0.9159 | 0.6468 | 0.7582 |
| MLP (Neural Net) | 0.8539 |0.8739 | 0.6718 | 0.7597 |
| Gradient Boosting |	0.8453 | 0.8636 |	0.6531 | 	0.7437 |
| LightGBM |	0.8378 | 	0.8393 | 0.6531 | 0.7346 | 
| Decision Tree | 	0.8292 | 	0.8368 | 	0.6250 | 	0.7155 |
| Logistic Regression| 0.7067 | 0.6192 | 0.3812 | 0.4719 |


##  Key Insights

* **Logistic Regression** : As predicted in the PCA analysis, it yields the lowest results, achieving only a 70% accuracy rate due to its linear structure.
* **Support Vector Machines (SVM) and Neural Networks (MLP)** : They have successfully identified complex patterns in the data, achieving 85% accuracy.
* **Catboost and Gradient Boosting** : As tree-based models, they again achieved high scores in the ~86% range.
#### Interpreting Metrics
* **Precision** : Our SVM and Random Forest models are correct 91% of the time when they predict that an employee will leave the company. This means that our model does not generate “false positives” and does not classify anyone as high-risk without being certain.
* **Recall** : This is the lowest score achieved. What this means is: If there are 100 people who will actually leave the company, our model can identify only 71 of them, while it incorrectly predicts that the remaining 29 will not leave.
* **F1-Score** : This is the most reliable metric that reflects the balance between Precision and Recall.
### Why Choose Random Forest as the Final Model?
* It leads by a wide margin in terms of accuracy and F1 score.
* Thanks to its structure that avoids overfitting, it can perform consistently on the company’s data in the coming years.
* Using **feature importance** , it can transparently explain why an employee left.

## Installation
To run this project locally, clone the repository and install the dependencies:

```bash
git clone [https://github.com/berkw2b/employee-dataset-classification.git](https://github.com/berkw2b/employee-dataset-classification.git)
cd employee-dataset-classification
pip install -r requirements.txt

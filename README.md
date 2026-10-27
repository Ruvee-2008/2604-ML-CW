#**CM2604 Machine Learning — Telco Customer Churn Prediction**
Project Overview

This project uses the Telco Customer Churn dataset to investigate whether a telecommunications customer is likely to leave the company. The task is a binary classification problem, where the target variable is Churn (Yes or No).

Dataset

The dataset contains 7,043 customer records and 21 columns, including customer information, services, contract details, charges, and churn status.

During the initial exploratory data analysis (EDA), the following findings were noted:

Approximately 26.54% of customers had churned, while 73.46% had not.
The TotalCharges column contained 11 blank entries, which require appropriate handling during preprocessing.
Customers with month-to-month contracts showed a higher churn rate than customers with longer-term contracts.
Project Objectives
Explore and understand the dataset using EDA and visualisations.
Prepare the data for machine learning.
Build classification models to predict customer churn.
Evaluate and compare model performance using suitable classification metrics.
Consider relevant limitations and ethical issues when using customer data and predictions.
Data Preparation

The modelling workflow includes the following preprocessing steps:

Remove customerID from the predictive features because it is an identifier.
Convert TotalCharges to a numeric data type and handle invalid or missing values.
Impute missing numerical values using the median.
Impute missing categorical values using the most frequent category.
Scale numerical features using StandardScaler.
Encode categorical features using OneHotEncoder.
Combine these operations using a ColumnTransformer and Pipeline.
Split the dataset into 80% training data and 20% testing data, using stratification to preserve the approximate churn-class proportions.

The preprocessing pipeline is fitted on training data and then applied to test data to help avoid data leakage.

Machine Learning Models

The coursework requires the implementation and comparison of these classifiers:

K-Nearest Neighbours (KNN) — predicts a class using nearby training examples.
Logistic Regression — estimates the probability of a customer belonging to a class.
Random Forest — combines predictions from multiple decision trees.

Hyperparameter tuning is carried out using GridSearchCV and cross-validation. Model settings are selected based on a defined evaluation metric, with the F1-score for the churn class (Yes) used in the current tuning workflow.

Evaluation Metrics

The models are evaluated using:

Accuracy: proportion of all predictions that are correct.
Precision: among customers predicted to churn, the proportion who actually churned.
Recall: among customers who actually churned, the proportion correctly identified.
F1-score: harmonic mean of precision and recall.
Classification report: per-class precision, recall, F1-score, and support for both Yes and No.
Tools and Libraries
Python
Pandas
Scikit-learn
Jupyter Notebook or Google Colab
Matplotlib and Seaborn for EDA visualisations, if used in the notebook
Git and GitHub for version control
How to Run
Clone or download this repository.
Open the notebook in Jupyter Notebook or Google Colab.
Ensure the Telco Customer Churn CSV file is available at the path used in the notebook.
Run the notebook cells in order, starting with the imports and data loading.
Review the EDA, preprocessing, model training, evaluation, and comparison outputs.

If running locally, install the required libraries as needed, for example:

pip install pandas scikit-learn matplotlib seaborn jupyter
Results

The notebook contains the experimental results for the models. Update this section after all three models have been evaluated using the same test set and metrics, and include the final comparison of their accuracy, precision, recall, and F1-score. Clearly distinguish cross-validation scores used during tuning from final test-set scores.

Limitations and Future Improvements
Model performance depends on the quality and representativeness of the available dataset.
The dataset has more No than Yes outcomes, so accuracy should not be considered alone.
Future work can include further hyperparameter tuning, additional evaluation, model comparison, and monitoring for changes in customer behaviour.
Churn predictions should support, rather than replace, informed business decisions and should be used responsibly

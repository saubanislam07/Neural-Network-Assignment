Project Summary: Bank Marketing Term Deposit Prediction

Project Objective
The goal of this project was to build a Logistic Regression model to predict whether a bank customer will subscribe to a term deposit. This helps the bank optimize its marketing campaigns by targeting the most promising candidates based on their demographics and past banking behavior.


Data Preprocessing
I used the "Bank Marketing Data Set" and prepared the data for machine learning with the following steps:
Loading: Loaded the CSV using Pandas, specifying a semicolon (sep=';') delimiter.
Encoding: Mapped the target variable (y) to binary values (1 for yes, 0 for no). Applied One-Hot Encoding (get_dummies) to convert categorical text features (like 'job' and 'marital') into numbers.
Scaling: Standardized the numerical features using StandardScaler to ensure balanced model training.


Model Architecture
I implemented a Logistic Regression model using scikit-learn. The dataset was split into an 80% training set and a 20% testing set to properly evaluate the model on unseen data. The model was trained with max_iter=1000 to ensure proper convergence.


Evaluation & Findings
Accuracy: The model achieved an overall accuracy of ~90%.

Class Imbalance: Because the dataset has significantly more "no"s than "yes"s, the model is slightly conservative when predicting successful subscriptions (Precision: 0.65, Recall: 0.34 for Class 1).

ROC AUC: The model achieved a high ROC AUC score of 0.904, proving it is highly effective at distinguishing between customers who will and will not subscribe, performing vastly better than a random guess.
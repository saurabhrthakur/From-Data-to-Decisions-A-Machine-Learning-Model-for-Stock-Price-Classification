Classification Using Decision Tree
1. Overview
This document describes the process of performing classification on a stock dataset using a Decision Tree classifier. The target variable (CLOSED_PRICE) is derived from the difference between the CLOSE and PREVCLOSE columns, and it is discretized into categorical labels: "Decrease," "No Change," and "Increase." The model's performance is evaluated based on accuracy and other classification metrics.

2. Data Preparation

    2.1 Loading the Dataset
    The dataset is loaded from a CSV file using the pandas library. The dataset contains various stock market-related features, including OPEN, HIGH, LOW, CLOSE, PREVCLOSE, etc.

    2.2 Creating the Target Variable
    The target variable, CLOSED_PRICE, is calculated by subtracting PREVCLOSE from CLOSE. This variable is then discretized into three categories:
    Decrease: When CLOSE is less than PREVCLOSE.
    No Change: When CLOSE is approximately equal to PREVCLOSE.
    Increase: When CLOSE is greater than PREVCLOSE.
    
    2.3 Defining Features and Target
    The features (X) are all columns except for CLOSE, PREVCLOSE, CLOSED_PRICE, and CLOSED_PRICE_BINNED. The target variable (y) is the discretized CLOSED_PRICE_BINNED.
    
    2.4 Preprocessing Categorical Features
    Categorical columns (e.g., SERIES) are encoded using LabelEncoder.

3. Model Building and Training

    3.1 Splitting the Dataset
    The dataset is split into training and testing sets using an 80-20 split.
    
    3.2 Initializing and Training the Decision Tree Classifier
    A Decision Tree classifier is initialized and trained on the training dataset.

4. Model Evaluation

    4.1 Making Predictions
    Predictions are made on the test dataset using the trained Decision Tree model.
    
    4.2 Evaluating the Model
    The model's performance is evaluated using accuracy and a detailed classification report, which includes precision, recall, and F1-score.
    
    4.3 Results
    The Decision Tree model achieved an accuracy of 51% on the test set. The classification report provides detailed metrics for each class ("Decrease," "No Change," and "Increase"). 
    The "No Change" category had very few instances and was not predicted correctly by the model, resulting in low recall and F1-scores.

5. Conclusion
    The Decision Tree classifier struggled to accurately predict the CLOSED_PRICE categories, particularly the "No Change" category. This indicates that the model might benefit from
    further tuning or using more sophisticated models like Random Forest or Gradient Boosting. Additionally, the imbalance in the target categories suggests that resampling techniques
    or feature engineering might improve performance.

Here is the Google Colab link: https://colab.research.google.com/drive/1Dvk3JvY-abkShvKpJeB17fGonTzROP8y?usp=sharing

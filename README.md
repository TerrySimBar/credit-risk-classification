# credit-risk-classification
<br>
A supervised machine learning project that uses SciKit-learn's `LogisticRegression` and Imbalanced-learn's `RandomOverSampler` to build an effective logistic regression model to predict the creditworthiness of borrowers in two classes: healthy loans (Class 0) and high-risk loans (Class 1). 
<br>  
<br>
<br>

<img src="/images/class_report_original.png" alt="Classification report for original data" width="800"/>
<br>
<br>
<br>

<img src="/images/class_report_resample.png" alt="Classification report for resampled data" width="800"/>
<br>
<br>
<br>

## Table of Contents
### Overview
### Requirements & Dependencies
### Project Structure
### Discussion of Results
### Usage
### Contributing
### License
<br>

### Overview  
The following analysis is based on the classification reports for the original data and the resampled data. The purpose of the analysis is to determine if the resampled data improves the model's performance. The data set contains information about borrowers' loan sizes, interest rates, incomes, debt to income ratios, number of accounts, derogatory marks, total debt, and loan status. The goal is to build a model that effectively predicts the creditworthiness of borrowers. The original data set is imbalanced with 75,036 healthy loans (Class 0) and 2,500 high-risk loans (Class 1). It is therefore useful to resample the data with `RandomOverSampler` and then check if the resampled data improves the model's performance.  

The project uses SciKit-learn and RandomOverSampler to achieve the following crucial steps:

- Use `train_test_split` to create training and testing data.   
- Use `LogisticRegression` to fit the training data and make predictions using the testing data.    
- Generate the confusion matrix, classification report, and balanced accuracy score for the model.  
- Use `RandomOverSampler` to resample the data.
- Analyze the results of the model and compare the results with the original model to determine if the oversampling the data improves the model's performance.

<br>

### Requirements & Dependencies
This project uses the following software and Python libraries:    

Python (version 3.10.9)

Pandas (version: 2.0.3)

NumPy (version: 1.24.3)

Sci-Kit Learn (version: 1.3.0)

Imbalanced-learn (version: 0.10.1)

<br>

### Project Structure
<br>

#### Original Data
1. **Set up dependencies and read/preview the data**

     The data is read from the `lending_data.csv` file and previewed.     

2. **Separate the data into labels and features** 
    Set the `loan_status` column as the target (y) and all other columns as features (X).   

3. **Split the data into training and test datasets** 
    Use `train_test_split` to split the data into training and testing datasets.

4. **Create and instance of the Logistic Regeression Model** 
    Use `LogisticRegression` to create an instance of the Logistic Regression model.    

5. **Fit the model to the data and make predictions** 
    Use `fit` to fit the model to the training data.
    Use `predict` to make predictions with the testing data. 

6. **Evaluate the models performance** 
    Use `balanced_accuracy_score` to generate the balanced accuracy score, `confusion_matrix` to generate the confusion matrix, and `classification_report_imbalanced` to generate the classification report, to get the values needed to evaluate the model's performance. 

<br>

#### Resampled Data   

1. **Resample the data**

    Create an instance of `RandomOverSampler` and resample the data to address the imbalance in the data.   

2. **Repeat the steps above and evaluate the model's performance on the resampled data**    

<br>  

### Discussion of Results

#### Model 1: Original Data  

- **Precision**
Healthy Loan (Class 0): 1.00
Precision of 1.00 indicates that when the model predicts a healthy loan, it is correct every time.

    High-Risk Loan (Class 1): 0.87
    Precision of 0.87 means that when the model predicts a high-risk loan, it is correct about 87% of the time.


- **Recall (Sensitivity)**
Healthy Loan (Class 0): 1.00
Recall of 1.00 indicates that the model correctly identifies all instances of healthy loans.

    High-Risk Loan (Class 1): 0.89
    Recall of 0.89 means that the model captures about 89% of the actual high-risk loans, but misses about 11% of the actual high-risk loans.   

- **F1-Score**
Healthy Loan (Class 0): 1.00
F1-score of 1.00 is remarkable and a perfect balance between precision and recall for Class 0. 

    High-Risk Loan (Class 1): 0.88
    F1-score of 0.88 is a good balance between precision and recall for Class 1.

- **Accuracy**
Overall accuracy is 0.99, indicating that 99% of all predictions (both true positives and true negatives) were correct.

- **Summary**
The model performs exceptionally well for predicting healthy loans (Class 0) with high precision, recall, and F1-score.
For high-risk loans (Class 1), the model performs with lower precision compared to Class 0.
In general, the model is highly accurate and effective, especially in identifying healthy loans. 
<br>

#### Model 2: Resampled Data  

- **Precision**
Healthy Loan (Class 0): 1.00
Precision of 1.00 indicates that when the model predicts a healthy loan, it is correct every time.

    High-Risk Loan (Class 1): 0.87
    Precision of 0.87 means that when the model predicts a high-risk loan, it is correct about 87% of the time.


- **Recall (Sensitivity)**
Healthy Loan (Class 0): 1.00
Recall of 1.00 indicates that the model correctly identifies all instances of healthy loans.

    High-Risk Loan (Class 1): 1.00
    Recall of 1.00 means that the model correctly identifies all instances of high-risk loans.   

- **F1-Score**
Healthy Loan (Class 0): 1.00
F1-score of 1.00 is a perfect balance between precision and recall for Class 0. 

    High-Risk Loan (Class 1): 0.93
    F1-score of 0.93 is a very good balance between precision and recall for Class 1.

- **Accuracy**
Overall accuracy is 1.00, indicating that 100% of all predictions (both true positives and true negatives) were correct.

- **Summary**
The model shows exceptional performance in predicting healthy loans (Class 0) with high precision, recall, and F1-score.
For high-risk loans (Class 1), the model shows improved performance, compared to the model for the original data.    
In general, the model is more accurate and effective than the model for the original data. 

#### Recommendations
The model for the resampled data improved in accuracy from 0.99 to 1.00, and the F1-score and recall for high-risk loans improved from 0.88 to 0.93 and 0.89 to 1.00, respectively. However, the precision for healthy and high-risk loans remained the same at 1.00 and 0.87, respectively. While the model for the resampled data shows overall improvement, it did not do better at predicting high-risk loans. A more effective model will be needed to predict high-risk loans with better precision, since an entity that lends money would want all the loans it approves to be healthy loans.  


<br>


### Usage
1. Ensure that you have all the necessary dependencies and files/scripts. 
2. Load the project files in an appropriate code editor such as Jupyter Notebook. 
3. Run the script in the Jupyter Notebook step by step
to execute the code and visualize the results appropriately.       

#### Contributions
Contributions to this project are highly encouraged! If you wish to contribute, please follow these guidelines:

- Fork the `credit-risk-classification` repository and clone it locally.
- Create a new branch for your feature or bug fix.
- Commit your changes with descriptive commit messages.
- Push your branch to your forked repository.
- Submit a pull request to the original repository.
- Please ensure that your code adheres to the project's coding style and conventions.


If you encounter any issues or have suggestions for improvements, please open an issue on the GitHub repository.

### License
These projects are licensed under the MIT License. Feel free to use, modify, and distribute the code as per the terms of the license. 


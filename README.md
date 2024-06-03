# Comparing-Classifiers-Bank-Marketing
In this practical application assignment, my goal is to compare the performance of the classifiers (k-nearest neighbors, logistic regression, decision trees, and support vector machines) on a dataset from ucimlrepo on Bank Marketing outcome. The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns.

# EDA of the data
After initial analyis check of data, following data ckena was done to ensure we can use the data for creating various models. Here's a brief data set with rows.

- age            45211
- job            44923
- marital        45211
- education      43354
- default        45211
- balance        45211
- housing        45211
- loan           45211
- contact        32191
- day_of_week    45211
- month          45211
- duration       45211
- campaign       45211
- pdays          45211
- previous       45211
- poutcome        8252

# Data Preparation
I trimmed rows for outliers based on pdays >400, Previous >25 and campign >30. I also replaced all 'Yes'/'No' in to 1 and 0 for columns_with_yes_no = ['default', 'housing', 'loan','y']
For all the columns_with_categories such as for ['job', 'marital', 'education', 'contact', 'month', 'poutcome'] used a label encoder
  
# Heatmap
After converting all featres in to numeric,below heat map shows initial corelation.
![image](https://github.com/NippaniP/Comparing-Classifiers-Bank-Marketing/assets/157237232/3507775e-a6f5-43f8-9951-228b7913b30e)

# KNN 
For the KNN model, I tried multiple n neighbours and using GridSearch CV, n_neighbours=95 was found to be the best model with following RoC curve Display along with Confusion matrix showing the accuracy score of 89.25% of the model.
![image](https://github.com/NippaniP/Comparing-Classifiers-Bank-Marketing/assets/157237232/d95d964b-cd86-4f40-ba18-82be80b4a3d0)

![image](https://github.com/NippaniP/Comparing-Classifiers-Bank-Marketing/assets/157237232/701e63ca-aee9-465f-b3b0-b503874c031d)

# Logistic Regression
For Logistic regression, I started with the default to accuracy score of 90%. Then various hyperparameters were tweaked as folows:

<U> Hyperparameters:</U>
1. #C (Inverse of Regularization Strength): Controls the trade-off between fitting the training data well and avoiding overfitting. Smaller values of C increase regularization, while larger values reduce it.
2. #Solver: The optimization algorithm used to find the best weights. Common choices include ‘lbfgs’, ‘newton-cg’, ‘sag’, and ‘liblinear’.
3. #Penalty: Determines the type of regularization (‘l1’ for L1 regularization, ‘l2’ for L2 regularization).

# Decision Tree based classification
For Decision Tree based model, following hyperparameters were used to get the best model.
<u>Hyperparameters:</u>
1. #max_depth: Maximum depth of the tree (controls overfitting).
2. #min_samples_split: Minimum number of samples required to split an internal node.
3. #min_samples_leaf: Minimum number of samples required in a leaf node

# SVC
For the last model using SVC, Following hyperparameters were used to get the best results. 
Hyperparameters:
1.#C (Regularization Parameter): Controls the trade-off between fitting the training data well and avoiding overfitting.
2. #kernel: Specifies the kernel function (‘linear’, ‘poly’, ‘rbf’, etc.).
3. #gamma: Kernel coefficient for ‘rbf’, ‘poly’, and ‘sigmoid’ kernels.

#Summary & Conclusion:
After running all the 4 models with hyperparameter tunning, following was the summary: Based on the results, the best model was #Decision Tree depth=10 and Entropy as criterion.
![image](https://github.com/NippaniP/Comparing-Classifiers-Bank-Marketing/assets/157237232/ee5d1d33-cacb-4f94-9a4a-02908079f68b)


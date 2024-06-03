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
For the KNN model, I tried multiple n neighbours and using GridSearch CV, n=95 was found to be the best model with following RoC curve Display
![image](https://github.com/NippaniP/Comparing-Classifiers-Bank-Marketing/assets/157237232/d95d964b-cd86-4f40-ba18-82be80b4a3d0)



# Neural Network Model Report

## Purpose of the Analysis
The purpose of this analysis is to evaluate the performance of a neural network model designed to select the applicants with the highest chances of success. This report will detail the methodology, results, and potential improvements for the model.

## Methodology
### Data Preparation
- The dataset used in this project includes these fields:
    - EIN - Identification column
    - NAME - Identification column
    - APPLICATION_TYPE - Alphabet Soup application type
    - AFFILIATION - Affiliated sector of industry
    - CLASSIFICATION - Government organization classification
    - USE_CASE - Use case for funding
    - ORGANIZATION - Organization type
    - STATUS - Active status
    - INCOME_AMT - Income classification
    - SPECIAL_CONSIDERATIONS - Special considerations for application
    - ASK_AMT - Funding amount requested
    - IS_SUCCESSFUL - Was the money used effectively
#### Preprocessing steps
1. The data was loaded into a Pandas DataFrame.
2. The ID columns were dropped.
3. Each `APPLICATION_TYPE` was then counted.
4. Each `CLASSIFICATION` was counted. Any values below 1 were dropped.
5. All categorical data in the dataset was then converted to numerical values uning `pd.get_dummies`.

### Model Architecture
- Layers
    - 1 input layer.
    - 2 hidden layers, the first with 80 nodes, the second with 30 (activation: "relu").
    - 1 output layer (activation: "sigmoid").
- Optimization algorithm

### Training Process
- The data was split for training and testing using the `train_test_split` method from sklearn.
- The Neural Network was trained using 100 Epochs.

## Results
### Data Preprocessing
#### What variable(s) are the target(s) for your model?
- The target for the model is the `IS_SUCCESSFUL` field in the data.
#### What variable(s) are the features for your model?
- Any features can be found in the list of fields above (ignore the identification fields, since those were dropped).
#### What variable(s) should be removed from the input data because they are neither targets nor features?
- The idendification fields were dropped because they had no bearing on determining whether or not the applicants would be successful or not.

### Compiling, Training, and Evaluating the Model
#### How many neurons, layers, and activation functions did you select for your neural network model?
- We had 4 layers total, 1 input layer, 2 hidden layers (the first hidden layer had 80 neurons, while the second had 30), and an output layer.
#### Were you able to achieve the target model performance?
- The model achieved an accuracy score of 72.51% with a loss of 55.61%.
#### What steps did you take in your attempts to increase model performance?
- To improve model performance, several steps were taken:
    - Adjusted the number of neurons in the hidden layers.
    - Increased the number of epochs for training.
    - Adjusted number of hidden layers for training.

## Summary of Results
### Summary of Results
The neural network model achieved an accuracy of 72.51% and a loss of 55.61%. While these results are somewhat good, other models I have used in the past have had a much better score.

## Alternative Model
### Model Selection
Logistic Regression

### Justification
- Logistic Regression is simple and interpretable.
- It performs well with binary classification tasks.
- It requires less computational power compared to neural networks.
- It is less prone to overfitting with fewer parameters to tune.
- It is also worth noting that, in a similar project (although all datasets are very unique), a logistic regression model was used and scored a 99% accuracy.

## Conclusion
The neural network model shows promising results but could benefit from further tuning and alternative approaches to enhance performance and efficiency.

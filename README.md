**Overview**
  This project aims to develop a binary classifier that can predict the likelihood of applicants achieving success if they receive funding from Alphabet Soup. The project will utilize the features present in the given dataset and employ diverse machine learning methods to train and assess the model's performance. The objective is to optimize the model in order to attain an accuracy score surpassing 75%.
  
 
**Result**
 **Data Preprocessing**
  
The model aims to predict the success of applicants if they receive funding. This shows by the IS_SUCCESSFUL column in the dataset which is the target variable of the model. The feature variables are every column other than the target variable and the non-relevant variables such as EIN and names which I will dropped. The features capture relevant information about the data and can be used in predicting the target variables. 

During preprocessing, I implemented binning/bucketing for rare occurrences in the APPLICATION_TYPE and CLASSIFICATION columns. Subsequently, I transformed categorical data into numeric data using the "one-hot" technique. I split the data into separate sets for features and targets, as well as for training and testing. Lastly, I scaled the data to ensure uniformity in the data distribution.


**Compiling, Training, and Evaluating the Model**

1: For my initial model, I decided to include 3 layers: an input layer with 80 neurons, a second layer with 30 neurons, and an output layer with 1 neuron. I made this choice to ensure that the total number of neurons in the model was between 2-3 times the number of input features. In this case, there were 43 input features remaining after removing 2 irrelevant ones. I selected the relu activation function for the first and second layers, and the sigmoid activation function for the output layer since the goal was binary classification. To start, I trained the model for 100 epochs and achieved an accuracy score of approximately 74% for the training data and 72.9% for the testing data. There was no apparent indication of overfitting or underfitting.

**Optimization 3 trials**

I attempted to optimize the model’s performance by first modified the architecture of the model by adding 2 dropout layers with a rate of 0.5 to enhance generalization and changed the activation function to tanh in the input and hidden layer. With that I got an accuracy score of 74.1% for my training set and 72.89% for my testing set.
For my second optimization attempt, I used hyperparameter tuning. During this process, Keras identified the optimal hyperparameters, which include using the tanh activation function, setting 41 neurons for the first layer, and assigning 13, 5, and 4 units for the subsequent layers. As a result, the model achieved an accuracy score of 73.21%.

In my final optimization attempt, I removed the STATUS column and applied binning to the ASK AMT column in the preprocessing phase. I created two bins: 1) mounts equal to $5,000 and 2) all other amounts in the ASK_AMT column because of the the imbalance in the dataset, which was identified through a histogram analysis. I kept the two dropout layers with a dropout rate of 0.5 and an activation function of tanh. To determine the optimal number of epochs, I utilized the early stopping function with a patience of 5, monitoring the val_accuracy metric. Through this approach, I found that training the model for 8 epochs yielded the best results. By implementing these adjustments, I achieved an accuracy score of approximately 73% with this final optimization attempt. After three attempts to optimize my model, I was able to achieve a goal of 79.46% accuracy score.


**Summary**
I was able to obtain the target accuracy above (75%), 79.46%, I suggest model 3 (optimozation 2). 

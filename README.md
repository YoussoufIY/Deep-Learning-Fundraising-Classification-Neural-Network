# deep-learning-challenge
## Overview

## Results

### Data Preprocessing

- The target variable for the model is the ''IS_SUCCESSFUL'' column. We are trying to determine whether or not
an organization will be successful in using the issued funds for their stated purpose. 

- The features for the model are all other columns except for the ''EIN'' and ''NAME'' columns. These are independent variables that will help make our prediction. 

- The ''EIN'' and ''NAME'' columns are removed from the input data because they are neither targets nor features that help to determine whether or not an organization will be successful in using the funds issued.


### Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
For the first model, I used:
 *80 neurons in the first hidden layer, about double the number of input features.
 *30 neurons in the second hidden layer, less than half the number of neurons in the first hidden layer in an 
    attempt to reduce overfitting by pruning the model.
 *1 neuron in the output layer as it is a classication problem. 
 *The relu activation function for the first two hidden layers and the sigmoid activation function for the output layer. 
 * 100 epochs for the model. 
 *The adam optimizer for the model. 
 *I used the binary_crossentropy loss function for the model. 
 *I used the accuracy metric for the model.
- I was unfortunately unable to achieve the target model performance of 75% accuracy. My best model had an accuracy of 73.6%.
- To increase the performance of the model, I started by measuring the p value of every feature by performing a chi-test on the training data. I then removed all features with a p value greater than 0.05. This improved the accuracy of the model slightly, from 72.94% to 73.56%. 
- I then tried to remove further features in the hopes of improving the accuracy of the model. This reduced the accuracy of the model to 73.41%. 
- Finally, I used Keras Tuner to try to find the best model. This resulted in a model with 2 hidden layers, 64 neurons in the first hidden layer, 32 neurons in the second hidden layer, and 1 neuron in the output layer. The model had an accuracy of 73.6%.


## Summary

The results of the model are far from optimal, but certainly better than random chance. The model could be improved by using more data, I believe there simply isn't enough data points to make an accurate prediction. However, this would be a good way to pre-approve organizations for funding. Whichever ones aren't approved could be given a second look by a human. This would save the foundation a lot of time and money.

# Neural Network Charity Analysis

## Overview

This project utilizes neural networks and deep learning to predict whether applicants for donations will be successful if they receive funding.

## Results

### Data Preprocessing

Two columns, EIN and NAME, were deleted from the original dataset as they will not impact the analysis.

Here are the remaining columns and the count of unique values in each:

![column_counts]()


There are two columns with non-numerical data that have more than 10 unique values: APPLICATION_TYPE and CLASSIFICATION.
Binning was performed on these columns before encoding them for analysis.

The target variable of our model was the IS_SUCCESSFUL column, because we are trying to determine whether applicants will be successful after
receiving funding.

The features of the model are all the other columns included in the above screenshot, excluding IS_SUCCESSFUL.

### Compiling, Training, and Evaluating

Originally, my model used 8 neurons in the first layer, and 5 neurons in the second layer. This was because, in other examples, using a large
amount of neurons does not make a model more efficient, and it can lead to overfitting.

I used the relu activation function.

For this model, the predictive accuracy was 72%:

![original_accuracy]()

This is pretty close to the target performance of 75%, but not quite there.

#### Optimization

I tried 4 separate things to improve the accuracy:

* First, I deleted the STATUS column to see if that would have any affect on the performance:

![delete_status](https://github.com/KW0114/Neural_Network_Charity_Analysis/blob/1c5c567f0b11c5707a074e58df01b5e716595d12/Resources/Screenshots/Delete_Status_Accuracy.png)

* Then, I added neurons to my two hidden layers:

![add_neurons](https://github.com/KW0114/Neural_Network_Charity_Analysis/blob/1c5c567f0b11c5707a074e58df01b5e716595d12/Resources/Screenshots/Add_Neurons_Accuracy.png)

* Then, I added another hidden layer:

![add_layer](https://github.com/KW0114/Neural_Network_Charity_Analysis/blob/1c5c567f0b11c5707a074e58df01b5e716595d12/Resources/Screenshots/Add_Layer_Accuracy.png)

* Finally, I changed the activation functions of my hidden layers to tanh:

![tanh](https://github.com/KW0114/Neural_Network_Charity_Analysis/blob/1c5c567f0b11c5707a074e58df01b5e716595d12/Resources/Screenshots/Tanh_Accuracy.png)

Overall, these really didn't do much to the performance of the model. 

## Summary

72% could be considered an acceptable accuracy in some cases, but when it comes to donating large amounts of money, I don't really think it is very good.
Perhaps using a random forest model could increase the accuracy. Even if it doesn't it would be much easier to interperet the results than using this
deep learning model.

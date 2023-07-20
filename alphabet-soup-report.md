# Alphabet Soup Neural Network Report

# Overview

For this project, I was provided with the data from a nonprofit foundation called Alphabet Soup, for which I built a neural network to determine whether its funding recipients were successful in their ventures.
This analysis will explain how I constructed this neural network, including the data preprocessing and the construction, training, and evaluation of the model. 
These sections will explain the features and targets of the neural network; which elements of the data were omitted; and the neural network model's performance.
Finally, I will explain how I attempted to optimize and improve the model.
At the end, I will offer my recommendations for which model should be used: my original neural network model or my optimized model.

# Results

    # Data Preprocessing
    
    1. The target, or y variable, of this data is the 'IS_SUCCESSFUL' column of the Alphabet Soup data.
    Because Alphabet Soup's central question was, whether their recipients' ventures were successful, I set the target value as the column that directly answers that question.
    As a result, I coded 'y = application_df_dummies['IS_SUCCESSFUL']'.
    2. The features, or X variable, of this data, are the following: 
    
        * Application status,
        * Ask amount,
        * Classification names that appear 1,500 times or more,
        * Application types that appear 500 times or more,
        * Income amount,
        * Special considerations,
        * Affiliations,
        * and use cases.
    
    After dropping the 'IS_SUCCESSFUL' column, these features would be used to train the model and determine whether the recipients' ventures were successful.
    
    3. The 'EIN' and 'Name' columns were dropped from the data, before it was fitted to the neural network model. 
    These columns were dropped because they are identifiers, rather than data about the type of venture, monetary status of the venture, or the outcomes of the venture. 
    Therefore, they had no predictive power, compared to the targets and features of the data.
    
    # Compile, Train, and Evaluate Model
    1. In total, my model has six layers -- three deep layers and three batch normalization layers. I chose three deep layers to account for the complexity of the data and batch normalization to speed up and stabilize training. 
    I added three dropout layers, as well, which shut off nodes at random to prevent overreliance on certain features. 
    Through trial and error, I decided on a conservative number of neurons in each deep layer. 
    The number of neurons in the first layer was based on the shape of the X_train variable, which were halved in the second layer, then halved again in the third.
    
    2. Unfortunately, I was unable to achieve target performance, with optimization leading to only meager improvements in accuracy. 
    I was able to improve the loss of the model, decreasing it by three percent.
    This means the model will be able to perform consistently on unseen data and be more stable.
    However, the model's accuracy only increased from 0.7248 to around 0.7296.
    
    3. Compared to the original model, I added (1) batch normalization and dropout laters, (2) added a third hidden layer, (3) increased the model to 500 epochs, and (4) decreased the number of neurons. 
    I attempted other optimizations, as well, including using other optimizers, altering the timing of the 'adam' optimizer, and dropping other layers in preprocessing. 
    However, none of these attempts improved the accuracy of the model. 
    The model's accuracy remained around 0.724 with other combinations of these alterations. 
    The four optimization techniques listed at the beginning of this subsection were the only ones that led to any improvement in the model's accuracy.
    
# Summary

Overall, my deep learning models were similar in performance and accuracy, when predicting the success of the ventures that received funding from Alphabet Soup. 
However, because of slight improvements to accuracy in my optimized model and significant improvements to its loss, I can recommend it over the model I was tasked to make in the starter code of this assignment.
I can recommend my optimized model as a more stable neural network, based on its loss, although its accuracy needs to be improved.

# Deep Learning Challenge

# Overview

For this project, I was asked to analyze data for a nonprofit organization called Alphabet Soup, which sought to determine which of its funding recipients were successful in their endeavors. To do this I produced two neural networks, one which followed the template included in the project and another which I attempted to optimize. Both models use the same preprocessing method, but their processes for compilation, training and evaluation differ. These differences will be listed in this file and more fully documented in the report that is also included in this repository.

# Instructions

Be sure that the following imports are available on your local machine or made at the top of your Jupyter Notebook:

  from sklearn.model_selection import train_test_split
  
  from sklearn.preprocessing import StandardScaler
  
  import pandas as pd
  
  import numpy as np
  
  import tensorflow as tf


Furthermore, ensure you are using a suitable tensorflow environment. 
If problems with tensorflow persist, upload the notebooks in the repository to Google Colab.

# Features

Both neural network models use the same preprocessing methods, uploading the .csv data file from a web address, dropping the identifier columns ("EIN", "NAME"), and selecting cutoff values for the "APPLICATION_TYPE" and "CLASSIFICATION" columns. Next, the data is made into dummies, split into features and targets, then scaled.
    
      # Basic Neural Network Model
      
          Following the template laid out by the assignment instructions, the first neural network model features two hidden layers. Its number of features corresponds to the [1] value of the shape of X_train. To find the number of neurons for this model, I experimented with more conservative numbers, but for this particular model, I determined that doubling the number of input features worked best for the first layer, then I set the second layer to the number of features found in X_train. Following the template I was provided, I used an "adam" optimizer and compiled the neural network to run 100 epochs. After running those epochs, the loss and accuracy data are printed and the model is saved as an HDF5 file.
    
      # Optimized Neural Network Model
      
        My optimized neural network added a third hidden layer, as well as a batch normalization and dropout layer for each hidden layer. After a lot of experimentation I rounded 79 -- the [1] value of the shape of X_train -- up to 80, then halved it to 40 for the next hidden layer, then to 20 for the third. Despite trying other optimizers and adjusting the "adam" training rate, I used the basic "adam" optimizer again and compiled the network to run 500 epochs. Again the loss and accuracy scores are reported at the end and the model is saved as an HDF5 file.

# Author

Daniel Adamson

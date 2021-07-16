# Neural Network Charity Analysis
<img src="https://github.com/tn64/Neural_Network_Charity_Analysis/blob/main/Resources/pexels-markus-spiske-1089438.png"></br>
<!-- Photo by Markus Spiske from Pexels -->
## Overview

In the scenario for this analysis, we are working with a foundation to analyze 
the impact of each donation and vet potential recipients to ensure the foundation's
money is being used effectively.

To accomplish this, we used a neural network using the Tensorflow machine learning
library for Python. The hope was that by using a neural network we could predict
the likelihood of success for potential projects

For this analysis, we first preprocessed the data, then compiled, trained, and 
evaluated the model. Finally, we optimized the model in three way to attampt to find
an optimization that would reach an accuracy of 75% or greater.

## Results

Results: Using bulleted lists and images to support your answers, address the 
following questions.

### Data Preprocessing
- Variables considered the target: IS_SUCCESSFUL
- Variables considered features: EIN, NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
- Variables that are neither targets nor features, and are removed from the input data: EIN, NAME (SPECIAL_CONSIDERATIONS was also removed during one of the optimization attampts)

### Compiling, Training, and Evaluating the Model
- Number of neurons, layers, and activation functions selected? 
The initial model includes a single input features & two hidden layers. The first hidden layer has 50 neurons, the second has 25. Additionally, each of the hidden layers employed the "relu" activation method, while the output layer employed the "sigmoid" activation.
- Were you able to achieve the target model performance? 
The 75% target was not reached. The first model only achieved a 71.5% accuracy rate.
<img src="https://github.com/tn64/Neural_Network_Charity_Analysis/blob/main/Resources/Opt0.png"></br>
- What steps did you take to try and increase model performance?
1. Optimization 1: Reduced the application_counts to less than 500 and the classification_counts to les than 800; increased neurons to 80 and 30 respectively.
<img src="https://github.com/tn64/Neural_Network_Charity_Analysis/blob/main/Resources/Opt1.png"></br>
2. Optimization 2: Dropped SPECIAL_CONSIDERATIONS feature because of prevalance of "N" for the value, returned application_counts to less than 700 and classification_counts to less than 1800; returned hidden layers to original values and added a third hidden layer with 25 neurons.
<img src="https://github.com/tn64/Neural_Network_Charity_Analysis/blob/main/Resources/Opt2.png"></br>
3. Optimization 3: Dropped the third hidden layer and changed the activation method for the output layer to "tanh"
<img src="https://github.com/tn64/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%203.png"></br>


## Summary
These attemmpts to finda a nueral network model for this dataset that achieved an accuracy 
rate of 75% or greater failed.

Since we are attempting a binary classification result for the dataset, better results might
be achieved using a supervised machine learning model such as "Random Forest Classifier" which 
works well when determining classification of data and reduces overfitting to improve accuracy.

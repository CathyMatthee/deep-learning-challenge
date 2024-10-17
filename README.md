# Credit Risk Analysis

## Overview of purpose of the analysis

The purpose of this analysis is to determine how effective the neural network is in predicting the success of receiving funding from AlphabetSoup based on the historical data and input features of past funding applications. In looking to improve the model's accuracy, pre-processing the data was identified as an opportunity to improve the model's predictive performance.

## Results

 - ###Data Pre-processing:
    - ####Variable target: "y" which is based on: the "IS_SUCCESSFUL" column in original df.
    - ####Variable features: "X" which is based on the following columns:
        APPLICATION_TYPE           12
        AFFILIATION                 6
        CLASSIFICATION             65
        USE_CASE                    5
        ORGANIZATION                4
        STATUS                      2
        INCOME_AMT                  4
        SPECIAL_CONSIDERATIONS      2
        ASK_AMT                   656

    - ####Variables to remove: non-beneficial columns of "EIN" and "NAME" were removed

 - ###Compiling, Training and Evaluating the Model:
    - ####Hyperparameters: - Used tanh activation function and 5 layers with the  following neurons:
        - layer 1: 36 neurons
        - layer 2: 66 neurons
        - layer 3: 56 neurons
        - layer 4: 11 neurons
        - layer 5: 41 neurons
        - output layer used a sigmoid function to return a binary classification
    
 - ####Did you achieve target model performance: 
        Yes, when running the Keras Tuner, the best model produced an accuracy of 0.7506

 - ####What steps did you take in your attempts to increase model performance: 
        After running a keras tuner of the best 3 models, the best model scored a 0.7506 accuracy. The model was retrained using the hyperparamaters of the best model best model from the Keras Tuner.
        - After retraining, it produced an accuracy of 0.7446 and a loss of 0.5524.
        - Analysed and removed outliers
        - Binned income amounts < 500 which are considered rare occurances
        - Changed activation function of layers to tanh

## Summary of results
The model returned a strong performance by successfully predicting outcomes based on the input features. A Random Forest Classifier is recommended as an alternative to improve classification accuracy because it is robust in handling overfitting, good at interpretability using the feature importance scores and can handle non-linear relationships well.

Sources:
Used chat gpt to help with removing outlier code and also with writing to a .h5 file.
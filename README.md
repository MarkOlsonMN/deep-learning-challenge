# README - deep-learning-challenge  
  
## Module 21 Challenge  
Class:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;U of M Data Analytics and Visualization Boot Camp , Summer 2024  
Student:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Mark Olson  
Professor:&nbsp;&nbsp;&nbsp;&nbsp;Thomas Bogue  ,  Assisted by Jordan Tompkins  
Date:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;08/26/2024  
  
## Location of this Repro (Public)  
URL:&nbsp;&nbsp;&nbsp;&nbsp;https://github.com/MarkOlsonMN/deep-learning-challenge  
  
## Code Source/Location within this Repo  
ReadMe:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;deep-learning-challenge/README.md  
(base) Jupyter Notebook (code):&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;deep-learning-challenge/AlphabetSoupCharity.ipynb  
(base) ML Model HDF5 (model export):&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;deep-learning-challenge/AlphabetSoupCharity.h5  
(optimize) Jupyter Notebook (code):&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;deep-learning-challenge/AlphabetSoupCharity_Optimaization.ipynb  
(optimize) ML Model HDF5 (model export):&nbsp;&nbsp;&nbsp;&nbsp;deep-learning-challenge/AlphabetSoupCharity_Optimaization_1.h5  
(optimize) ML Model HDF5 (model export):&nbsp;&nbsp;&nbsp;&nbsp;deep-learning-challenge/AlphabetSoupCharity_Optimaization_2.h5  
(optimize) ML Model HDF5 (model export):&nbsp;&nbsp;&nbsp;&nbsp;deep-learning-challenge/AlphabetSoupCharity_Optimaization_3.h5  

# ANALYSIS REPORT  

Title:  
Alphabet Soup Charity - Determining Highly Successful Funding Applicants - via a Deep Learning (DL) Model  

Section 1 - Purpose:  
We are researching Deep Learning techniques, in order to create a Machine Learning model, that will be able to successfully predict whether an applicant is most likely to be successful if they receive funding from the Alphabet Soup nonprofit foundation.  Our target predictive accuracy is to be greater than 75%.  
  
Section 2 - Results:  
 - Data Preprocessing
    - Target variable
       - 'IS_SUCCESSFUL' column
    - Feature variables
       - 'APPLICATION_TYPE, 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', 'ASK_AMT' columns
    - Removed variables
       - 'EIN', 'NAME' columns
 
 - Compiling , Training, and Evaluating the Model
    - Neural network model
      This model is structured for a binary classification task, with the sigmoid function providing a probability output between 0 and 1
        - Neurons
          Neurons: 111 total (80 in the first layer, 30 in the second, 1 in the output layer).
            - Input Layer: The input layer does not have neurons in the typical sense; it just specifies the shape of the input data, which has columns_in_training_data (i.e. 43) features.
            - First Dense Layer: 80 neurons
            - Second Dense Layer: 30 neurons
            - Output Layer: 1 neuron
            - Total Neurons: ( 80 + 30 + 1 ) = 111 neurons
        - Layers
          3 Dense layers (i.e. excluding the Input Layer)
            - Input Layer
            - First Dense Layer
            - Second Dense Layer
            - Output Layer
        - Activation Functions
          2 layers use relu, and 1 layer (the output) uses sigmoid.
            - First Dense Layer:  relu       (Rectified Linear Unit)
            - Second Dense Layer: relu
            - Output Layer:       sigmoid    (commonly used for binary classification)

    - Model Performance 
       - target   = >75%
       - obtained =  72%
       - we did NOT achieve the target model performance !
         
    - Steps taken to increase performance
       - OPTIMIZATION 1 = Add More Neurons to a Hidden Layer
          - increased the number of neurons being used by the First and Second Dense Layers
       - OPTIMIZATION 2 = Add More Hidden Layers
          - added both a Third and a Fourth Dense Layer
       - OPTIMIZATION 3 = Increase the Number of Epochs
          - increased the number of Epochs used to train the model

Section 3 - Summary:  
The required predictive accuracy , which was greater than 75.00 % , was not obtained.  
The best model accuracy obtained was 72.93 % , after several optimizations.  
We must consider ways to increase predictive accuracy , including choosing a different model.

Section 4 - Choosing A Different Model:  
To enhance this Machine Learning model , to gain predictive accuracy , a recommended course of action would be to first start with Tree-Based Models (ex. Random Forest, XGBoost) - These models usually provide a strong performance boost on tabular data and can handle feature interactions automatically.  

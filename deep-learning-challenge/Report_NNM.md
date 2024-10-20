###### Michael Sanchez
###### October 2024
###### Challenge 21
# Report on Neural Network Models

## Overview
This purpose of the project is to use data from a non-profit organization Alphabet Soup to develop a model that can be used to help predict whether applicants will be successful in funding the company.  The dataset itself includes information from these companies including and not limited to their name, type of application, classifications of government organization and income, the amount they ask, status, and special considerations.  
## Results
### Data Processing
- Target Variable: IS_SUCCESSFUL
- Features: Application_Type, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION type, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT.
- Variable Removed: STATUS, for the purpose of balance and the fact that a non-active organization would not contribute to the overall funding initiative of the organization.  Note, this variable was removed after the first run of the model.
### Compling, Training, and Evaluating the Model
Prior to creating the model the data was modified in the following ways:
- The Variable APPLICATION_TYPE re-named types that had less than 156 companies to other to reduce the number of types.
- The Variable CLASSIFICATION had similarly renamed classifications that had less than 1883 companies attached to other.
The purpose of changing these variables is to reduce the number of columns created when the data is transfomred using the get_dummies function which creates a numerical/boolean value necessary to run the prediction model.
#### Attempt 1
After the data had been cleaned and transformed the first attempt at the model had the following characteristics:
- First Layer: Activiation function "Relu" since all values are non-negative and utilizing values from 0 to 1 used by the features of the data.  80 neurons are used with input_dimensions is 43 to represent the 43 features.
- Second Layer: 30 Neurons with the "Relu" activiation model.
- Output Layer: "Sigmoid" to accommodate the binary structure of the model.
- Model Fit: 100 epochs were used.
- Results: Loss at 0.5615 and 0.7265
#### Attempt 2
The initial function was used as a baseline to determine the changes that could be made to optimize the model.  After some observation, the removal of the "STATUS" feature was removed.  The new characteristics of the second model include:
- First Layer: The "Relu" activation model was not changed and the number of neurons were increased from 80 to 90.  The input dimenions were changed to 42 to accomodate the removal of "STATUS".
- Sceond Layer: "Relu" with an increase of neurons from 30 to 40.
- Output Layer: Same as model 1
- Model Fit: 60 epochs after observing little change in accuracy after 50 in the first model.
- Results: Loss 0.5556 Accuracy 0.7249
The results of this model had an accuracy that was reduced slightly.
#### Attempt 3
In attempt to increase accuracy, the following characteristics were used:
- First Layer: Remained the same from model 2.
- Second Layer: Remained the same from model 2.
- Third Layer: A third layer was added with the same activation function "Relu" with 10 neurons.
- Output Layer: Remained the same from model 1 and 2
- Model Fit: 70 epochs were used instead of 60.
- Results: Loss at 0.5609 and Accuracy at 0.7247
Results were not much different from model 2.
#### Attempt 4
One more attempt was made with the idea that increasing the neurons would improve accuracy after the addition of the third layer.
- First Layer: Neurons were increased to 100
- Second Layer: Neurons were increased to 50
- Third Layer: Neurons were increased to 20
- Output Layer: Remained the same from previous models.
- Model Fit: 80 epochs were used.
- Results: Loss at 0.5700 and Accuracy at 0.7250
Results had an accuracy slightly higher but may not be that significant.
## Summary
After these attempts I have not reached the 75% goal, but I feel there is potential due to the accuracy falling short by about 2.5% on average.  Another look at the features can probably improve the results if they are decided that they have no bearing on the success of the company.  Since most of the values are categorical, it may be useful to have more quantitative metrics to ensure the success of the companies.
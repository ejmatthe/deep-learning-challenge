# deep-learning-challenge
## Overview
For this project, the goal was to take a dataset of projects funded by the client (Alphabet Soup), and create a neural network model to predict if applicants will be successful. The dataset contained historical project information for evaluation and then training of the model. The ability to successfully predict a project's success or not would translate to better use of funds and less waste.
## Results
There are three main pieces to talk about - the data and its preparation, the model itself and attempts to optimize and improve the model.
#### The Data
For starters, the provided dataset included two columns that were unnecessary - EIN and the organization name. As the goal is to evaluate the projects independently, it is less important to know the individual organization (by name) compared to the categories and features of it. 

The variable used as the target is the project success column (titled in the dataset as "IS_SUCCESSFUL." It was already set as a numerical binary, which required no change. It is also the goal of the project to successfully predict its value.

The variables used as features are the remaining columns not yet discussed. They are:
  * Application type (which was reduced from 17 unique entries to the 8 most common, and 1 bucket for the remaining values)
  * Industry affiliation
  * Government organization classification (which was reduced from 71 unique entries to the 5 most common, and 1 bucket for the remaining values)
  * Use case
  * Organization type
  * Active Status
  * Income amount classification
  * Whether or not there were special considerations
  * Funding requested
#### The Model
The initial model was close to target performance, providing 72.76% accuracy. I started off with 2 hidden layers (with 80 neurons in the first one and 30 neurons in the second one, using the "relu" activation), plus an output layer with 1 neuron and the "sigmoid" activation. A loss of  0.5586, however, was less than desirable.
#### Model Optimization
In order to attempt to optimize the model, I started off by changing the variables used as features. I dropped the "funding request" variable due to the sheer volume of unique values (8,747 compared to the 2nd highest being 71 and then 17, which were "Application Type" and "Classification" as discussed above). The first attempt to opimize the model otherwise mirrored the initial model, as far as neurons, layers and functions/activations are concerned. This performed a little better with an accuracy of 72.84% and loss of 0.5575, but still did not meet target performance.

The second attempt used the same layer and activation/function structure as the previous models, but used 80 neurons each in both hidden layers. This was largely a step backwards, though, as accuracy fell to 72.77% and loss increased to 0.5616.

The third attempted optimization provided the biggest change, by adding an additional hidden layer. The first hidden layer consisted of 80 neurons using the "relu" activation, the second hidden layer consisted of 50 neurons using the "tanh" activation, the third hidden layer consisted of 30 neurons using the "tanh" activation with a final layer consisted of 1 neuron with the "sigmoid" activation. This provided the best results of any of the models, but still failed to meet target performance with only 72.86% accuracy and a loss of 0.555.
## Summary
Unfortunately, overall, my approach did not meet the target performance, nor did the approach to optimization result in significant change in performance. If I were to continue trying to find a better model to work for this issue, there are two different approaches I would take. The first is to see if the current model could be iterated on further by, in this case, changing the input variables again. As eliminating the funding request did not make much of an improvement, I would suggest including it, but providing "bins" for different funding ranges to reduce the number of unique values from the 8,747 originally present to something more manageable like 10 or fewer.

The other approach I would recommend attempting is to see if a supervised learning model could provide better predictions. As we are reviewing historical data, we know what the outcome is, and use that as a basis for the model. This has the added benefit of providing a "simpler" (or at least, less resource intensive) model to use, if it proves to be feasible.

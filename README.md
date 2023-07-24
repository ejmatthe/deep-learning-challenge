# deep-learning-challenge
## Overview
For this project, the goal was to take a dataset of projects funded by the client (Alphabet Soup), and create a neural network model to predict if applicants will be successful. The dataset contained historical project information for evaluation and then training of the model. The ability to successfully predict a project's success or not would translate to better use of funds and less waste.
## Results
There are three main pieces to talk about - the data and its preparation, the model itself and attempts to optimize and improve the model.
#### The Data
For starters, the provided dataset included two columns that were unnecessary - EIN and the organization name. As the goal is to evaluate the projects independently, it is less important to know the individual organization (by name) compared to the categories and features of it. 

The variable used as the target is the project success column (titled in the dataset as "IS_SUCCESSFUL." It was already set as a numerical binary, which required no change. It is also the goal of the project to successfully predict its value.

The variables used as features are the remaining columns not yet discussed. They are:
  * Application type
  * Industry affiliation
  * Government organization classification
  * Use case
  * Organization type
  * Active Status
  * Income classification
  * Whether or not there were special considerations
  * Funding requested
#### The Model
The initial model was close to target performance, providing 72.76% accuracy. 
#### Model Optimization
## Summary

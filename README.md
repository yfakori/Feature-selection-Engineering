# Feature-selection-Engineering

## Problem statemen

This dataset is composed of a range of biomedical voice measurements from 31 people, 23 with Parkinson's disease (PD). Each column in the table is a particular voice measure, and each row corresponds to one of 195 voice recordings from these individuals ("name" column). The main aim of the data is to discriminate healthy people from those with PD, according to the "status" column which is set to 0 for healthy and 1 for PD

I used this dataset to experiment with feature selection techniques, specifically filter methods. Consequently, I skipped data cleaning and exploratory data analysis. My objective is to assess whether feature selection can improve model performance.

The goal is to create a machine learning model that can predict whether a patient is likely to have Parkinson's disease based on biomedical voice measurements.

Data source: https://www.kaggle.com/datasets/vikasukani/parkinsons-disease-data-set/data


List of features:

name - ASCII subject name and recording number
MDVP:Fo(Hz) - Average vocal fundamental frequency
MDVP:Fhi(Hz) - Maximum vocal fundamental frequency
MDVP:Flo(Hz) - Minimum vocal fundamental frequency
MDVP:Jitter(%), MDVP:Jitter(Abs), MDVP:RAP, MDVP:PPQ, Jitter:DDP - Several measures of variation in fundamental frequency
MDVP:Shimmer,MDVP:Shimmer(dB),Shimmer:APQ3,Shimmer:APQ5,MDVP:APQ,Shimmer:DDA - Several measures of variation in amplitude
NHR, HNR - Two measures of the ratio of noise to tonal components in the voice
status - The health status of the subject (one) - Parkinson's, (zero) - healthy
RPDE, D2 - Two nonlinear dynamical complexity measures
DFA - Signal fractal scaling exponent
spread1,spread2,PPE - Three nonlinear measures of fundamental frequency variation

## Workflow

1. Train the model using all the features (22). I used logistic regression to train the model. 
2. Evaluate the model performance . The evaluation scores are called baseline evaluation
3. Feature selection
4. Train a second model called final model using all the selected features using the same data split (random state)
5. Evaluate the model performance . The evaluation scores are called final evaluation
6. Compare the perdormance of two models

## Feature selectio using filter methods: They are focus on intrinsic properties of features
•	Correlation with target
•	Pairwise correlation
•	Variance threshold

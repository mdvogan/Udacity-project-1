# Udacity-project-1
Udacity DS project 1

This repository is for the first project of the Udacity Data Science nanodegree.
The goal of the project was to use estimate a model to determine
the main variables that influence Airbnb listing ratings and write a
blog post summarizing the results.

## Questions of interest
1) What actions can a host take to get a high rating?

2) Are specific property attributes correlated with high ratings?

3) Do customers prefer Airbnb rentals in certain parts of Seattle?

##Libraries used
* numpy
* pandas
* seaborn
* matplotlib

##Datasets used
Data available at https://www.kaggle.com/datasets/airbnb/seattle?resource=download&select=listings.csv
* listings.csv

The Jupyter notebook is divided into three sections:

## Part 1 - Data Preprocessing
The code in this section loads the data, and reduces the features down to
only those that are relevant to this project. Note that I excluded all features
that are directly related to rating such as superhost and sub-ratings
since they would tautologically have a very strong correlation.

This section is also where I created new features and cleaned the numeric variables.
I dropped all observations with missing rating since that is the
target variable and imputation could affect the model. However, I imputed
all other missing numeric features with mean values.

## Part 2 - Descriptive Analysis
The code in this section performs simple descriptive analysis to answer
the questions of interest. Routine summary statistics, distributional
analysis, and correlation plots.

## Part 3 - Build and Test model
The code in this section creates dummy variables for the categorical variables
and estimates a ridge regression to measure which features have the highest
correlation to listing rating. All features were normalized by standard scaling
to make the coefficient magnitudes comparable. Prior to estimation I split the
data into 67-33 training test sets to validate results. For the ridge regression, I
used cross validation to pick the best regularization alpha, and then ranked the
coefficients by order of magnitude. Training MAE was 4.05 and testing MAE
was 4.20.

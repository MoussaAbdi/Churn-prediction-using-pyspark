# Churn Prediction with PySpark

## Description
In this project, we study the data of a music streaming application in order to identify the users that are
likely to churn. Multiple users interact in parallel with the application, and for each action an event is created (like e.g.
playing a new song or listening to an ad) and added to a database with the corresponding caracteristics (time stamp, type of event, etc...).
The goal of the project is to use the generated data in order to perform churn prediction. The dataframe
is analyzed using PySpark. The dataset is provided by Udacity in the context of the capstone project of the Data Scientist Nanodegree
program.


This project is decomposed into three different parts:  
* The first step of the project consists in exploratory data analysis. First, we  do some analysis on the initial dataframe to have a first insight into the data. Then, we explain why this is more useful to construct a new user-indexed dataframe, and we perform a deeper understanding of the data using this new dataframe.
* After exploratory data analysis, we build some features and inject them in a model that will be ran using PySpark. In terms of modeling, we also perform hyper-parameter tuning and the final performance of the best model will be given. Some results analysis will be done, and some corrective actions to reduce the number of churners will be
suggested.
* In the final part of the project, we analyze the results and provide some ideas to improve the model performance.


## Dependencies

For smooth running of the code, please install the following packages: 
* PySpark version 2.4.3 (mainly pyspark.sql module and pyspark.ml)
* pandas >= 0.23.4  
* numpy >=  1.15.4  
* matplotlib >= 2.1.0
* seaborn >= 0.8.1

## Files Descriptions

The different directories are the following:
* The Sparkify.ipynb file is the notebook used to analyze the data and produce the results. We also provide the html version. 
* We also provide the dataset as the mini_sparkify_event_data.json file for results reproductibility
* The WriteUp_Sparkify.pdf file describes in details the different steps of the analysis and the main conclusion and possible improvements. 

## Summary of the obtained results 

Here are the main outcome of the study:
* The features are build using quantities per unit of time or per visit
* To be able to build such features, we first built per-user observation windows using registration days and churn timestamps
* The feature matrix is indexed by users, and each column is a feature describing the way the users interact with the application. 
Features such as the number of songs per hour or the number of roll-advert per hour are considered
* We compared three models that were tuned using grid-search with the F1-score metric to optimize. The best model was found 
to be the Gradient-Boosted tree with a final score of 0.64
* The analysis of the feature importance permitted to suggest several triggers to reduce the number of churners through preventive actions. 
* Several ideas to improve the model are also given. 


## Acknowledgements
I would like to thank Udacity for the project and for providing the data. 

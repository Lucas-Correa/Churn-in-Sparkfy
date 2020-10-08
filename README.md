# Churn-in-Sparkfy

## 1. About
This project uses spark to create a machine learning algorithm that predict the churn of users in a digital music stream company called Sparkfy. 

In sparkfy there are paid level users (premium account) and free tier level users. In the paid level, a user can stream music without advertisements between songs. The main goal here is to predict the premium accounts more likely to cancelled it's subscription.

The available data base is composed by the user log action whitin the stream plataform. Actions like play next song, like or deslike a song, add friends are organized among sessions Id's in sequencia timestamps. 

The full dataset size is 12GB which require the use of big data frames in a cloud computing service like pyspark and Amazon Web Service, which were the ones used.

## 2. How to Start 
This Git has a jupyter noteook containing:
  
  1. The pre-processing steps to load and clean the dataset;
  2. The Exploratory Data Analysis;
  3. The model build and training;
  4. Metrics for validate the model.
  
 The notebook already consider the dataset web path of the full 12gb, so I recommend that you run it in distribuited system of computers. 

## 3. Regarding the Data

## 4. Regarding the Model

## 5. Results and evaluation metrics

## 6. License

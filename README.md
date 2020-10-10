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

Each user log row is compused by:
- artist: artist name
- auth: 
- firstName: first name of the user
- gender: user gender
- itemInSession: the sequencial number of that item in the session
- lastName: user last name
- length: music duration 
- level: the account level, free or paid
- location: location where the session is been stremed
- method: the action in that user log register (put or get) 
- page: page of the log
- registration: number of user registration 
- sessionId: session unique key
- song: name of the song
- status: code for the sataus of the page
- ts: timestamp of the log 
- userAgent: browser used by the user to acess that session 
- userId: user unique key

## 4. Regarding the Model

The model was built to classify each user in two possible categories, one for users who are likely to churn and the users more likely to stay in the sparkfy plataform. The idea of the model is to learn from the features of already cancelled users so it can tag users that are with similar characteristics but still remains in the plataform. This assumes users take the same steps before cancelle their account.

The final model considered 6 features: 

- AvgSongsPlayes: Avarage songs played by each user. It is expected that users who canceled their account have less engagement in the plataform, therefore less 
                  played songs
                  
- SongVariety: Different songs listend by the user. Users that explore different songs tend to have a better utilization of the plataform, therefore tend to keep                it

- LikedSongsProportion: The ratio of desliked songs for liked songs by each user id. If the user deslike the songs of the plataform, it is expected him to leave

- FriedsAdded: How many times a user pressed the Add Friend Button. Users that engage more with others tend to stay longer in the plataform

- DaysInPremium: How many days a user is with the premium account. This features was created to control landmarks in users account life. Probably users behave in                  differente manners according to how much time they are in the premium account.

- SessionsLast30days: How many sessions a user had in the last 30 days. It is expected that users reduce the number of sessions before they cancelled.

The initial classifer used was Logistic Regression, but, because the data was imbalanced for the number of cancelled and active users, the classifer was tagging all the users as active users and still getting a good accuracy score. To surpass this problem, I have changed the classifer to a Gradient-Boosted Tree so the model starts to be penalize for incorrect labels on every interaction. 

## 5. Results and evaluation metrics

The Metrics choosed to evaluate the model where the accuracy, recall, precision and f1-score.

## 6. License


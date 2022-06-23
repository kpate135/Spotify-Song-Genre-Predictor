# Spotify-Song-Genre-Predictor
A machine learning project leveraging pandas, NumPy, and sklearn to create a model in order to predict the genres of over 18,000 songs using Spotify metadata and a K-Nearest Neighbors training method.

[The DataSet Used in this Project](https://www.kaggle.com/datasets/imuhammad/audio-features-and-lyrics-of-spotify-songs?resource=download) <br>
- referred to as "spotify_songs.csv" in the source code.

# What is the DataSet? <br>
The dataset we have is a Spotify dataset that includes over 18,000 songs. The dataset includes the
song’s name, artist, lyrics, genre, and various audio features. With this dataset we wanted to be able
to predict the genre of a specific song using a predictive model. To do this we focused on using the
different audio features of the songs, such as danceability, energy, and loudness. These features are
measured on a scale quantitatively by Spotify’s own process. The predictive model we decided to
use to incorporate these different features was a KNN Classifier model.

# Cleaning Up the DataSet <br>
We first remove all unnecessary features from the dataset, because we only wish to observe
quantitative song attributes.
Initially all genres were included, but after analyzing our dataset we found dropping certain genres
would improve our accuracy.
The final combination of genres we used were EDM, Rap, and Rock as shown below.
We assign numeric values to each categorical genre to be later used for our knn model.

# Exploratory Data Anlaysis
- Histogram Visualizations for the Normalized Ratings of Each Feature
- Bar Graph Visualizations for the Mean Normalized Ratings of Each Feature Between Different Genres

# Determining features for the K-Nearest Neighbors model
First, we tried running a KNN model including every genre and every quantiative feature.
To be able to create a KNN model, we imported a KNN classifier from the sklearn library.
In order to intialize the model, we split the data into training and testing.
From there, we fit the model with the training data.
Finally, we predicted the genres based on the features in the testing data.
<br>
<br>
This resulted in importing the sklearn metrics to observe the accuracy of our model which was about .47
In order to try improving this low accuracy of our model, we decided to try removing latin and r&b
due to the similarities in the mean ratings of their features based on the bar graphs above.
With the new model, predicting only edm, pop, rap, and rock, we were able to produce an accuracy
of .63
<br>
<br>
Next, we tried looping through every combination with at least 5 features and 3 genres to try
finding the best accuracy.
<br>
# Final Accuracy
We have found the highest accuracy of .8175
It predicts the genres of edm, rap, and rock.
The features the KNN model is based on are 'danceability', 'energy', 'loudness', 'mode',
'speechiness', 'valence', 'tempo', and 'duration_ms'. 


# Video Game Console Recommendation

## Overview

"A video game is an electronic game that involves interaction with a user interface to generate visual feedback on a two- or three-dimensional video display device such as a touchscreen, virtual reality headset or monitor/TV set. Since the 1980s, video games have become an increasingly important part of the entertainment industry, and whether they are also a form of art is a matter of dispute.

The electronic systems used to play video games are called platforms. Video games are developed and released for one or several platforms and may not be available on others. Specialized platforms such as arcade games, which present the game in a large, typically coin-operated chassis, were common in the 1980s in video arcades, but declined in popularity as other, more affordable platforms became available.

These include dedicated devices such as video game consoles, as well as general-purpose computers like a laptop, desktop or handheld computing devices." (Wikipedia)

Video games have been a big part of my life in good and bad times. I enjoy the various genres and stories across games that kept me playing for hours or even days and weeks. In order to play though, I would need to buy a certain game console or platform and there are certain games I enjoy that are exclusive to a platform.

I want to find a way to analyze the current generation platforms Playstation 4, Xbox One, and Nintendo Switch games library and find a way to recommend a platform based on popularity and total ratings (critics and user ratings) along with possibly the genres, game engines, and game modes.

![](/images/Genres.png)

## Executive Summary

The goal is to increase interest and sales in video games by recommending video game consoles. The data was obtained from the Internet Game Database (IGDB) through its Application Programming Interface (API).

k-Means Clustering is the main algorithm mainly because of its ease of use and being unsupervised since there is no true target or correct answer using inertia and silhouette score as the metrics.

Since k-Means Clustering works best with continuous values (ex. 1, 2.5, 3.14), a majority of the columns used in the data frame are categorical data (labels, names) that were transformed into binary numbers (0,1) to fit the model.

## Statistical Summary

The unsupervised (no target variable) learning algorithm k-Means clustering was implemented. PCA Analysis was used to reduce shear large number of columns into smaller and manageable shape. The PCA transformed dataframe is then clustered with k-Means Clustering.

The metric silhouette score evaluated that 0.15 meaning the model is going in the right direction but needs more work. A silhouette score is ranged from -1 to 1 and a score closer to 1 is ideal.

Based on the visuals and scores, there should be more game attributes such as time played and platforms included to better group data points.

With the above data, it's possible to group the data sets as platforms and that way, a recommender system may be possible.

![](/images/PCA_k_cluster_final.png)

![](/images/inertia_silhouette_score.png)

## Data Gathering & Wrangling

![](/images/sample_igdb_api.png)


The data was obtained from the Internet Game Database through its API with the help of Insomnia, a REST client application that simplifies the data scraping process. The data is then saved as a csv file (text file similar excel) in the Python notebook then certain columns were removed and modified to match certain data types such as strings and arrays to be modeled.

k-Means Clustering finds similarities among the numerical data and groups them displaying as clusters. Sometimes, the data sets may contain an unthinkable number of columns. The game dataset contains 62 columns so the Principles Component Analysis (PCA) model is used to reduce the shape and size extracting the most important info then fitted into the k-Means Clustering model.

After fitting the data set to a PCA model and visualizing the results, the number of clusters is set to 4 since the change in value of inertia is no longer significant and most likely the variance as well after 4 clusters according to the PCA transformed clusters. The random state is set to 42 to keep consistency throughout the modeling process.

## Notebooks

- 01_IGDB_API.ipynb
- 02_EDA.ipynb
- 03_Modeling.ipynb


## Resources

  - [IGDB](https://www.igdb.com/discover)
  - [Insomnia](https://insomnia.rest/)
  - [medium](https://medium.com/) blog posts on k-Means clustering and PCA
  - [Stack Overflow](https://stackoverflow.com/)
  - [Python for Data Science & Machine Learning](https://www.udemy.com/course/python-for-data-science-and-machine-learning-bootcamp/)
  - General Assembly (GA) Lecture Notes on Unsupervised Learning
  - GA Global Instructors
  - GA Boston Data Science Immersive (DSI) local instructors
  - [Dataset]('/datasets/clean/games_clean_with_ori.csv') used for the model development can be found in the clean folder under datasets in this repository
  - Tableau Public

## Next Steps
 - Rework dataset and modeling
 - Create Recommender System
 - Host as a web app using Flask

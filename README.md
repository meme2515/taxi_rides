# 🚕 Taxi Ride Duration Prediction

`taxi_ride.ipynb` contains code used to predict the duration of taxi rides in Manhattan island using data published by [NYC Taxi and Limousine Commission](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page). I have mainly used the Python [pandas](https://pandas.pydata.org/) and [sklearn](https://scikit-learn.org/stable/) libraries, where the best outcome was achieved with tree regression. The learning takes place in four distinct parts.

## 1. Data Selection and Cleaning

After collecting a random sample of the original taxi rides data into a [SQLite](https://www.sqlite.org/index.html) database, I have queried only the rides that occurred within the boundaries of New York City. I have then proceeded to filter the data to exclude abnormal rides and keep only rides that happened on Manhattan island using the [point-in-polygon algorithm](https://en.wikipedia.org/wiki/Point_in_polygon).

## 2. Exploratory Data Analysis

I analyzed fluctuations in taxi users to exclude abnormal dates from the training data. Because the data is limited to the month of January, I have found that new year's day, MLK day, and a blizzard in 2016 significantly affected the number of taxi users.

## 3. Feature Engineering



## 4. Model Selection

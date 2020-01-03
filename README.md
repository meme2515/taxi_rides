# 🚕 Taxi Ride Duration Prediction

`taxi_ride.ipynb` contains code used to predict the duration of taxi rides in Manhattan island using data published by [NYC Taxi and Limousine Commission](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page). I have mainly used the Python [pandas](https://pandas.pydata.org/) and [sklearn](https://scikit-learn.org/stable/) libraries, where the best outcome was achieved with tree regression. The learning takes place in four distinct parts.

## 1. Data Selection and Cleaning

After collecting a random sample of the original taxi rides data into a [SQLite](https://www.sqlite.org/index.html) database (placed inside the `data` folder), I have queried only the rides that occurred within the boundaries of New York City. I have then proceeded to filter the data to exclude abnormal rides (rides with negative number of passengers, duration longer than one hour, etc.) and keep only rides that happened on Manhattan island using the [point-in-polygon algorithm](https://en.wikipedia.org/wiki/Point_in_polygon).

## 2. Exploratory Data Analysis 📈

Because the data is limited to the month of January, I have found that new year's day, MLK day, and a blizzard in 2016 significantly affected the number of taxi users. I analyzed fluctuations in taxi users accordingly to exclude abnormal dates from the training data. 

## 3. Feature Engineering

I have selected start location, end location, trip distance, time of day, and day of the week from the original data as features for prediction, and created a feature matrix using the sklearn package. Because it was difficult to directly use lat-lon location as a feature, I have used the PCA algorithm to divide the rides into three groups: Lower, Midtown, and Upper Manhattan. The resulting features also indicate the speed of the ride and whether or not the ride happened in the weekend.

## 4. Model Selection 🌲

In this part I have run various models such as constant prediction, linear regression, and tree regression and compared the root mean squared error of each model's prediction. As a result, I have found that tree regression outperforms all of the other models. It was also true that predicting speed directly resulted in lower rmse. This was useful because I could derive the ride duration by combining speed and distance (which was already provided as a feature).

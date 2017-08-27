# Case Study - Churn Prediction


## Executive Summary


## Table of Contents
1. [Motivation](#motivation)
2. [Analysis](#analysis)
3. [Results](#results)
4. [Conclusions](#conclusions)


### Motivation <a name="motivation"></a>

A ride-sharing company (Company X) is interested in predicting rider retention.
To help explore this question, I examined a sample dataset of a cohort of 
users who signed up for an account in January 2014. The data was pulled on July 1, 2014; 
we consider a user retained if they were “active” (i.e. took a trip) in 
the preceding 30 days (from the day the data was pulled). In other words, a user is "active"
if they have taken a trip since June 1, 2014.

I was interesed in understanding what factors are the best predictors for retention, and 
operationalizing those insights to help Company X.

Here is a detailed description of the data:

```
city: city this user signed up in
phone: primary device for this user
signup_date: date of account registration; in the form `YYYYMMDD`
last_trip_date: the last time this user completed a trip; in the form `YYYYMMDD`
avg_dist: the average distance (in miles) per trip taken in the first 30 days after signup
avg_rating_by_driver: the rider’s average rating over all of their trips
avg_rating_of_driver: the rider’s average rating of their drivers over all of their trips 
surge_pct: the percent of trips taken with surge multiplier > 1
avg_surge: The average surge multiplier over all of this user’s trips 
trips_in_first_30_days: the number of trips this user took in the first 30 days after signing up
luxury_car_user: TRUE if the user took a luxury car in their first 30 days; FALSE otherwise
weekday_pct: the percent of the user’s trips occurring during a weekday
```
_Note that this dataset cannot be shared in this public repository_

### Analysis <a name="analysis"></a>

The case study team decided to approach this 

**Work Flow**

1. Perform any cleaning, exploratory analysis, and/or visualizations to use the provided
   data for this analysis.
   
2. Build a predictive model to help determine whether or not a user will be retained.

3. Evaluate the model.
 
4. Identify / interpret features that are the most influential in affecting predictions.

5. Evaluate the validity of the model.

6. Repeat 2 - 5 until a satisfactory model is developed.


### Results <a name="results"></a>


### Conclusions <a name="conclusions"></a>


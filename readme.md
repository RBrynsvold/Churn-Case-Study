# Case Study - Churn Prediction


## Executive Summary


## Table of Contents
1. [Motivation](#motivation)
2. [Analysis](#analysis)
3. [Results](#results)
4. [Conclusions](#conclusions)


### Motivation <a name="motivation"></a>

A ride-sharing company (Company X) is interested in predicting rider retention.
To help explore this question, my case study team and I examined a sample dataset of a cohort of 
users who signed up for an account in January 2014. The data was pulled on July 1, 2014; 
we consider a user retained if they were “active” (i.e. took a trip) in the preceding 30 days 
(from the day the data was pulled). In other words, a user is "active" if they have taken a trip 
since June 1, 2014.

We were interesed in understanding what factors are the best predictors for retention, and 
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

The case study team decided to approach this problem by fitting and evaluating several different 
models to compare their accuracy and look for agreement in churn prediction features.  These 
models were:

* Logistic Regression
* K-Nearest Neighbors (kNN)
* Random Forest
* Support Vector Machine (SVM)
* Gradient Boosted Trees

The target in all of these model predictions was whether or not a customer would churn.

In fitting and evaluating our respective models, each group member followed this general **Work Flow**:

1. Perform any cleaning, exploratory analysis, and/or visualizations to use the provided
   data for this analysis 
2. Build a predictive model to help determine whether or not a user will be retained
3. Evaluate the model
4. Identify / interpret features that are the most influential in affecting predictions
5. Evaluate the validity of the model
   * Cross-validation
   * Test set actual churn result vs. model-predicted churn
6. Repeat 2 - 5 until a satisfactory model is developed

### Results <a name="results"></a>

The best out-of-sample predictive performance was obtained with the Gradient Boosted Trees model,
with an accuracy of 79.2%

The feature importance scoring of the Gradient Boosted Trees model yielded the following as the 
three most important features:

1. city
2. weekday_pct
3. surge_pct

For details on the performance of the other models (including a ROC curve for each), see the 
slides included in this repository.

### Conclusions <a name="conclusions"></a>

 The importance of the 'city' feature would suggest that (as would be expected) different markets
 will have different customer engagement with and loyalty toward the ridesharing service, and 
 resources such as advertising or discount promotions should be targeted to certain markets to 
 maximize the return on the investment.  The impotance of the 'weekday_pct' feature would suggest
 that those that ride on weekdays (presumably, those that use ridesharing as part of their daily
 commute) are lower-churn customers, and that a campaign aimed at building numbers of these users
 could mean longer-term gains than a campaign aimed at weekend users.  Finally, the importance of
 the 'surge_pct' feature would suggest that users are turned off by high-surge rides, and that 
 it would be advisable for the rideshare company to do further analysis to compare the increase
 in profits that comes from surge pricing vs. the lost profits from customers that may have been 
 prompted to churn by these surge prices.  A profit curve analysis could help determine the
 surge pricing scheme that maximizes profits by balancing these opposing forces (additional 
 profits vs. churn)

Interestingly, the Random Forest model, which at 74.9% was only slightly less accurate the the
Gradient Boosted Trees model, had a completely different feature scoring result.  This indicates
that more work should be done to understand the mechanisms at play before considerable resources
are expended to enact any of the above recommendations.

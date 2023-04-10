Airfare Price Prediction

Statement of Issue 
It can be hard to guess airline ticket rates, we might see a fare today, find out the price of the same flight tomorrow,
it's going to be a different story. We may have heard travelers sometimes complain that the costs of airline fares are too volatile.
As data scientists, we can show that something can be expected provided the correct data. 

1) Data Exploration
Feature variables

Airline: The name of the airline.
Date_of_Journey: The date of the journey
Source: The source from which the service begins.
Destination: The destination where the service ends.
Route: The route taken by the flight to reach the destination.
Dep_Time: The time when the journey starts from the source.
Arrival_Time: Time of arrival at the destination.
Duration: Total duration of the flight.
Total_Stops: Total stops between the source and destination.
Additional_Info: Additional information about the flight

Target Variable
Price: The price of the ticket

2) Data Cleaning
Two null values found which were then removed
Route was removed
Additional_Info was removed
Arrival Time was removed

3) Feature Engineering

Feature Extraction
Journey month was extracted from Date_of_Journey
Journey day was extracted from Date_of_Journey
Departure minutes was extracted from Dep_Time
Departure hour was extracted from Dep_Time
Duration hour and Duration minutes were extracted from Duration

Feature Encoding
Duration minutes were encoded
Airline was encoded (One Hot)
Source was encoded
Destination was encoded
Total_stops was encoded

4) Data Visualization
Airline vs Price (Lineplot and Boxplot)
Source vs Price (Boxplot)
Heatmap of Correlation was plotted to select appropriate features

5) KFold Cross Validation
Linear Regression, KNN(Regressor), SVM(Regressor), Random Forest(Regressor), Decision Tree(Regressor)

Linear Regression 0.6179099793115541
KNN 0.40794821526134684
Decision Tree Regressor 0.6705725263524906
Random Forest Regressor 0.8132188409219161
SVM -0.0038753252561708694
AdaBoost 0.3853050182388652

6) Hyperparameter Tuning
Random Forest Regressor
R2 Score of Random Forest is 0.7601890985139343 where criterion is 'squared_error', n_estimators are 10 
max_depth is 18 ,max_leaf_nodes are 42 and min_samples_split is 12

R2 Score of Random Forest is 0.4582142819025393 where criterion is 'poisson', n_estimators are 10 
max_depth is 18 ,max_leaf_nodes are 42 and min_samples_split is 12

7) Model Fitting
Algorithm is <class 'sklearn.linear_model._base.LinearRegression'> and its score is 0.6244170576900374
Algorithm is <class 'sklearn.tree._classes.DecisionTreeRegressor'> and its score is 0.9803996114917645
Algorithm is <class 'sklearn.svm._classes.SVR'> and its score is 0.00010943867670232255
Algorithm is <class 'sklearn.ensemble._forest.RandomForestRegressor'> and its score is 0.9619617676206139
Algorithm is <class 'sklearn.neighbors._regression.KNeighborsRegressor'> and its score is 0.6279371517660898
Algorithm is <class 'sklearn.ensemble._weight_boosting.AdaBoostRegressor'> and its score is 0.4311096254419491

8) Best Model
Random Forest Regressor(criterion='squared_error', n_estimators=10, max_depth=18, max_leaf_nodes=42, 
                                  min_samples_split=12)

9) Evaluation
Training Score is 0.790767940049389
Testing Score is 0.750773084114793
R2 Score is 0.750773084114793
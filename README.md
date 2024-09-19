
# Machine Learning with US Airline Flight Routes and Fares 1993-2024 Dataset Supervised-and-Unsupervised-Algorithm

##  Aim of the Project :
This project aims to help airlines optimize pricing and plan routes more effectively. 


**Kaggle notebook with the EDA part of the project**
*  --> https://www.kaggle.com/code/akadir0223/flights-eda

**Kaggle notebook with a short data analysis and model building part of the project**
*  --> https://www.kaggle.com/code/akadir0223/flights-fare-prediction

## Dataset : 
The dataset used consists of 245,955 rows and 23 columns. The columns are respectively as follows:

- **tbl**: Table identifier
- **Year**: Year of the data record
- **quarter**: Quarter of the year (1-4)
- **citymarketid_1**: Origin city market ID
- **citymarketid_2**: Destination city market ID
- **city1**: Origin city name
- **city2**: Destination city name
- **airportid_1**: Origin airport ID
- **airportid_2**: Destination airport ID
- **airport_1**: Origin airport code
- **airport_2**: Destination airport code
- **nsmiles**: Distance between airports in miles
- **passengers**: Number of passengers
- **fare**: Average fare
- **carrier_lg**: Code for the largest carrier by passengers
- **large_ms**: Market share of the largest carrier
- **fare_lg**: Average fare of the largest carrier
- **carrier_low**: Code for the lowest fare carrier
- **lf_ms**: Market share of the lowest fare carrier
- **fare_low**: Lowest fare
- **Geocoded_City1**: Geocoded coordinates for the origin city
- **Geocoded_City2**: Geocoded coordinates for the destination city
- **tbl1apk**: Unique identifier for the route
----

The dependent variable was determined as “ fare”.
Various algorithms were used to predict the value of “ fare”.
Although it was deleted later, all regression algorithms were tried and finally RandomForestRegressor() was the best working algorithm, so it was continued with it.
KMeans, one of the Unsupervised Learning algorithms, was used.

The model score was improved by hyperparameter optimization.

The evaluation result for RandomForestRegressor is as follows : 
----

**Model Performance**
* Average Error: 18.5220 degrees.
* Accuracy = 91.00%.
* Mean Squared Error: 755.4095027366814
* Mean Absolute Error: 18.522000200718868
* R² Score: 0.843834237560804
* sonuçlar optimizasyon sonrası bu hale gelmiştir.
---
The scores obtained for KMeans are as follows : 
---
* The following Performance metrics measure the quality of clusters. Metrics on clustering performance i.e. : 
* Silhouette Score for 4 clusters: 0.46371227067631293
* Davies-Bouldin Index for 4 clusters: 0.7062882332826151
---

### Evaluation of Results
**RondomForest**
* The model predicts with 91% accuracy, indicating that most of the model's predictions are quite close to the true values.
* An R² score of 0.8438 indicates that the model explains 84.38% of the target variable. That is, the model has a strong predictive power based on the data.


## Comment on The Success Difference Between Algorithms
The K-Means algorithm is designed for clustering and is not directly used in regression problems. Clustering algorithms, which aim to partition data points into clusters, perform poorly when estimating a continuous target variable. Therefore, K-Means is not a suitable approach to predict a numerical value such as the average ticket price.

However, Unsupervised ML algorithms such as KMeans are indirectly used in regression problems for feature selection. The fact that it failed in this study does not mean that it is completely irrelevant for regression problems.

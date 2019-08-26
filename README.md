# BOS_Bluebikes_Predictions

Bluebikes is a continuously growing bike share system serving Boston and the four nearby cities, Somerville, Cambridge, Brookline, and Everett. Our goal is to recommend sensible locations for new Bluebikes stations for their future expansion. 

In "clean_process_triphistory.ipynb", Bluebikes trip history from August 2017 to July 2019 is aggregated to compute the average number of trips per month per existing bike station. 

In "clean_process_metrostation.ipynb", we obtain the coordinates of MBTA stations (not including the stations on the Silver line or the Mattapan Trolley) and label each station to which line it belongs. 

In "clean_process_bikestation.ipynb", we read in live station data from https://member.bluebikes.com/data/stations.json and group stations into 7 zones: downtown Boston, East Boston, West Boston, South Boston, Cambridge, Somerville, and Everett.
A few things to note: <br />
-East Boston includes East Boston and Charlestown.<br />
-West Boston includes Allston, Brighton, Brookline.<br />
-Here, South Boston means the residential part of Boston and DOES NOT mean the "South Boston in the city".

In "model_train.ipynb", Linear Regression model, Random Forest Regressor, Gradient Boost Regressor, and Sequential Neural Network models were explored. 

Among them the best model was the Graident Boost Regressor which has the test score (R^2 score) 81.7%. 

The 5-fold validation score is 76.4%. 

In "predict_new_bike_stations.ipynb", we update the dataset MBTA station to include 6 new metro stations that are part of Green line extension project spanning Cambridge, Somerville, and Medford scheduled for completion in 2021. For more information, visit https://www.mass.gov/info-details/about-the-green-line-extension-project. 

We were able to recommend 21 new bike station locations. These are the locations <br /> 1. where the current bike station density is not too high, <br /> 2. near the current bike stations which often have shortage of bikes,<br /> 3. where the user volume prediction is high. 

The visual map is included in "predict_new_bike_stations.ipynb".  


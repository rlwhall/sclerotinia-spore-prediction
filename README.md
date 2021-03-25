# **Sclerotinia Spore Prediction**
  
<br />

## Goal<br>
The goal of this project was to create a predictive model that could forecast spore levels of sclerotinia, an agricultural fungus.
<br />

The spore count data for this project was generously provided by Jonathan Reich (jonathandreich@gmail.com) and Sayama Chatterton from the [Lethbridge Research and Development Centre](https://www.agr.gc.ca/eng/scientific-collaboration-and-research-in-agriculture/agriculture-and-agri-food-research-centres-and-collections/alberta/lethbridge-research-and-development-centre/?id=1180547946064).
<br />

## Motivation<br>
Sclerotinia is a widespread and serious agricultural disease that effects a wide variety of crops across multiple continents. An infection can greatly decrease crop yields, up to 50% in some cases. Accurately predicting the risk of a sclerotina infection can help growers identify the timing of fungicide applications to reduct the risk of an outbreak.
<br />

There are multiple risk factors that can lead to a following infection, such as environmental conditions, leaf cover, crop rotaion history, and the plant growing cycle, but the sclerotinia life cycle begins with the release of spores from the soil. These spores are dispered into the air before settling onto a crop. Being able to predict the timing and magnitude of these spore events is an important part of forecasting overall sclerotinia risk.
<br />

<br />

**Directories**
* **Final-files:** Copies of the final project files.


<br />

## Project Overview

**Spore Count Data**
<br />
* The dataset consisted of 933 spore count samples collected from 17 field sites in Southern Alberta. The data was collected over a period of three years, 2018 to 2020, during the summer season(mid-June to end of August). 

**Weather Data**
<br />
* Weather data was gathered for each field site using the [Alberta Climate Information Service (ACIS)](https://agriculture.alberta.ca/acis/) historical weather database. Field sites were matched with their closest geographical weather station.
* **Note:** The original spore dataset also included weather data from onsite weather stations. However, this data was not used due to a high proportion of missing values. 

**Feature Engineering and Selection**
* The release of soil stored spores is greatly influenced by temperature and moisure levels. As such many new features were created and tested realting to precipitation, dewpoint and temperatures. In particular, features were add that captured weather patterns over the previous seven days. 
* A modelling pipeline was created, and Scikit-learn's SelectKBest module was used to help with feature selection.
* PCA was also explored as a dimensionality reduction option and feature engineer option.
* Both label encoding and dummy variable creation were explored for categorical variables.
<br />


**Modelling – Regressor**
* A number of different baseline regression models were tried, including: linear regression, lasso regression, ridge regression, SVM, GradientBoostingRegressor, RandomForest and XGBoost.
* XGBoost was chosen as the final regressor, and a python pipeline was created for the model.
* A regressor with high accuracy for precise spore counts could not be developed, but the model was highly correlated with the ground truth values, and the model was able to capture the timing of large spore events.
<br />

**Classification**
* A custom classification threshold was found and subsequently used to build a classification function to identify spore events.
<br />
<br />

## Conclusions

This project was able to accurately predict high spore count events through a regression-classification ensemble. 
<br>
This outcome demonstrates promising potential for even better regression performace given additional features such as field level weather and irrigation data, crop rotation history, and previous infection rates. 
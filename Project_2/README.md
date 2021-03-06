# Project 2 - Ames Housing Data and Kaggle Challenge


## Overview
  
Ames is a city in Story County, Iowa, United States, located approximately 30 miles (48 km) north of Des Moines in central Iowa. This project aims to predict the price for a list individual residential properties sold in Ames provided by Kaggle. Data set leveraged contains information from the Ames Assessor’s Office used in computing assessed values for individual residential properties sold in Ames, Iowa from 2006 to 2010.

## Data dictionary
  
Data dictionary can be found [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

## Conclusions

This project's model predicted sales prices with a root mean squared error of 31,165. Baseline score is approximately 55,000 and Kaggle's leaderboard top 50 scores are around 20,000 to 33,000.

1. Model had low usage of location features (only MSZoning was used). Most location features were categorical and dummy variables take up too many feature space.
2. Best predictors are area and overall quality.
3. Occam's razor stands true - feature engineering did not provide big benefits.
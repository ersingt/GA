# Ames Housing Data Analysis

### Problem Statement:

#### What home features deliver higher sale prices? 
In other words, given the number of available features per house, which ones are the best predictors of sale price? 
 
### Executive Summary
This analysis uses the Ames, Iowa housing dataset, listing home sales from 2006 to 2010, to assess home features that impact sale price. Using standard Exploratory Data Analysis (EDA) techniques, feature engineering, and linear regression modeling, this analysis identifies several home features of high impact on home sale prices. Specificaly, three features and one note of caution present themselves: 

- 1. Remodeling a home can help mitigate the effects of home age.
- 2. The overall quality of material and finish is a strong predictor of price. 
- 3. Livable square footage, though obvious, is a strong predictor of price
- 4. Analysis of spatial patterns in the data as predictors of price should be avoided without a more comprehensive understanding of the local underlying socioeconomic factors.

Given the relative impacts of the above features on home sale price according to our models and explained in further detail below, we recommend focusing on Remodeling, material and finish quality, and livable square footage as predictors of sale price.    

### File Directory:
- notebooks
   - EDA.ipynb   
   - DataCleaning.ipynb   
   - FeatureEngineering.ipynb
   - Modeling.ipynb  
   - Graphicss.ipynb  
- datasets
   - train.csv
   - test.csv
   - train_cleaned.csv
   - test_cleaned.csv
   - train_cleaned_engineered.csv
   - test_cleaned_engineered.csv
- output
   - age_at_scale.scatt.png
   - lot_frontage.scatt.png
   - overallqual.box.png
   - sqft_total.scatt.png
   - yrs_since_remod.scatt.png
- predictions
   - ers_predict_03.csv
   - ers_predict_04.csv
- presentation
   - ames_housing_20200410.pdf
- README.md

### Data Dictionary:
The Data Dictionary for the entire dataset of ~80 variables can be found here: https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/data

The final variables selected for modeling in this analysis are as follows:

|Feature|Type|Description|
|---|---|---|
|log_SalePrice|int64|Log of Sale Price|
|Sq Ft Total|float64|Sum of 1st floor, 2nd floor, and basement SqFt variables|
|Overall Qual|int64|Ordinal measurement (1-10) of Overall Home Material and Finish Quality|
|Lot Frontage|float64|Linear feet of street connected to property|
|Home Age|int64|Age of home at time of sale|
|Yrs Since Remod|int64|Years since remodeling or addition at time of sale|
|Has Fence|int64|Indicator variable describing fence presence(1) or absence(0)|
|Has Wood Deck|int64|Indicator variable describing wood deck presence(1) or absence(0)|
|Has Masonry|int64|Indicator variable describing exterior masonry presence(1) or absence(0)|
|Has Fireplace|int64|Indicator variable describing fireplace presence(1) or absence(0)|
|Has Garage|int64|Indicator variable describing garage presence(1) or absence(0)|
|Has Pool|int64|Indicator variable describing pool presence(1) or absence(0)|
|Exter Qual|float64|Ordinal measurement (0-4) of exterior quality|
|Exter Cond|float64|Ordinal measurement (0-4) of exterior condition|
|Bsmt Cond|float64|Ordinal measurement (0-4) of basement condition|
|Bsmt Qual|float64|Ordinal measurement (0-4) of basement quality|
|Kitchen Qual|float64|Ordinal measurement (0-4) of kitchen quality|

### Findings:
Include charts + interpretations:





### Conclusions and Recommendations:

tie back to problem statement 

Total Square Footage:
1-Sqft Increase:
Associated with a $46.97 increase in sale price, all else equal.

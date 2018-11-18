## Predicting House Prices in Ames, Iowa using Machine Learning

Data Set from the House Prices: Advance Regression Techniques competition on Kaggle: 
https://www.kaggle.com/c/house-prices-advanced-regression-techniques/

Machine Learning Project for NYC Data Science Academy
Cohort 15


## Overview

The data was provided as train.csv (with house prices), and test.csv (new observations with all the same features as train.csv, but missing the Sale Price). We processed the train.csv dataset, performed feature engineering by a number of methods and optimized model hyperparameters using K-fold splitting, performed a stacking algorithm of different models based on train/test optimization, and created the final csv file for Kaggle submission.

We essentially performed 2 different runs with our data:

**Run 1** -- Cleaned/processed train.csv and test.csv separately. Did not perform manually-assessed feature removal or feature creation. Obtained feature lists by AIC, Lasso, and GBoost, and manually curated these lists bases on optimal score in train/test modeling.

**Test Score (RMSLE): 0.113, Kaggle Score: 0.130**

**Run 2** -- Cleaned/processed train.csv and test.csv together. Performed manual feature removal/alteration based on detailed reading of the data description file. Obtained feature list using AIC minimization method and applied this list in model development with no changes.

**Test Score (RMSLE): 0.122, Kaggle Score: 0.118**



## Repository Contents

### Data cleaning and processing:

#### Run 1:

**AmesDF_Processing** -- Processing/cleaning of train.csv only, without additional feature removal/creation. Associated with Run 1

**Ames_Final_Feature_DF** -- Script to create final Train DF with manually-tested feature list. Associated with Run 1

**Ames_TestSet1_Processing_Run1_XGB_Submission** Processing/cleaning of test.csv and applying the stacked (linear/gboost/random forest) model to the test data, using the feature list computed in Run 1

#### Run 2:

**Ames_TestTrain_Processing_Run2_Submission** -- Joint processing of the test.csv and train.csv, and creating and submission of the second prediction csv for Kaggle

### Feature Engineering:

**AmesDF_Multicollinearity_Feature_Reduction** -- Checking the processed DF for signs of multicollinearity and correlation between features. Also performing AIC feature selection algorithm associated with Run 1.

**AmesDF_FeatureSelection_AfterManualRemoval** -- Multicollinearity and correlation check of processed data from Run 2, and Feature Engineering for Run 2 using a random feature selection algorithm to minimize AIC.

**Feature_Engineering_Lasso** -- Use of Lasso algorithm to choose optimal lambda values and engineer exclusion list of features whose coefficients decrease to 0 after regularization penalty. Features were normalized using min/max standardization to avoid bias

**Feature_Engineering_GradientBoost** -- Use of GradientBoostingRegressor to detemine a relevant candidate feature list using the feature_importances_ method

### Modeling and hyperparameter optimization:

**Modeling_Linear** -- K-Fold testing of multiple linear regression using features from AIC optimization

**Modeling_Ridge_AllStandardized** -- Choosing optimal lambda hyperparameter using train/test modeling, with the features having non-zero coefficients from Lasso feature engineering

**Modeling_RandomForest** -- K-Fold testing and hyperparameter optimization using the RandomForestRegressor algorithm from sklearn, using feature list generated from AIC optimization

**Modeling_GBoost_AIC** -- K-Fold hyperparameter optimization and modeling using GradientBoostingRegressor from sklearn, with the feature list generated from AIC optimization

**Modeling_Elasticnet** -- Choosing optimal alpha and rho hyperparameters for balancing Ridge/Lasso regularization algorithms using train/test modeling

### Model stacking and train/test comparison:

**Stacking_FinalFeatures_Run1_WithXGB** -- Stacking model for Run 1, where a 24% XGBoost, 36% Gradient Boost, 20% Random Forest, and 20% linear stacked model was found to be best against the test set 

**Stacking_FinalFeatures_Run2** -- Stacking model for Run 2, which suggested an optimal balance of 40% gradient, 35% random forest, and 25% linear model (0% Ridge)


### Test.csv prediction and Kaggle submission:


### Individal subfolders:

These subfolders contain pre-work or work that was not part of the final process pipeline

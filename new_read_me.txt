Dave folder:

ipython Notebooks:


AmesDF_Multicolinearity_FeatureReduction:
The first attempt to do Feature selection, and remove some features based on high collinearity or for being too sparse. 


Ames_Gradient_Boosting_Test: 
This was my version of hyperparameter tuning (K-fold) for gboost, using the feature list I had

Ames_Random_Forest_Test:
This was my version of hyperparameter tuning (K-fold) for randomForest, using the feature list I had

Ames_Linear_Model_Tests: 
This was a script to K-fold test linear models, with various imported Feature DFs


AmesDF_Processing:
The first processing page. Did not manually alter features (except for BsmtScore and Month>Season), and Dummified before making ordinal, which looked a little bit unorganized. Only did the train.csv DF

AmesDF_Processing_Ordinal_First:
Basically the same as AmesDF_PRocessing, but importantly, it does the ordinal categories first, which makes the script look simpler and keeps us from having to do that strange function where we input some numbers manually.




Ames_Final_Feature:
This was a small script which took Denises xgbFeatures.csv, which had the primary features we wanted, retreieved this feature list, modified it with a few features we had agreed on, then exported a final test CSV (AmesDummiesOrdinalF.csv)

Ames_Overall_Models_and_Stacking_FinalFeatures:	
This script is used to import a Final Training DF, and run it through the stacked model and get a predicted RMSLE score, as well as some graphs.

Ames_TestSet_Processing_Submission:
This was where we manually processed the Test.csv DF, then ran it through the stacked model and submitted it the first time



Ames_TestTrain_Processing_FeatureReduction_Submission:
This is the 3rd version of the processing. Here, I processed Test and Train together, made some manual decisions about feature reduction/combination, and numbering, and then (after doing the random AIC feature selection on another page) submitted the prediction CSV.

AmesDF_FeatureSelection_AfterManualRemoval:
This is where I did the random-AIC-generating feature selection, after manually altering/removing some feature beforehand. Used to get the featurelist with 0.118 score.

Ames_Overall_Models_and_Stacking_FinalFeaturesDJC:
This is the new version of the file where I imported features from the ReducedFeature analysis and checked the stacked model, giving a score of 0.122.
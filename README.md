# mod-3-final-project
By Kenny Oh and Moses Lin

# Goal
To create a classification model that can correctly predict whether a subject will be arrested at a Terry Stop based on various parameters of the officer and subject. We will also analyze certain features such as officer/subject race/gender to see if there is any significant association between them and arrests.

# Data Resource:
This data represents records of police reported stops under Terry v. Ohio, 392 U.S. 1 (1968). Each row represents a unique stop.

* Each record contains perceived demographics of the subject, as reported by the officer making the stop and officer demographics as reported to the Seattle Police Department, for employment purposes.
* Where available, data elements from the associated Computer Aided Dispatch (CAD) event (e.g. Call Type, Initial Call Type, Final Call Type) are included.

# Statistical Tests
We conducted Chi Square Tests on Subject Race/ Officer Race/ Time of Day/ Subject Gender, and Arrests, and found a significant association between these characteristics and Arrests. However, we do not know which exactly have an association and to what degree.

# Class Imbalance
Our dataset had a large imbalance, with 94.56% of the cleaned data leading to no arrests. To deal with this, we utilized SMOTENC as almost all of our features were categorical. Because of such an imbalance, we needed to take into consideration F1 score and not Accuracy during modeling.

# Modeling
We created 4 different classification models: Logistic Regression, KNN, Decision Tree, and Random Forest. Logistic Regression gave us the best model with 0.394 F1 score. Afterwards we used Grid Cross-Validation on LR and Random Forest and obtained a worse and slightly better (0.356 -> 0.378) F1 scores respectively.

We also implemented XGBoost which only had a 0.357 F1 score. Using Grid Cross-Validation increased the score to 0.383

Our Voting Classifier, which combined all of the previous models, gave us a F1 score of only 0.384

As a result, we would use the Logistic Regression model when predicting unseen datasets.

# Conclusion
Our Logistic model, based on F1 score, is supposedly 39.4% accurate when predicting arrests based on various parameters of the Terry Stop encounter. Perhaps the reason the F1 score is so low is because arrests simply cannot be predicted very well from just Terry Stop parameters alone.

# Future Work
- We could look into data for police reported stops in other regions.
- We could focus more on specifics of the Seattle Police Department.
- We could gather data on arrests in general, not just as Terry Stops.

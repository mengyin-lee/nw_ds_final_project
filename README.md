# Final-Project

### NW Data Science Bootcamp Final Project Report 
– Happiness Analysis and Prediction w Machine Learning
### Team Members: Ivan Choi, Paul Smith, Meng-Yin Lee

-Google Drive: https://drive.google.com/drive/folders/19rd_mrhzEEKfVz2Qv6fnOeG0r8fNI9eI?usp=sharing

-GitHub Repository: https://github.com/RebelDroid09/final-project.git

-Tableau Public: https://public.tableau.com/profile/ivan.choi#!/vizhome/FinalProjectMap_16137055299100/Story1?publish=yes


##### The definition of the Happiness Score is based on survey results, that was first used in the 2012 World Happiness 
##### Report. In the survey, the respondents were asked to rate their happiness on a scale from 0 to 10. The Happiness 
##### Score is calculated by averaging the survey results of the respondents.

### World Happiness Report found a number of key factors that could likely explain the variance in happiness.
1.	GDP per capita:
2.	Social support 
3.	Healthy life expectancy
4.	Freedom to make life choices
5.	Generosity
6.	Perceptions of corruption

### Machine Learning Workflow

1.Collect and Prepare the data
-	Utilize AWS S3 and RDS
-	Database: PostgreSQL
-	Drop data with missing values or fill in with mean value.
	
2.Analyze the data in Python
- Utilize sklearn, statsmodels, seaborn, pandas, seaborn, numpy, matplotlib
- Data Analysis
-	Use scatter plot and find Pearson Correlation coefficient for each factor
-	Checking for multicollinearity
-	Use seaborn stripplot to further analyze outliers

3.Create the Machine Learning Model
-Multiple Linear Regression
##### Based on our data analysis and the nature of the data sets, we have selected multivariate/multiple linear regression to build the model.
##### When implementing linear regression in a machine learning system, the variables must be continuous in nature, not categorical.
#### The variables in our datasets are continuous variables, so we don't need to encode them at all.
##### A linear regression carried out on more than one independent variable, comparing the correlations between features for the given number of features.


4.Train the Model
##### Data volume: 782 records, from 2015 to 2019 kaggle data sets

##### X=[["GDP per capita", "Social support", "Healthy life expectancy", "Freedom to make life choices", "Generosity", "Perceptions of corruption"]]

##### y=["Score"]

##### X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.2, random_state=9)

5.Evaluate the model
##### To validate our regression models, we use R2, RMSE and Residual plots to visually confirm the validity of your model.
##### Calculate R2 (R-squared ) and RMSE (Root mean square erro)
- Training R2 Score: 0.7755999127353526
- Testing R2 Score: 0.7151408209729091
- Test Set RMSE: 0.6100957246059002
- Test Set R2: 0.7151408209729091


-  Prediction with Input
##### Multiple linear regression formula
##### The formula for a multiple linear regression is:
#####
##### y= B0 + B1X1 +...+ BnXn + e

##### Using 2019 Finland as example to evaluate prediction. Finland score was 7.769, rank 1
*New_GDP = 1.34
*New_Social_Support = 1.58
*New_Health = 0.986
*New_Freedom = 0.596
*New_Generosity = 0.153
*New_CDI = 0.393
*print ('Predicted Score: \n', regr.predict([[New_GDP ,New_Social_Support, New_Health, New_Freedom, New_Generosity,New_CDI]]))

### Predicted Score: [[7.02453596]]


##### Using 2019 South Sudan as example to evaluate prediction. South Sudan score was 2.853, rank 156

*New_GDP = 0.306
*New_Social_Support = 0.575
*New_Health = 0.295
*New_Freedom = 0.01
*New_Generosity = 0.202
*New_CDI = 0.091
*print ('Predicted Score: \n', regr.predict([[New_GDP ,New_Social_Support, New_Health, New_Freedom, New_Generosity, New_CDI]]))

### Predicted Score: [[3.40548722]]


### Conclusion:

##### With the individual key factor data analysis and multiple liner regression model we can obtain about 70% accuracy comparing to World Happiness Report happiness score.

##### We might be able to use this model to predict personal happiness with personal happiness key factors.

##### However, we have to accept that there is a part of the Happiness Score that cannot be explained by other – more easily measurable – factors.







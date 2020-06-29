# Wine Quality Project: Project Overview
This project is based on the Kaggle dataset by UCI Machine Learning. This project lists many different variables that make up the "Vinho Verde" Portuguese wine, as well as the numeric quality of the wine on a scale from 1-10. The different data points are also ordered and not balanced, meaning there are more normal types of wine than anything else. I chose to put together a multiple linear regression analysis to find the relationship between the variables that most closely correlated to the quality of the wine.

# Prerequisities 
* Python 3.8 3 
* Jupyter Notebooks - Python Anaconda Suite 
* Red Wine Quality Dataset: https://www.kaggle.com/uciml/red-wine-quality-cortez-et-al-2009
* Optional: Knowledge of CRISP-DM Workflow

# CRISP-DM Stages 
## Understanding Business Objectives
In a real world senario, I would be doing this project to figure out what manufacturers and wine-makers could do to increase the quality of their wine, and overall increase sales. The two main objectives for this project were to 
1. Find which variables correlate closely to quality of the wine 
2. Create a model that predicts the quality of wine based off of correlated variables 

## Data Understanding and Data Cleaning
After diving into the data, I found that the amount of outliers was causing the data to become unevenly distributed. I created an interquartile range (IQR) function that allowed me to eliminate the bottom 25% of the distribution and the top 25% of the distribution. This was the only cleaning that I really needed to do, as the data was in the right format and there was no missing or corrupt data.

## Construct Data 
After cleaning and understanding the data, I went into some basic statistical analysis. I found that there were 3 variables that had a correlation high enough to warrent futher analysis:
1. Alcohol: 0.46 
2. Sulphates: 0.38 
3. Citric Acid: 0.23 
Alcohol and sulphates also had a correlation of 0.21. After finding these correlations, I started on my model.

## Modeling
For my model, I set x to "alcohol", "sulphates", and "citric acid", and y to "quality". After running the model, I found an R^2 score of 0.31, warrenting further analysis within the model. I also found the following coefficients for each variable: 
1. Alcohol: 0.31 
2. Sulphates: 1.84 
3. Citric Acid: 0.43 
While the correlation between alcohol and quality was high, the regression coefficient of sulphates indicate that there is a stronger relationship between sulphates and the dependent variable, quality, than alcohol. As sulphates change, so does the quality. 

# Conclusion 
After modeling, I found that an increase in sulphates can increase the quality of wine from a numeric standpoint.

<img width="316" alt="2" src="https://user-images.githubusercontent.com/65836934/85966246-c3cc7700-b984-11ea-835b-064092c2bb9d.png">
<img width="313" alt="Annotation 2020-06-28 185530" src="https://user-images.githubusercontent.com/65836934/85966247-c4650d80-b984-11ea-8196-97e41592c0fc.png">

# The Minimum Viable Product (MVP) for Microsoft Malware Prediction 
### This jupyter_notebook contains :
- Downloading the dataset 'train.csv' from Kaggle and cut the data to be only 10,000 rows 
- Exploring the data 
- Dealing with missing value and drop the empty columns
- Using function 'get_dummy' to convert the categorical features to numorics
- Because the features in the dataset too large '12346' columns so, I prefer to use machine learning model to select the best features
- Applying three methods to select the features
- Apply logistic Regression on the three methods by using 'Pipline' and 'GrideSearch'.

#### Logistic Regression Model
| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| ExtraTreesClassifier  | 0.564 | 0.503 |
| SelectKBest |0.564  |0.548|
|Random Forest Feature Importances |0.556 | 0.54|


<b>This best score that I got by using 'SelectKBest' method and the confusion_matrix shows below:

![My image](https://github.com/NohaZamaan/MVP/blob/main/Screen%20Shot%201443-04-02%20at%201.50.16%20AM.png)</b>
### Conclusion :
I applied Logistic Regression model on the three methods but unfortunately I got bad scores for all three.<p>
Now , I'm trying to apply more models on the features and I will do scaling on the three methods before modeling
to improve the prediction of models.




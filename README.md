# The Minimum Viable Product (MVP) for Microsoft Malware Prediction 
### This jupyter_notebook contains :
- Downloading the dataset 'train.csv' from Kaggle and cut the data to be only 10,000 rows 
- Exploring the data 
- Dealing with missing value and drop the empty columns
- Using function 'get_dummy' to convert the categorical features to numorics
- Because the features in the dataset too large '12346' columns so, I prefer to use machine learning model to select the best features
- Applying three methods to select the features
- Apply logistic Regression on the three methods by using 'Pipline' and 'GrideSearch'.


#### Conclusion :
I applied Logistic Regression model on the three methods but unfortunately I got bad scores for all three.
Now , I will tried to apply more models on the features and I will do scaling on the three methods before modeling
to improve the prediction of models




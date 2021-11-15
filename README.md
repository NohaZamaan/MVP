# Project Name: Microsoft Malware Prediction 
---

<b>By:</b>  Noha Abdulwahab Zamaan

---

## CONTENTS :
 * Introduction
 * Libraries
 * Data Preprocessing and Feature Engineering
 * Methodology 
   - EDA
   - Exploratory Data Analysis
   - Visualizing dataset
   - Modeling
 * Project outcome
 * Recommendation and Conclusion 
 * Resources

---

### Introduction:

Industries of malware and hacking are very powerful and growth sharply. It works to harm millions of victims and companies. These industries have great funding from a variety of organizations and people to meet their purposes. However, large global companies like Microsoft work hard to defense their customer from any attack.
Microsoft provides its dataset ‘ https://www.kaggle.com/c/microsoft-malware- prediction/overview ’ that includes many features about its consumer’s machine devices that collected by by Microsoft's endpoint protection solution and Windows Defender.<p> 
<B> Microsoft </B> challenges the data scientist to apply various machine learning models to predict malware before occurring.
  
---
  
### Libraries:
  
- <B> For reading file </B> --> Ex: pandas 
- <B> For Visualization </B> --> Ex:seaborn
- <B> For Modeling </B> --> Ex: RandomForestClassifier
- <B> For Metrics </B> --> Ex: accuracy_score
- <B> For scaling </B> --> Ex: StandardScaler
- <B> For validation </B> --> Ex: cross_val_score

---
  
### Data Preprocessing and Feature Engineering
  
The dataset was very big , it contains 8921482 rows so,I decided to cut it in  10000 rows.<p>
the dataset divided into a training set (90%) and a testing set (10%).<p>
There were 10 columns that have unavalible data or null so, I drop them all. <p>
Other features that had some missing values, presented to see the type of them. <p>
All missing values were in numorical columns, then Visualized to see thier distribustion <p>




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




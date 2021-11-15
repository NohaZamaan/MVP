<img src="https://github.com/NohaZamaan/Project_T5/blob/main/Images/%D8%A7%D9%94%D9%83%D8%A7%D8%AF%D9%8A%D9%85%D9%8A%D8%A9-%D8%B3%D8%AF%D8%A7%D9%8A%D8%A7.png" width="150" height="150"> Project Name: Microsoft Malware Prediction 
---

<b>By:</b>  Noha Abdulwahab Zamaan

***

## CONTENTS :
 * Introduction
 * Libraries
 * Data Preprocessing 
 * Methodology 
   - Dealing with Features
   - Modeling
 * Results and Conclusion 
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
  
### Data Preprocessing 
  
The dataset was very big , it contains 8921482 rows so,I decided to cut it in  10000 rows.<p>
the dataset divided into a training set (90%) and a testing set (10%).<p>
There were 10 columns that have unavalible data or null so, I drop them all. <p>
Other features that had some missing values, presented to see the type of them. <p>
All missing values were in numorical columns, then Visualized to see thier distribution <p>
![distribution](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.29.05%20PM.png) 
Most columns have unnormal distribution so, using 'median' to fill the missing value is the best. <p>
Using 'get_dummy' function to convert all categorical columns <p>
Then apply heatmap to approve no missing value in the data and print the new shape of the data   <p>
![missing](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.29.48%20PM.png) <p>  

---

### Methodology <p>
#### - Dealing with Features <p>
After using dummy, there are 12347 columns. It is unpossible to use all these features for modeling 
<p> So, I tried to use different techniques
- Select the best 10 features by:
   1)feature_importances_ from ExtraTreesClassifier: <p>
      
   ![feature_importances_](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.30.34%20PM.png) <p>
      
   2)SelectKBest from chi2:<p>
      
   ![SelectKBest](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.30.51%20PM.png) <p>
      
   3)feature_importances_ from RandomForestRegressor: <p>
      
   ![rf_feature_importances_](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.31.02%20PM.png) <p>
      
- Using Principal Component Analysis (PCA) with n_components=6 <p>
   
   
#### - Modeling

   - Logistic Regression Model with Pipline, Scaling, GridSearch <p>
   
| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| ExtraTreesClassifier  | 0.548 | 0.537 |
| SelectKBest |0.591 |0.596|
|Random Forest Feature Importances |0.549 | 0.562| 

<p> I select the best two score to apply the next model on them <p>
   
   - KNeighborsClassifier Model with Pipline, Scaling, GridSearch <p>
   
| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| SelectKBest |0.587  |0.592|
|Random Forest Feature Importances |0.505 | 0.499|
   
   - Random Forest Classifier Model with Pipline, Scaling, GridSearch <p>  
 
| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| SelectKBest |0.59  |0.596|
|Random Forest Feature Importances |0.585 | 0.585|
| PCA  | - | 0.54 |
      
   - Neural_Network Model <p>
      

| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| SelectKBest | - |0.581|

      
### Results and Conclusion 
      
- Random Forest was the best model performance with Scaling and GridSearch methods :+1: . However, it consumed the longest time in execution. <p>  
- The Feature_selection with ‘SelectKBest()’ function can be the best method when applying models on it, so, may approve it on huge features. <p>
- Still, the score isn’t good even though trying a variety  of parameters, GridSearch, and scaling the data. <p>
- Maybe it needs other features that have more correlation with the target, or there are external conditions that affect  the target. <p>
- This result leads us to agree that, some problems are still hard to predict their solution for them even though they have data about them. :shipit: <p>



### Resources:
      
[1] https://medium.com/@erikgreenj/k-neighbors-classifier-with-gridsearchcv-basics-3c445ddeb657 <p>

[2] https://towardsdatascience.com/random-forest-ca80e56224c1 <p>

[3] https://medium.com/@amrianto.saragih/4-methods-to-boost-the-accuracy-of-a-neural-network-model-bb694e650a69 <p>

[4] https://towardsdatascience.com/pca-using-python-scikit-learn-e653f8989e60 <p>

[5] https://towardsdatascience.com/machine-learning-step-by-step-6fbde95c455a <p>





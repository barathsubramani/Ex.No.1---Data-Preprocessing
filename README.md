# Ex.No.1---Data-Preprocessing
## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## RELATED THEORETICAL CONCEPT:

Kaggle :
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

Data Preprocessing:

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

Need of Data Preprocessing :

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
1. Importing the libraries
2. Importing the dataset
3. Taking care of missing data
4. Encoding categorical data
5. Normalizing the data
6. Splitting the data into test and train

## PROGRAM:
```
Name: Barath S
Ref no: 212222230018
```
```python
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split
```
```python
#read the dataset
df=pd.read_csv('Churn_Modelling.csv')
df
```
```python
df.drop('RowNumber',axis=1,inplace=True)
df.drop('CustomerId',axis=1,inplace=True)
df.drop('Surname',axis=1,inplace=True)
df.drop('Geography',axis=1,inplace=True)
df.drop('Age',axis=1,inplace=True)
df.drop('Gender',axis=1,inplace=True)
df
```
```python
#checking for null, duplicates, outliers in lasrt column
df.isnull().sum()
```
```python
df.duplicated()

df['Exited'].describe()

sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df),columns=['CreditScore','Tenure','Balance','NumOfProducts','HasCrCard','IsActiveMember','EstimatedSalary','Exited'])
df2
```
```python
#split dataset
x=df2.iloc[:,:-1].values #all rows from all except last column
x

y=df2.iloc[:,-1].values #all rows from only last column
y
```
```python
##creating training and test data
X_train, X_test, y_train, y_test = train_test_split(x, y, test_size=0.2)
print(X_train)
print("\n")
print(len(X_train))
```
```python
print(X_test)
print("\n")
print(len(X_test))
```
## Data Set and its properties
![model](1.png)
![model](3.png)
## Duplicated
![model](4.png)
## df['Exited'].describe()
![model](5.png)
## Normlised Data Set
![model](6.png)
## X and Y column data
![model](7.png)
![model](8.png)
## Training Data
![model](9.png)
## Test Data
![model](10.png)



## RESULT
Thus, the Data preprocessing is performed over a data set successfully.

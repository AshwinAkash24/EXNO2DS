# EXNO:2 DS- EDA Analysis Using Pyhton
## Name: Ashwin Akash M
## Register Number : 212223230024
## Date :
## Department : Artificial Intelligence And Data Science
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Colab Link:
https://colab.research.google.com/drive/12c6m3peqMZ7KdOOjM9odD_yZS-LeVWaJ?usp=sharing
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
```
df=pd.read_csv('titanic_dataset.csv')
df
```
![alt text](images/ds2-1.png)
```
df.info()
```
![alt text](images/ds2-2.png)
```
df.shape
```
![alt text](images/ds2-3.png)
```
df.set_index("PassengerId",inplace=True)
df
```
![alt text](images/ds2-4.png)
```
df.describe()
```
![alt text](images/ds2-5.png)
```
df.nunique()
```
![alt text](images/ds2-6.png)
```
df["Survived"].value_counts()
```
![alt text](images/ds2-7.png)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![alt text](images/ds2-8.png)
```
sns.countplot(data=df,x="Survived")
```
![alt text](images/ds2-9.png)
```
df.Pclass.unique()
```
![alt text](images/ds2-10.png)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![alt text](images/ds2-11.png)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```
![alt text](images/ds2-12.png)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![alt text](images/ds2-13.png)
```
df.boxplot(column="Age",by="Survived")
```
![alt text](images/ds2-14.png)
```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
![alt text](images/ds2-15.png)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![alt text](images/ds2-16.png)
```
sns.catplot(col="Survived",x="Gender",hue="Pclass",kind="count",data=df)
```
![alt text](images/ds2-17.png)
```
num=df.select_dtypes(exclude=[object])
sns.heatmap(num.corr(),annot=True)
```
![alt text](images/ds2-18.png)
```
sns.pairplot(df)
```
![alt text](images/ds2-19.png)
# RESULT
Hence, The EDA Analysis of an given sample has been analised successfully.

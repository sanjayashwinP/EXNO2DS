# EXNO2DS
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
### NAME:SANJAY ASHWIN P
### REG NO:212223040181
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/30ce4010-f5bb-4bb3-8abc-471ee9278eb2)
```
df.info()
```
![image](https://github.com/user-attachments/assets/a9015d2a-ae58-40b5-be3c-70af3dd93a45)

```
df.shape
```
![image](https://github.com/user-attachments/assets/ca21bffc-5ea7-4044-9ed4-8f4d6699e6f8)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/4093676f-e38c-4d06-a857-3a57c1837b8c)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/9985f865-6907-444e-844e-61d65ac3186a)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/b6591806-87e9-418f-82f1-a9fc0f0f83c4)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/d0553fe6-9b8a-4d84-8e57-65e6befe78e1)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/ec376045-4d49-4030-b454-5dbefab412da)

```
df
```
![image](https://github.com/user-attachments/assets/e6db6dbb-316d-4ad0-a217-aea051f48780)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/f88a59d5-ae07-4d8e-9d7c-41dc187fcecc)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/524043e2-8a81-418d-80be-6ffb2fdbf5e2)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/7e8a01fd-414f-41b3-a68a-bd7f99faad99)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/ba00c951-72d7-4274-85c4-419c9e096e61)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/bf63549f-9e32-4b4e-b351-5a4f9c83aef6)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/c059a3b2-92f7-4b95-8404-d8704cf7e7df)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/1e6c7b71-059e-4bea-ba26-ad2a8915a44a)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/81cd54bb-081a-4d5c-bc64-8c2a44d03e42)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/5669605d-fafd-432a-8e1f-5ff655d7c9e9)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/377e1b8b-598a-4eb0-a684-4b87f93a10aa)

# RESULT

Exploratory Data Analysis on the given data set successfully.

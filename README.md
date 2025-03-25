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
```
NAME: DEEPIKA R
REGISTRATION NO. : 212223230038
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/108c9838-ffa0-455d-8c7a-9ae6beba947a)

```
df.info()
```
![image](https://github.com/user-attachments/assets/762d8471-5ea8-4755-bf3d-df1e09d39f4b)

```
df.shape
```
![image](https://github.com/user-attachments/assets/73531609-5280-42f9-b981-0a9598cb7761)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/21b57df4-5bcc-4816-8d78-49cde75415a1)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/05f3caa0-12be-4aae-9126-eb96acb9ea78)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/841e0f38-3417-4a73-9f1b-bbe828028291)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/59c862e9-bee0-4bf1-bdcb-da0ca3cf0e04)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/ec13e15a-8686-4fad-a3fd-6a1f90d52367)

```
df
```
![image](https://github.com/user-attachments/assets/52783975-6f4a-488c-b0c9-f49973c6655c)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/e10e62e0-56d9-4ea4-8970-9af89a13ac3b)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/b393d20c-fac8-42e1-b06d-e80a16ff2643)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/3c7f3915-5e7c-4773-9d89-406585ac3b92)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/3559262c-9d73-4c38-9717-c932430d3a79)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/1db00a24-b2d7-46c4-8ccf-ca0f9d84546b)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/1a43a892-f54c-4183-8077-bce4091fff30)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/d7a126cd-7d5a-489c-ad53-33a5a09b271d)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/b7c0dd71-a11c-44b4-9bcb-8a5010afa161)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/cfdf42e8-7d07-4e37-a625-e925cc8da703)

```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/7b4917b6-6751-41e2-af92-b86da53c3536)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/fc3a0523-c626-4f2a-a07b-0dc3221f0279)

```
# RESULT
Thus this dataset has been completely analysed successfully

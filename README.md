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
NAME:DEEPIKA R
REG NO. : 212223230038
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/623d6da7-9d6b-4ac0-810e-110e14e2863c)

```
df.info()
```
![image](https://github.com/user-attachments/assets/1a4c7ae2-6fe1-485a-a566-73c70b6b2430)

```
df.shape
```
![image](https://github.com/user-attachments/assets/6bd61de5-0f0a-409f-ba82-c651bdb18eb7)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/7b369394-20e6-4a19-b859-1eef6df38383)
```

df.shape
```
![image](https://github.com/user-attachments/assets/3e54f06e-edcc-4764-8823-df69ed2ccb51)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/2180d47f-aa46-4c38-9c02-26ee7167f860)
```

df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/91317e65-eadd-4bb8-a0fd-d596bebf940e)
```

per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/4394cf2c-6dac-4536-9651-c5c8710b5219)
```

sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/165dd62f-872c-419d-875b-88c9f1cc7607)
```

df.Pclass.unique()
```
![Screenshot 2025-03-24 155230](https://github.com/user-attachments/assets/2e413ffa-c779-450f-83fc-c56e5d90026b)
```

df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-24 155146](https://github.com/user-attachments/assets/8da05a3b-afdf-478b-ad1b-0c8c2c1e4457)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/cbf826f4-f160-4c9f-b6ec-bdfb6cfc5117)
```

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/7a2ce835-4f40-47be-a05e-016cbae0f923)
```

df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/05eb1ca0-5937-4362-8229-c5c9af464fd7)
```

sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/714ccfb3-71bc-498c-b01a-4b367a963bd1)
```

sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/82259706-5fb4-440f-89a5-c70626ab44ca)
```

fig, ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/2bea70cc-fe62-4518-9002-28189cfab104)
```

sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/055305e5-cb51-4485-ae0e-ba0b0f87120f)

```
corr = df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/a39e5312-414c-422e-a1d8-a4e9e2479038)
```

sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/8b47628e-1654-431b-9be0-a9c48b114bf4)
```
# RESULT
Thus this dataset has been completely analysed successfully

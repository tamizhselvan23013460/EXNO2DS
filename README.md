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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/db8bedf0-c11d-4f29-9d1f-622a1ae15b6f)

df.info()

![image](https://github.com/user-attachments/assets/ea7add9d-925b-4b27-b366-28cf2b2334ee)

df.shape

![image](https://github.com/user-attachments/assets/68683296-311e-47bd-ac78-c6eb652aa0ba)

```
df.set_index("PassengerId",inplace=True)
df.nunique()
```

![image](https://github.com/user-attachments/assets/3531679a-d6b4-46a7-82c5-05cef665f524)


df["Survived"].value_counts()

![image](https://github.com/user-attachments/assets/53bd51e4-481f-4173-ad28-16977ca2e3d5)


```
per = (df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```


![image](https://github.com/user-attachments/assets/c8e6cd2d-4e09-47b2-82c1-895f82f35092)



df.describe()

![image](https://github.com/user-attachments/assets/e7a264bd-c0a5-425f-a81d-a53f9cb9158c)



sns.countplot(data=df,x="Survived")


![image](https://github.com/user-attachments/assets/0058c0a9-8706-4515-bbf0-c9d2a1252317)



df.Pclass.unique()


![image](https://github.com/user-attachments/assets/42d3462d-410f-4c7e-ad56-b69f97bdccc6)



```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

![image](https://github.com/user-attachments/assets/828da521-7159-4754-adcc-138d8612af78)



sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

![image](https://github.com/user-attachments/assets/a4b6f43d-85e9-411a-96d3-c25878d9fb89)



sns.catplot(x='Survived',hue="Gender",data=df,kind="count")

![image](https://github.com/user-attachments/assets/92609802-956c-486e-8f8a-82730a02326e)



df.boxplot(column="Age",by="Survived")


![image](https://github.com/user-attachments/assets/74388083-44c8-4a7d-bdeb-a21fea347e27)


sns.scatterplot(x=df["Age"],y=df["Fare"])


![image](https://github.com/user-attachments/assets/f5b7822a-d468-4bca-8fa2-d8f61eca8316)



sns.jointplot(x="Age",y="Fare",data=df)

![image](https://github.com/user-attachments/assets/fca87a31-f812-4166-b631-342036461b93)



```
fig,ax1 = plt.subplots(figsize=(8,5))
pt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

```

![image](https://github.com/user-attachments/assets/94ea0771-5100-42a4-bff2-0565408e2783)


sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")


![image](https://github.com/user-attachments/assets/ed45706e-5efa-422d-862f-2d735e2ce0a0)

```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
sns.pairplot(df)

![image](https://github.com/user-attachments/assets/0f95fc33-f37f-441f-a3ce-c0481bbae6a6)


# RESULT
        Thus the data analysis has been implemented succesfully.

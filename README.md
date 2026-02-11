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
```py
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
```
```py
dt=pd.read_csv("titanic.csv")
dt
```
<img width="1260" height="458" alt="image" src="https://github.com/user-attachments/assets/00a3d946-d151-4791-bf92-809514ef8b37" />

```py
dt.info()
```
<img width="526" height="366" alt="image" src="https://github.com/user-attachments/assets/850e8b1d-51c4-48ae-be6d-e706b56eccc4" />

```py
dt.shape
```
<img width="132" height="35" alt="image" src="https://github.com/user-attachments/assets/9c10e960-101a-4e50-87be-26b370646f99" />

```py
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
<img width="696" height="337" alt="image" src="https://github.com/user-attachments/assets/44f82481-6e5c-49c9-86c7-9747dc76510d" />

```py
dt.nunique()
```
<img width="201" height="236" alt="image" src="https://github.com/user-attachments/assets/b53def59-0cfd-43d9-9986-1209a4022548" />

```py
dt["Survived"].value_counts()
```
<img width="220" height="82" alt="image" src="https://github.com/user-attachments/assets/732efefd-0024-4f3a-83ac-4dd1a8c9c379" />

```py
per=(dt["Survived"].value_counts()/dt.shape[0]*100)
per
```
<img width="250" height="88" alt="image" src="https://github.com/user-attachments/assets/9542e798-3280-4f94-ac90-02107f34a22b" />

```py
sns.countplot(data=dt,x="Survived")
```
<img width="779" height="518" alt="image" src="https://github.com/user-attachments/assets/ce2ce2c2-a68d-40aa-b008-82ffd3b927d6" />

```py
dt
```
<img width="1326" height="504" alt="image" src="https://github.com/user-attachments/assets/3991539f-c0c8-4e0f-80c0-544d9ded4ee2" />

```py
dt.Pclass.unique()
```
<img width="144" height="35" alt="image" src="https://github.com/user-attachments/assets/937f66f5-9b4d-4051-892a-9236b9a0c40c" />

```py
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
<img width="1304" height="494" alt="image" src="https://github.com/user-attachments/assets/232f134a-a6ad-4701-b9d3-693ffa8a78e3" />

```py
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
<img width="870" height="590" alt="image" src="https://github.com/user-attachments/assets/94d2885d-dc2a-4839-aafe-9c10dfa69788" />

```py
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
<img width="651" height="579" alt="image" src="https://github.com/user-attachments/assets/35706930-15d8-4d78-88d3-9080972a3901" />

```py
dt.boxplot(column="Age",by="Survived")
```
<img width="882" height="537" alt="image" src="https://github.com/user-attachments/assets/6df86449-b15a-4b57-8d03-54fc6b7c9e40" />

```py
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
<img width="749" height="518" alt="image" src="https://github.com/user-attachments/assets/16ed5e09-37c1-47e3-bb32-4aa836a957bf" />

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
<img width="686" height="693" alt="image" src="https://github.com/user-attachments/assets/fa657197-36e0-42df-96db-4f1077336dc9" />

```py
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
<img width="796" height="527" alt="image" src="https://github.com/user-attachments/assets/62c7048c-e010-47d2-b4ca-52066461f5e8" />

```py
import seaborn as sns
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="847" height="418" alt="image" src="https://github.com/user-attachments/assets/5a0bcfe9-9ec6-414c-b00e-b385883716e2" />

```py
numeric_columns = dt.select_dtypes(include=['float64', 'int64'])
corr = numeric_columns.corr()
sns.heatmap(corr, annot=True)
```
<img width="607" height="501" alt="image" src="https://github.com/user-attachments/assets/e892db2f-8c9b-422e-927c-933745fb1106" />

```py
sns.pairplot(dt)
```
<img width="566" height="558" alt="image" src="https://github.com/user-attachments/assets/264da7a6-5356-45bf-b476-a8b1f3adc8f4" />


# RESULT
Thus,the Exploratory Data Analysis on the given data set was performed successfully.


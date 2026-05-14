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
Name: SRISHANTH J
Reg No:2122232404160
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="997" height="362" alt="image" src="https://github.com/user-attachments/assets/004fcaf9-26cb-454f-8b6f-4853464d54a7" />

```
df.info()
```
<img width="377" height="337" alt="image" src="https://github.com/user-attachments/assets/024f06f1-240d-4f21-8cec-24ba4a74db79" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="337" height="165" alt="image" src="https://github.com/user-attachments/assets/42bcd77c-9e08-4191-aa8b-bb8575ec721a" />

```
df.shape
```
<img width="157" height="41" alt="image" src="https://github.com/user-attachments/assets/05512259-473e-496f-8cf5-c8caf93fe42b" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="562" height="252" alt="image" src="https://github.com/user-attachments/assets/c913a409-1f75-4f2d-9a04-e9fedaf5e566" />

```
df.nunique()
```
<img width="185" height="222" alt="image" src="https://github.com/user-attachments/assets/b087c2c4-c114-4ca1-b6b7-fd15ac833c1f" />

```
df["Survived"].value_counts()
```
<img width="352" height="76" alt="image" src="https://github.com/user-attachments/assets/f4a01b97-4e1c-4a86-8d17-8174b7ea7fa5" />

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
<img width="367" height="75" alt="image" src="https://github.com/user-attachments/assets/09eb80b7-9215-4361-9215-40464097fd71" />

```
sns.countplot(data=df,x="Survived")
```
<img width="685" height="483" alt="image" src="https://github.com/user-attachments/assets/b53fa957-31cd-4ea0-816b-11b6a41da698" />

```
df
```
<img width="965" height="397" alt="image" src="https://github.com/user-attachments/assets/e41f42e8-c643-4cb9-9518-a290d804bafe" />

```
df.Pclass.unique()
```
<img width="377" height="38" alt="image" src="https://github.com/user-attachments/assets/6189fc1e-8ca5-44e0-b3c5-2e63256bb0df" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="995" height="401" alt="image" src="https://github.com/user-attachments/assets/efb2c1a5-2583-4bed-9d2a-41844d4b04c8" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="831" height="540" alt="image" src="https://github.com/user-attachments/assets/eeb3ab99-e5c2-4cc1-8516-80d2628d996f" />

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
<img width="641" height="533" alt="image" src="https://github.com/user-attachments/assets/8f375ac2-fa11-4237-9793-eb7fecb0591f" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="596" height="493" alt="image" src="https://github.com/user-attachments/assets/0be4b397-1454-4192-b27c-0621aa4842b0" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="642" height="461" alt="image" src="https://github.com/user-attachments/assets/f44ee912-e82e-454a-9558-2e5435f2bc91" />

```
sns.jointplot(x="Age",y="Fare",data=df)
```
<img width="630" height="632" alt="image" src="https://github.com/user-attachments/assets/b2c3c397-3627-48ad-b9e6-7c19cd0ffafa" />

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="790" height="462" alt="image" src="https://github.com/user-attachments/assets/0ba52f54-3609-4784-90dd-69d17aa57c06" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1000" height="505" alt="image" src="https://github.com/user-attachments/assets/018b1fb4-e9c8-493b-b0b6-8a6a3e9b9a49" />

```
numeric_df =df.select_dtypes(include=['number'])
corr =numeric_df.corr()
sns.heatmap(corr,annot=True)
```
<img width="580" height="467" alt="image" src="https://github.com/user-attachments/assets/0467966b-fa4f-4b2d-ad60-a6f9d9770871" />

```
sns.pairplot(df)
```
<img width="631" height="645" alt="image" src="https://github.com/user-attachments/assets/94bda8de-fd75-41c6-9beb-79c1c1a272f8" />


# RESULT
Thus, To perform Exploratory Data Analysis on the given data set is implemented successfully.

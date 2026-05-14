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
import pandas as pd
import numpy as np
import seaborn as sns
data=pd.read_csv("/content/titanic_dataset.csv")
data
```


```
data.info()

```
<img width="420" height="288" alt="Screenshot (1056)" src="https://github.com/user-attachments/assets/cf8c055c-d3ed-403d-81ae-e59b6dc8d3ec" />

```
data.describe()

```
<img width="572" height="249" alt="Screenshot (1057)" src="https://github.com/user-attachments/assets/f403763f-9f21-447d-8418-342ba164c7a3" />

```
data.dtypes

```

<img width="438" height="382" alt="Screenshot (1058)" src="https://github.com/user-attachments/assets/90e771b9-9b89-41aa-a027-3a24a78bae7f" />

```
data.shape

```

<img width="180" height="65" alt="Screenshot (1059)" src="https://github.com/user-attachments/assets/9de7c88f-80c7-4e29-8b88-a2126d645eba" />

```
data.value_counts()

```

<img width="772" height="487" alt="Screenshot (1060)" src="https://github.com/user-attachments/assets/fdb40395-eb1b-4c9e-af35-27d98898866e" />

```

data['Name'].value_counts()

```

<img width="551" height="402" alt="Screenshot (1061)" src="https://github.com/user-attachments/assets/83e16b9c-09cd-46a1-9d91-a59dc2cf3557" />

```

data.set_index("PassengerId") #or data.set_index("PassengerId", inplace=True)
data

````

<img width="778" height="476" alt="Screenshot (1062)" src="https://github.com/user-attachments/assets/f6dde0ae-3300-4c33-b6f2-4556d0b7e281" />

```

data.nunique()

```

<img width="548" height="372" alt="Screenshot (1063)" src="https://github.com/user-attachments/assets/04b8aa2f-f246-496e-9303-591a221bddb6" />

```
sns.countplot(data=data,x='Survived')

```

<img width="683" height="386" alt="Screenshot (1064)" src="https://github.com/user-attachments/assets/08a34140-e5c7-4a18-918d-fd53e5534578" />


```
data.rename(columns={'Sex':'Gender','PassengerId':'P_ID'},inplace=True)
data

```

<img width="747" height="412" alt="Screenshot (1065)" src="https://github.com/user-attachments/assets/d34ceb32-e997-49b6-9f36-9d563cbb0fb0" />

```

sns.catplot(x="Gender",col="Survived",kind="count",data=data)

```

<img width="770" height="408" alt="Screenshot (1066)" src="https://github.com/user-attachments/assets/6c0c8800-6a1d-4817-870c-10f0fffa98bc" />

```

data.boxplot(column="Age",by="Survived")

```

<img width="601" height="391" alt="Screenshot (1067)" src="https://github.com/user-attachments/assets/f2063af8-8e0e-471b-adbb-ec88368794b0" />

```

sns.scatterplot(x=data["Age"],y=data["Fare"])

```

<img width="531" height="380" alt="Screenshot (1068)" src="https://github.com/user-attachments/assets/daec3439-608d-417a-9016-d8b83ec1fc24" />

```

plt=sns.boxplot(x='Pclass', y='Age', hue='Gender', data=data)

```

<img width="619" height="372" alt="Screenshot (1069)" src="https://github.com/user-attachments/assets/9a80b6b2-d176-4f72-ba6b-2e3d93d2395c" />

```

sns.catplot(data=data, col="Survived", x="Gender", hue='Pclass', kind="count")

```

<img width="770" height="400" alt="Screenshot (1070)" src="https://github.com/user-attachments/assets/02b878c8-0777-4c6a-97a7-07e278505055" />


```

corr=data.corr(numeric_only=True)
sns.heatmap(corr,annot=True)

```
<img width="555" height="384" alt="Screenshot (1071)" src="https://github.com/user-attachments/assets/b9c7a194-1836-4e22-9d2d-6a5d903393f7" />


# RESULT

Thus, the programs are executed and verified successfully.

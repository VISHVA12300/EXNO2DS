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
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![Screenshot 2024-03-19 103913](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/fb5d6327-bc70-4d26-b021-9e30a98e2cdf)

```
dt.info()
```
![Screenshot 2024-03-19 103927](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/95297af0-30db-438e-b64a-ab63a968a3ee)


```
dt.shape
```
![Screenshot 2024-03-19 104001](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/ee1bacfc-0c43-4bab-96b3-21c59c6f61d2)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![Screenshot 2024-03-19 104010](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/3b35763f-ab40-4e7f-9ff1-3167c8b7dca8)


```
dt.nunique()
```
![Screenshot 2024-03-19 104019](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/8ac159f5-4c68-4b3a-abe5-3851d4b43ffd)


```
dt["Survived"].value_counts()
```
![Screenshot 2024-03-19 104027](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/f5229779-5563-4180-bf40-e0e34569cfe2)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2024-03-19 104041](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/b22fb34e-c689-411c-a5d8-51613fea02ea)



```
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2024-03-19 104049](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/0bc1810b-d963-45ee-8aea-396fcff46f54)



```
dt
```

![Screenshot 2024-03-19 104055](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/e72a36d7-864a-4860-a196-7d1f9efe5e54)



```
dt.Pclass.unique()
```

![Screenshot 2024-03-19 104103](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/77dee020-b47f-4200-adc9-dfa838c61983)


```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

![Screenshot 2024-03-19 104110](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/f6b3dd35-d2bd-46f2-8acf-e2cabb514635)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

![Screenshot 2024-03-19 104118](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/3cb5904c-6eb6-4471-902b-eabd859bf0c1)


```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```

![Screenshot 2024-03-19 104127](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/ab6ea156-e9eb-408b-8456-1b3cde03adb4)


```
dt.boxplot(column="Age",by="Survived")
```

![Screenshot 2024-03-19 104135](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/04c4aac0-e3ef-4b0c-859b-206a0535a828)


```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![Screenshot 2024-03-19 104142](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/aea374f8-5f53-4745-9691-29dfb07c55b2)


```
sns.jointplot(x="Age",y="Fare",data=dt)
```

![Screenshot 2024-03-19 104200](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/0467c4a0-f502-4a68-94b1-640f8f4166e9)


```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```

![Screenshot 2024-03-19 104219](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/e7c0dd46-082d-442c-ba26-b307471c7a80)


```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![Screenshot 2024-03-19 104225](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/869d53b4-5566-4563-a1d6-8528fe0a0b51)



```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![Screenshot 2024-03-19 104232](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/fb409972-abff-4d13-9c2f-da7bd10c402c)



```
sns.pairplot(dt)
```

![Screenshot 2024-03-19 104239](https://github.com/VISHVA12300/EXNO2DS/assets/119404426/c1227d7a-90c7-43c0-9328-2bcae51ef474)


# RESULT
Thus , the Exploratory Data Analysis on the given data set was performed successfully.

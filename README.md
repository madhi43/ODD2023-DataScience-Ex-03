# ODD2023-DataScience-Ex-03
# AIM

To read the given data and perform the univariate analysis with different types of plots.

# EXPLANATION

Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

# ALGORITHM

# Step1

Read the given data.

# Step2
Get the information about the data.

# Step3
Remove the null values from the data.

# Step4
Mention the datatypes from the data.

# Step5
Count the values from the data.

# Step6
Do plots like boxplots,countplot,distribution plot,histogram plot.

# Program

```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
from google.colab import files
uploaded = files.upload()
```
```
df = pd.read_csv('diabetes.csv')
df
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/e6cdaf86-1759-4fb1-81d6-7acae8e0b865)

```
df.isnull().sum()
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/75cf9c59-816e-4816-bf4c-e5795885f5ad)

```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/a020ef7d-de9d-4901-83da-20991d03d044)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/ff66070e-c9d8-4a8e-9bd0-188fdcfcde49)

```
sns.boxplot(df)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/df1b36a7-d984-4aba-91f0-f82c79dcc1b8)

```
sns.displot(x ="Glucose", data = df)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/42982430-fa32-46d1-bc9f-9ec660158d5a)


```
sns.displot(x ="BloodPressure", data = df)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/5df15c67-bf47-411f-8af7-cb795db302e7)

```
sns.displot(x ="BMI", data = df)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/19eb9c26-4c2d-4733-aeef-a6e4105fccdc)


![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/6724dfce-cf65-45f6-85eb-62da05649320)
```

sns.displot(x ="DiabetesPedigreeFunction", data = df)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/82452a69-2add-4d28-b97c-64e503123fca)


```
sns.displot(x ="Age", data = df)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/c5c55dce-0a3f-43b1-b391-3b88a203b26d)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/9496e58e-06df-4830-a53e-2d555aae0ac3)

```
df = pd.read_csv('employeesal.csv')
df
```

![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/fb132cdb-553a-4c39-892c-623dc3fba8eb)

```
df.isnull().sum()
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/e1cae3e7-4ad5-4984-b250-5401e2e09239)

```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/fd5f4a9d-1077-42a1-92ea-6d56a1e9b571)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/7cbaf37f-bb29-4aa6-a624-309bb931daf9)
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/6b85aa9d-316d-422d-8a56-b18320d56458)


```
sns.histplot(x = 'Experience_Years',data = numeric_cols)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/0f76f1b6-b92e-4475-ba79-6b9e6eda2416)
```
sns.histplot(x = 'Age',data = numeric_cols)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/91070275-5dcf-45a8-9fa3-a3b9f8d3b30c)
```
sns.histplot(x = 'Salary',data = numeric_cols)
```

![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/6470ce8f-8f95-49ff-a19a-c3acfe001661)
```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/daeb66dc-f87b-4754-8060-227dcd468388)


```
df = pd.read_csv('SuperStore.csv')
df
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/4b3c9a9c-fe37-4784-ae9a-6bf4045e7f55)
```
df.isnull().sum()
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/204f8bfc-e273-441d-8200-f3c95cc3ae58)

```
df.dropna()
```

![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/56fb739f-00f1-4814-9137-993ab18df57b)


```
df.dtypes
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/d0e9f439-d37d-4a12-9fe4-2a45d81b5b4c)



```
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/65dcb785-9bb3-4659-a7b1-877629ee2dc0)


```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]low = q1 - 1.5*iqr
```

```
sns.boxplot(numeric_cols)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/64facb03-cfab-4434-822f-6b15433ba023)

```
sns.histplot(x = 'Sales',data = numeric_cols)
```
![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/4c29f0ef-2998-4303-9793-86570417c49c)




```
sns.countplot(x="Postal Code", data=numeric_cols)
```

![image](https://github.com/madhi43/ODD2023-DataScience-Ex-03/assets/103943383/870f8348-5c48-4515-99bf-e2e80dbb4cf8)


# Result

Thus we have read the given data and performed the univariate analysis with different types of plots.










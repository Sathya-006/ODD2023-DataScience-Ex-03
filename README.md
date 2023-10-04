# ODD2023-DataScience-Ex-03
# Aim
To read the given data and perform the univariate analysis with different types of plots.

# Explanation
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

# Algorithm :
Step1
Read the given data.

Step2
Get the information about the data.

Step3
Remove the null values from the data.

Step4
Mention the datatypes from the data.

Step5
Count the values from the data.

Step6
Do plots like boxplots,countplot,distribution plot,histogram plot.

# Program:
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
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/41cb4118-df8d-4ccc-8cf8-5ba0b702cbe1)
```
df.isnull().sum()
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/85986616-a43a-488d-889c-8afcdedb165a)
```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/26296da5-0b4e-408d-9556-babe610d3f8d)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/2a713d91-d326-4d0c-8a7b-c72ee99935a7)
```
sns.boxplot(df)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/01b13bfc-4138-4d66-972d-e1ee1bec25f5)
```
sns.displot(x ="Glucose", data = df)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/7db63f8b-df72-49f5-98f8-88bd71bca717)
```
sns.displot(x ="BloodPressure", data = df)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/e8679034-419d-45e5-b2a8-45cd0ae5faa4)
```
sns.displot(x ="BMI", data = df)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/c4c18adb-3535-4064-b41b-50be7bdbc643)
```
sns.displot(x ="DiabetesPedigreeFunction", data = df)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/7e2c6ea3-4b10-424d-951d-1bf5f432affe)
```
sns.displot(x ="Age", data = df)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/3429d9cc-c068-4826-beb0-bde98aa0fdd4)
```
from google.colab import files
uploaded = files.upload()
```
```
df = pd.read_csv('employeesal.csv')
df
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/fce7bcd8-dfde-4381-a535-90c431c81d48)
```
df.isnull().sum()
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/072bc7ba-ff69-4c2e-9916-3f2c2f0d3d0a)
```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/9764b5b4-0328-46a8-86c6-d5a58df9b816)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/a032cf29-6439-4207-81ae-4c9a09c49463)
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/2478e529-cd36-4a0f-8440-1c5c1df818e7)
```
sns.histplot(x = 'Experience_Years',data = numeric_cols)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/1015d56c-2599-4c22-8bdc-ad86ef8b7a14)
```
sns.histplot(x = 'Age',data = numeric_cols)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/322f6ff3-3546-43fd-8dff-c3de9f79501d)
```
sns.histplot(x = 'Salary',data = numeric_cols)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/f950dd75-f68e-45cf-a207-1f65f916dc96)
```
from google.colab import files
uploaded = files.upload()
```
```
df = pd.read_csv('SuperStore.csv')
df
```
```
df.isnull().sum()
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/7fcbf9d2-0f73-48b5-b5ae-81d4a9158d11)
```
df.dropna()
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/ba64f23e-0c04-462c-9462-77904127086c)
```
df.dtypes
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/e7a08c04-7ca9-4e7a-8b30-c925fd791b1d)
```
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/53d133be-8e80-4793-ab22-b8e7fa3dfc74)
```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
```
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/c38c7b16-19e4-4096-8697-3ca9eb6a8134)
```
sns.histplot(x = 'Sales',data = numeric_cols)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/45cd28d6-2515-4cc3-8c0d-707440c36a90)
```
sns.countplot(x="Postal Code", data=numeric_cols)
```
![image](https://github.com/Sathya-006/ODD2023-DataScience-Ex-03/assets/121661327/db69bfc5-e169-4790-a0e8-a90bc5ca52c2)

# RESULT:
Thus we have read the given data and performed the univariate analysis with different types of plots.

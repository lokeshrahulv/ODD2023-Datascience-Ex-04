# ODD2023-Datascience-Ex-04

## AIM:
To perform Multivariate EDA on the given data set.

## EXPLAINATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The 
primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
Step1:
Import the built libraries required to perform EDA and outlier removal.
Step2:
Read the given csv file.
Step3:
Convert the file into a dataframe and get information of the data.
Step4:
Return the objects containing counts of unique values using (value_counts()).
Step5:
Plot the counts in the form of Histogram or Bar Graph.
STEP 6
Use seaborn the bar graph comparison of data can be viewed.
STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()
STEP 8
Save the final data set into the file.
## PROGRAM:
```
Developed By: Lokesh Rahul V V
Register Number:212222100024

import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('SuperStore.csv')
df.describe()
df.isnull().sum()
df.info()
# FILLING NULL VALUES
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
sns.boxplot(df)
sns.scatterplot(x=df['Region'],y=df['Sales'])
plt.figure(figsize=(10,3))
sns.barplot(x=df['State'],y=df['Sales'])
plt.xticks(rotation=90)
sns.heatmap(df.corr(),annot=True)
sns.displot(df,x='Region',hue="Category")
```
![275109768-c5042567-00d5-4c23-8abb-a2029b56ae63](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/1ccac7c3-6409-465c-b6d0-2813a7709044)
![275109816-9e8f4939-b468-4302-9073-11276501879c](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/060d9bb0-6a6a-42b7-aadd-88ed9c7af2e2)
![275109861-f98f118e-3035-4d4e-b345-77d7e6278e6f](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/9aa325ce-edc0-4889-b1e5-c108372ddb00)
![275109923-7ded794e-a9b1-4c94-806a-816207254263](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/8c859484-1f43-4e23-8c14-4f25985eba60)
![275109973-cced6367-35a0-4492-9488-a2658cef1665](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/84faa946-dc66-4244-bdff-4a65ac782e9e)
![275110038-13e1ef68-f212-453f-870d-e260194a608b](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/98cfa9d2-7030-4438-9419-ef420ba8f101)
![275110128-4b053fb9-9eab-400b-a497-14288e67087c](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/92be2961-2a21-49de-9885-cbf22bf4caa2)
![275110181-9682a83c-ab75-4649-9659-cdfacee4ec47](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/fb20aeee-b929-469d-8325-6af06181da99)

```
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('diabetes.csv')
df.describe()
df.isnull().sum()
# REMOVING OUTLIER
z = np.abs(stats.zscore(df['Glucose']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
df=df[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
df=df[(z<3)]
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])
Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)
sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])
sns.displot(df, x="Glucose", hue="Outcome")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
![275110314-7fbf2251-1aef-4cd6-8866-5e38f4c085d6](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/f91ae6d6-d86c-4dd6-acd4-1309343fb11b)
![275110365-16e01081-ec44-42a5-9185-2ff3ceca9c8a](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/807abbfd-6a59-46f2-a21c-7a1d7c7ac5c4)
![275110443-52a1a988-25bd-4d95-8956-33f6f68ca479](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/0336e08b-2021-41f6-ba13-252e46d22d8c)
![275110496-633ac96f-3287-4b2b-a673-e2560bda7805](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/bb288133-583f-4884-91c1-88f74674bcb8)
![275110586-5c7fba5b-aea5-42d2-8c2e-1c1aecd5abb4](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/0cb7e6fa-6579-4fde-b316-d8111ee0ba19)
![275110660-63692e8a-0d95-44b0-a4f8-c1ec659a9359](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/7d319c18-e575-4d96-af0d-819c3547df9a)
![275110737-7340a7be-50c3-4004-a02b-07e34008169a](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/4f463d3a-c59a-449e-8cd9-ea47615cabce)
![275110793-060691aa-48fc-4ed9-af8e-3018b07e34e0](https://github.com/lokeshrahulv/ODD2023-Datascience-Ex-04/assets/118423842/2a3acfa0-fa73-4724-8098-85f307173fa5)

## RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.

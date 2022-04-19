# Ex-04-EDA
# AIM:
To perform EDA on the given data set.
# EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
# ALGORITHM:
## STEP 1
Import the required packages(pandas,numpy,seaborn).
## STEP 2
Read and Load the Dataset
## STEP 3
Remove the null values from the data and remove the outliers.
## STEP 4
Remove the non numerical data columns using drop() method.
## STEP 5
returns object containing counts of unique values using (value_counts()).
## STEP 6
Plot the counts in the form of Histogram or Bar Graph.
## STEP 7
find the pairwise correlation of all columns in the dataframe(.corr()).
## STEP 8
Save the final data set into the file.
# CODE:
```
Developed By: Guruprasad
Register No: 212221230032

import pandas as pd 
import seaborn as sns
import matplotlib.pyplot as plt
df= pd.read_csv('supermarket.csv')
df.head()
df.info()
df.isnull().sum()
df.boxplot()
cols = ['Tax 5%', 'Total','gross margin percentage','Payment']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
df.boxplot()
df["Total"].value_counts()
plt.title('Grouped by Total')
sns.countplot(x="Total",data=df)
df["Payment"].value_counts()
plt.title('Grouped by Payment')
sns.countplot(x="Payment",data=df)
df["City"].value_counts()
plt.title('Grouped by City')
sns.countplot(x="City",data=df)
df["Product line"].value_counts()
plt.title('Grouped by Product line')
sns.countplot(x="Product line",data=df)
sns.displot(df["Quantity"])
sns.countplot(x="Gender",hue="Product line",data=df)
sns.countplot(x="Total",hue="Customer type",data=df)
pd.crosstab(df["Total"],df["Payment"])
pd.crosstab(df["Quantity"],df["City"])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:
![op1](https://user-images.githubusercontent.com/95342910/163918250-5cb4ca06-cc99-4608-a1e9-d6a7349a9077.png)
![op2](https://user-images.githubusercontent.com/95342910/163918279-85d45d04-a9a5-4fec-ae81-d2d48dbaad99.png)
![op3](https://user-images.githubusercontent.com/95342910/163918345-313266e4-5b43-4186-a661-b0366ee6bd39.png)
![op4](https://user-images.githubusercontent.com/95342910/163918358-ed6dd686-d02a-43bc-b6e5-14a13fc056f7.png)
![op5](https://user-images.githubusercontent.com/95342910/163918376-e73ea20d-e606-42df-9c20-9270f765aa6f.png)
![op6](https://user-images.githubusercontent.com/95342910/163918406-84994251-cd7d-4846-bcb7-8dbb42c78e09.png)
![op7](https://user-images.githubusercontent.com/95342910/163918428-297326e9-cb12-4ca0-ad26-4f51c3e7f0db.png)
![op8](https://user-images.githubusercontent.com/95342910/163918446-29faa3ee-6f3d-4141-908b-f1169259e4d7.png)
![op9](https://user-images.githubusercontent.com/95342910/163918468-eeb52f73-1fd4-4da4-a0d0-fa13d80ae41d.png)
![op10](https://user-images.githubusercontent.com/95342910/163918477-e2ed25e9-6d3d-4cd8-a40d-12f17faa1f9d.png)
![op11](https://user-images.githubusercontent.com/95342910/163918484-4a27be33-afbe-4a79-b5b3-3b4ffbf6f6ce.png)
![op12](https://user-images.githubusercontent.com/95342910/163918494-c4596e8e-56ec-4296-8666-353d06a3b751.png)
![op13](https://user-images.githubusercontent.com/95342910/163918506-c83ca66f-bd25-4c08-955e-1f45a9f59404.png)
![op14](https://user-images.githubusercontent.com/95342910/163918526-3070e047-2caa-4e67-ad9e-30c308dd0c81.png)
![op15](https://user-images.githubusercontent.com/95342910/163918530-eb649427-1e54-4bcb-b60f-474862dc0c81.png)
![op16](https://user-images.githubusercontent.com/95342910/163918541-8dc7b448-ccfd-40aa-8151-f3157c1da000.png)
![op17](https://user-images.githubusercontent.com/95342910/163918549-e6aa593b-d25c-4f1a-bce6-116026c304cc.png)


# RESULT:
Thus the Exploratory Data Analysis (EDA) on the given data set is successfully completed.

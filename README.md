# workshop-Multivariate-analysis
# Aim
To perform multivarient analysis on the given data set.
# Algorithm
1.Clean the data
2.Remove outliers
3.Apply the skew function and Kurtosis
4.Apply Bivariate analysis on numerical and categorical
5.Apply Multivariate analysis.
# Program
Developed by:KUMARAVEL R

Register Number:212221220029
```
Bivariate analysis
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_excel("/content/FlightInformation (1).xlsx")
df
df.info()
df.isnull().sum()
df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
df.shape
df.kurtosis()
df.skew()
sns.boxplot(x=df['Price'],y=df['Dep_Time'],data=df)
sns.scatterplot(x=df["Price"],y=df["Source"],data=df)
sns.displot(df,x="Airline",hue="Destination")
sns.barplot(x=df['Price'],y=df['Source'],data=df)

Multivariate analysis
plt.figure(figsize=(17,7))
sns.scatterplot(x=df['Price'], y=df['Source'],hue=df['Source'])
states=df.loc[:,["Dep_Time","Price"]]
states=states.groupby(by=["Dep_Time"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)
states=df.loc[:,["Airline","Price"]]
states=states.groupby(by=["Airline"]).sum().sort_values(by="Price")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Airline")
plt.ylabel=("Price")
plt.show()
df.corr(method='pearson')
sns.heatmap(df.corr(),annot=False)
```
# Output
Bivariate analysis

Dataset

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/1.jpg)


Info

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/2.jpg)


Null values

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/3.jpg)


After cleaning  

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/4.jpg)


Shape

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/5.jpg)


Skew

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/6.jpg)


Kurtosis

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/7.jpg)


Scatterplot for numerical and numerical

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/8.jpg)


Boxplot for numerical and catagorical

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/9.jpg)


Displot

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/99.jpg)


Barplot

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/999.jpg)


Multivariate analysis
Price and Source

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/9999.jpg)


Price and Dep_Time

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/99999.jpg)


Price and Airline

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/999999.jpg)


Corr()

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/9999999.jpg)
Heatmap

![](https://github.com/KumaravelIT/workshop-Multivariate-analysis/blob/main/99999999.jpg)


# Result
Thus the Bivariate and Multivariate analysis is observerd for the given data set.

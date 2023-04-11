# Ex-04-Multivariate-Analysis

# AIM

To perform Multivariate EDA on the given data set.

# Explanation:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:

### STEP 1

Import the built libraries required to perform EDA and outlier removal.

### STEP 2

Read the given csv file

### STEP 3

Convert the file into a dataframe and get information of the data.

### STEP 4

Return the objects containing counts of unique values using (value_counts()).

### STEP 5

Plot the counts in the form of Histogram or Bar Graph.

### STEP 6

Use seaborn the bar graph comparison of data can be viewed.

### STEP 7

Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8

Save the final data set into the file

# Program:

```py
Name : K.NAGUL
Register Number : 212222230089

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("/content/SuperStore.csv")
df.head()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(x=df['Row ID'],y=df['Postal Code'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("State")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(x=df['Sales'],y=df['Ship Mode'],hue=df['Category'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```

# OUTPUT:

## DF

![output](a.png)

## DF.INFO

![output](b.png)

## NULL.SUM()

![output](c.png)

## AFTER CLEANING

![output](d.png)

## DATA TYPES

![output](e.png)

## SCATTER PLOT

![output](f.png)

## BARPLOT

![output](g.png)
![output](h.png)
![output](i.png)
![output](j.png)

## CORRELATION COEFFICIENT INTERPRETATION

![output](k.png)

## HEATMAP

![output](j.png)

# RESULT:

Thus we have read the given data and performed the multivariate analysis with different types of plots.

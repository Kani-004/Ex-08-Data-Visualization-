# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE

~~~
#Reading the given dataset

import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line Plot

plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)

sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()

~~~

# OUPUT

## Reading the given dataset

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/feda5042-433a-47ad-8569-d8cfe5209a30)

# Data Visualization Using Seaborn:

## 1.Line Plot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/0fb29dc0-4de5-48b2-9ab3-812fee6c8326)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/655dbc83-3ba7-445a-8312-fb3343508fb8)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/76eb15b4-0b87-44b1-814a-915bca990165)

## 2.Scatterplot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/e680d43d-b1e6-4915-bb0b-2b8dc2d57dc4)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/c1185e58-8459-4a60-8f81-0d173496de8a)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/f38a5171-3329-4379-87f2-79d6dc3cabb8)

## 3.Boxplot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/efc56e00-16ee-43d3-904e-747d827cc221)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/c9e869ae-090a-4723-93e9-0b8fa3ff787e)

## 4.Violin Plot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/ea4181d9-6938-4b3d-a009-35272d918184)

## 5.Barplot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/d826690d-83cb-45f9-af71-e1a0896a53d4)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/4e0f081b-d3ce-4767-bf9d-be77da9a80f8)

## 6.Pointplot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/94368845-469d-4a8d-99b6-e857b6345c21)

## 7.Count plot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/379fe50a-1362-425a-a739-0f5fa1128450)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/2e6a207f-3a9f-46fb-b772-e6c7a8c59f49)

## 8.Histogram

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/b675626e-b71a-47d1-a604-a2c8856a5744)

## 9.KDE Plot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/7af366ae-611c-4d86-b1d8-4cc54f6ceeb8)

# Data Visualization Using Matplotlib:

# 1.Plot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/62a9ab64-ea11-4d5f-aa30-9050989baff6)

# 2.Heatmap

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/99413a2d-3ea3-4c60-9b79-9fa57ec8649f)

## 3.Piechart

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/fcc8f8b0-2e5b-40b0-9fc7-84bdfae56837)

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/64bc871b-3a34-4948-a4d2-9f265d0d32f8)

## 4.Histogram

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/2c60f89c-c284-41ef-84e5-fdf55939b5c0)

## 5.Bargraph

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/1b2f7e4b-04b7-47fa-89d5-cd96ddf41734)

## 6.Scatterplot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/2f5e0e7f-d03b-4ef8-bf72-2bf9eef42072)

## 7.Boxplot

![image](https://github.com/Kani-004/Ex-08-Data-Visualization-/assets/129577149/21db415d-fee8-4b8f-8961-d2369825ba48)


# RESULT

~~~

Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

~~~


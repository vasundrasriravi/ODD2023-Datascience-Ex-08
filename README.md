# Ex-08-Data-Visualization-
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
## Inserting libraries
```
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_csv("/content/Superstore - Superstore.csv (1).csv")
df.head()
df.info()
df.isnull().sum()
```
## Data Visualization using seaborn
### Lineplot
```
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

sns.lineplot(x='Ship Mode', y='Category',hue="Segment",data=df)
plt.title("Multiline Plot")
plt.show()
```
### Barplot
```
sns.barplot(x="Category",y="Sales",data=df)

sns.barplot(x='Region', y='Sales', data=df,palette='Set1')
plt.title("Sales in different Regions")
plt.show()
```
### Scatterplot
```
sns.scatterplot(x='Category',y='Sub-Category',data=df)
plt.title("Scatterplot")
plt.show()

sns.scatterplot(x='Category',y='Sub-Category',hue='Segment',data=df)
plt.show()
```
### Boxplot
```
sns.boxplot(x="Sub-Category",y="Discount",data=df)
plt.xticks(rotation=90)

sns.boxplot( x="Profit", y="Category",data=df)
```
### Pointplot
```
sns.pointplot(x=df["Quantity"],y=df["Discount"])
```
### Violinplot
```
sns.violinplot(x="Profit",data=df)
```
### Countplot
```
sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)
plt.xticks(rotation=90)
```
### Histogram
```
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```
### KDEplot
```
sns.kdeplot(x="Discount", data = df,hue='Category')
```
## Data Visualization using Matplotlib
### Plot
```
plt.plot(df['Region'], df['Sales'])
plt.show()
```
### Heatmap
```
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
### Piechart
```
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
```
### Histogram
```
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="black",bins=10)
plt.xticks(rotation =90)
plt.show()
```
### Barplot
```
plt.bar(df['Category'],df.index)
plt.show()
```
### Scatterplot
```
plt.scatter(df["Region"],df["Profit"], c ="red")
plt.show()
```
### Boxplot
```
plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUTPUT
### initial data:
![8 0](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/30f14eda-f497-49cf-b52a-7df3280f692f)

### Data information:
![8 1](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/ea54037e-b676-4151-b005-f77d75a97815)

### Null values:
![8 2](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/5f56306b-c760-4643-b42e-65de6b1b0480)

## Data Visualization using Seaborn
### Lineplot:
![8 3](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/f2c2cc06-b434-486b-a1ea-8abdd758f421)
![8 4](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/368410b6-400e-4fae-9d60-32a9c1053a02)

### Barchart:
![8 5](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/b700c4d3-05ef-48c5-aaf0-7fc608cb860a)
![8 6](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/5801f0aa-fc00-402f-b9e0-b5710c86af36)

### Scatterplot:
![8 7](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/4c277057-ab30-4d60-ade4-fd5cb67844b0)
![8 8](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/6aaac5a8-79ae-46d9-9bec-c1294fd8e36f)

### Boxplot:
![8 9](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/dfba116e-2c7f-4d78-b607-c70516a07f85)
![8 9 1](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/92ca093c-1067-41ba-9957-6723040923dc)

### Pointplot:
![8 10](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/cc90f55e-375f-43e6-a1af-32d277b5f58b)

### Violinplot:
![8 11](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/bf56f1c8-e558-41f9-972f-5778260bdf36)

### Countplot:
![8 12](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/f5db116d-bc36-4d40-82e5-cb5532d051e4)

### Histogram:
![8 13](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/62ca4f12-c8f5-4c14-8263-c57ece52aaad)
![8 14](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/260ab51f-46c7-4153-91d7-4e57995fc58d)

### KDEplot:
![8 15](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/a2c67bc7-f6f5-48f5-b728-8f8354452bdc)

## Data visualization using Matplot
### Plot:
![8 16](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/730548cf-33ca-4694-a601-0bc9036c5def)

### Heatmap:
![8 17](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/5861f119-8baa-4a5e-8303-54d6d64b5a7e)

### Piechart:
![8 18](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/7f5e1acd-593c-4a75-b0fa-ec4ae23e47e7)
![8 19](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/cddde8c7-fc11-4f9d-9260-ab7df62cd123)

### Histogram:
![8 20](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/16960bfb-2f4a-431f-866e-6c08031e206d)

### Barplot:
![8 21](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/2f88f222-745c-4e0b-a01c-de0fbae93576)

### Scatterplot:
![8 22](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/34f51820-bc21-4e11-9494-b4abf77acf4b)

### Boxplot:
![8 23](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-08/assets/119393983/42a51b03-8fcf-491d-8ccf-1208d80c862e)

# Result:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset
2.check for null values
3.Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KAVYA.K
RegisterNumber:  212222230065
*/
```
```
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```
## Output:
1.DATA.HEAD():

![image](https://github.com/kavyasenthamarai/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118668727/3793fd55-a79c-45bd-99c6-bc167d85a950)

2.DATA.INF0():

![image](https://github.com/kavyasenthamarai/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118668727/e81769c2-ea9e-4fff-b39b-b0c9c6f9a994)

3.DATA.ISNULL().SUM():

![image](https://github.com/kavyasenthamarai/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118668727/e0f026dc-1c5a-47db-b9de-cbc61d2d4878)

4.PLOT USING ELBOW METHOD:

![image](https://github.com/kavyasenthamarai/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118668727/001f7b43-9d0c-4b48-acd4-311de33bcd61)

5.K-MEANS CLUSTERING:

![image](https://github.com/kavyasenthamarai/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118668727/44bb8af7-3865-46ec-9429-cba15f34a69e)

6.Y_PRED ARRAY:

![image](https://github.com/kavyasenthamarai/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118668727/08cc7738-7e37-4a8c-80ae-9093145d02ec)

7.CUSTOMER SEGMENT:

![Uploading image.png…]()


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

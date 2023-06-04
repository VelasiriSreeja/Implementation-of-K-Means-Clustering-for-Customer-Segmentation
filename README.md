# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplot libraries.
2.import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs.
5. Display the outputs
 
 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: v.sreeja
RegisterNumber:212222230169  
*/
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
plt.xlabel("No.of.clusters")
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
plt.title("customer segments")
*/
```
## Output:
data.head() function

![Screenshot (244)](https://github.com/VelasiriSreeja/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118344328/090f6ed7-7c6d-404a-baf5-d302e0874473)

data.info

![Screenshot (245)](https://github.com/VelasiriSreeja/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118344328/1f80e3fd-482a-45b9-ac4d-3702582bc6f6)

data.isnull().sum() function

![Screenshot (246)](https://github.com/VelasiriSreeja/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118344328/b7ca6995-ce2b-45e6-9a43-414349df438f)

elbow method graph

![Screenshot (247)](https://github.com/VelasiriSreeja/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118344328/0a584a1c-f475-479e-8a63-917359d97f7d)

k means clusters

![Screenshot (248)](https://github.com/VelasiriSreeja/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118344328/98727e7d-cc54-448e-ac08-e50eb5141ba2)

customer segment graph

![Screenshot (249)](https://github.com/VelasiriSreeja/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118344328/7eb0b186-3ff6-4a58-a898-7c8bedadecb7)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

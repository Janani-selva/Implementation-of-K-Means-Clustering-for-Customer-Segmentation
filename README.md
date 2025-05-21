# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import dataset and print head,info of the dataset
2.check for null values
3.Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments 
```
## Program:
```
Developed by: Janani S
RegisterNumber: 212224230103
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
## Data.head()
![Screenshot 2025-05-21 100806](https://github.com/user-attachments/assets/f2ae2a2e-5109-4dab-95bc-fd68b7dc66a4)
## Data.info()
![Screenshot 2025-05-21 100814](https://github.com/user-attachments/assets/805fe1e1-bba3-4311-953d-e535ce7d2b5e)
## Data.isnull.sum()
![Screenshot 2025-05-21 100822](https://github.com/user-attachments/assets/4127ba67-049c-4fd3-b4a9-3ff644fa2ff2)
## Plod using Elbow Method
![Screenshot 2025-05-21 100846](https://github.com/user-attachments/assets/94e0ecea-211b-4313-92c1-fd6b18fb079d)
## K-means Clustering
![Screenshot 2025-05-21 100857](https://github.com/user-attachments/assets/ba14e6ce-7719-43f5-b278-12b685c8c13a)
## Y-pred array
![Screenshot 2025-05-21 100906](https://github.com/user-attachments/assets/8593d550-374d-45d8-8591-9a9278e43dbf)
## Customer Segment
![Screenshot 2025-05-21 100921](https://github.com/user-attachments/assets/1972e574-e9d6-4d79-8fc8-6d9523d48745)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

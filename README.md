# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages.
2. Import the dataset to work on.
3. From sklearn module import kmeans.
4. Define number of clusters to be made.
5. Assign the cluster values.
6. Plot the cluster using matplotlib.pyplot
7. End the program.
   

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Preethika N
RegisterNumber:  212223040130
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    Kmeans = KMeans(n_clusters = i,init = "k-means++")
    Kmeans.fit(data.iloc[:,3:])
    wcss.append(Kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
Km = KMeans(n_clusters = 5)
Km.fit(data.iloc[:,3:])
y_pred = Km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c = "red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c = "black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c = "blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c = "green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c = "magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:

Data head 

![image](https://github.com/preethi2831/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155142246/c79eead2-7eb7-416b-9ef9-7323a82e8189)

Data Information

![image](https://github.com/preethi2831/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155142246/f668aa7c-9971-43c8-91dc-7511aa906448)

Null data

![image](https://github.com/preethi2831/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155142246/764b94c0-08a2-4c15-a2ee-3daaaf91ac9d)

Graph

![image](https://github.com/preethi2831/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155142246/dff6cf3a-cc4e-4218-a74e-74399d183a32)

Prediction

![image](https://github.com/preethi2831/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155142246/797ecbdf-1b64-4c44-b5d7-d730cd82dc4a)

Customer graph

![image](https://github.com/preethi2831/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/155142246/36bc3148-7838-4605-a7a5-f7a51497e98f)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

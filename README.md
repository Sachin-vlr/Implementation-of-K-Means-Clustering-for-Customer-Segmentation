# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages.

2. Read the given csv file and display the few contents of the data.

3. Import KMeans and use for loop to calculate the within cluster sum of squares the data.

4. Plot the wcss for each iteration, also known as the elbow method plot.

5.Predict the clusters and plot them.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SACHIN.C
RegisterNumber:  212222230125

```

```PYTHON
import pandas as pd 
import matplotlib.pyplot as plt 
data=pd.read_csv("Mall_Customers (1).csv")

data.head()

data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []  
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:

### data.head()
![image](https://github.com/Sachin-vlr/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497666/33f035d3-76ee-4fb8-91da-ce4a4c2c1559)

### data.info()
![image](https://github.com/Sachin-vlr/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497666/0ff2e7ac-1b65-4463-ac34-4434ef978637)

### NULL VALUES
![image](https://github.com/Sachin-vlr/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497666/b0570520-b478-41d2-b7fc-5cf1babe9fa2)

### ELLBOW GRAPH
![image](https://github.com/Sachin-vlr/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497666/ace6e241-3da5-4df5-aa69-d7beba7825b8)

### CLUSTER FORMATION
![image](https://github.com/Sachin-vlr/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497666/bec446ac-a0e4-4101-a5a4-ffa4d82f8c18)

### PREDICTED VALUE
![image](https://github.com/Sachin-vlr/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497666/ae58e73f-3ff8-4a68-ac36-d41793d5763e)

### FINAL GRAPH
![image](https://github.com/Sachin-vlr/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497666/50158996-f0a4-4208-9010-9bd194e44362)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

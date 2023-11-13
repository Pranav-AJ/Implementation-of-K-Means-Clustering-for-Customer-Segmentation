# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the output and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: A.J.PRANAV
RegisterNumber: 212222230107
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data
```
```
data.head()
```
```
data.info()
```
```
data.isnull().sum()
```
```
from sklearn.cluster import KMeans
wcss = []
```
```
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
```
```
plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
```
```
km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
```
```
y_pred = km.predict(data.iloc[:,3:])
y_pred
```
```
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
plt.title("Customer Segments   ")
```
## Output:

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/8c3d9fd3-c26f-49c9-b4b1-23d14e0d38de)

### data.head()

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/763ec88c-5570-460b-a1bd-0f3ce0a85502)

### data.info()

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/e906ea4e-ccfc-4231-a866-690420641b82)

### data.isnull().sum()

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/fef49db5-5b9a-4428-824c-ef18b9431339)

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/9acf6b19-ba9f-4840-bc36-e5b802965f96)

### Elbow method graph

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/7c1ce1fd-f35e-461b-a8d7-cf642bd4ca72)

### KMeans clusters

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/7094be01-02e1-4c0f-ad91-01ff66798531)

### y_pred

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/81f13b1b-4c4e-4a36-9778-d02ddaeff9e1)

### Customers Segments Graph

![image](https://github.com/Pranav-AJ/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118904526/e23913a7-4e70-452f-ab63-af8254bf81e1)

## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

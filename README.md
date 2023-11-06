# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs. 5.Display the outputs

## Program:
```python
Program to implement the K Means Clustering for Customer Segmentation.

Developed by: KULASEKARAPANDIAN K
RegisterNumber:  212222240052
```

```python
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")
print('data.head():')
data.head()
print('data.info():')
data.info()
print('isnull() and sum():')
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
print('Elbow method diagram:')
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
print('KMeans():')
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
print('array():')
y_pred=km.predict(data.iloc[:,3:])
y_pred
print('Customer segments diagram:')
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
plt.title("Customer segments")
```

## Output:

#### HEAD VALUES:
![Alt text](241356509-13eb30e9-00fb-45a0-a8d6-68e802a446af.png)

#### DATA INFO:
![Alt text](241356541-7a998261-a53d-442b-9bd9-d66d8475f17d.png)

#### NULL:
![Alt text](241356629-02aed00f-8ad4-4533-8d13-398f47af667a.png)

#### ELBOW METHOD GRAPH:
![Alt text](241356609-c24c0019-3e36-46c5-9371-990de579961d.png)

#### KMeans:
![Alt text](241356760-6dcb359f-0af6-48c1-9f95-6bb2065cb831.png)

#### CUSTOMER SEGMENTS GRAPH:
![Alt text](241356717-53de6a5b-0333-4028-bdaf-3209e6592b45.png)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

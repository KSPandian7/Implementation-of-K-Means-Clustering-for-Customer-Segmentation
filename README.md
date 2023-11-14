## EXP NO. 08
# Implementation-of-K-Means-Clustering-for-Customer-Segmentation
### Date : 31.10.23
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot
2. Read the dataset and transform it
3. Import KMeans and fit the data in the model
4. Plot the Cluster graph

## Program:
```python

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KULASEKARAPANDIAN K
RegisterNumber: 212222240052
```

```python
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km=KMeans(n_clusters = 5)
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
plt.title("Customer Segments   ")
```
## Output:
### data.head():
![image](https://github.com/ShanmathiShanmugam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121243595/5b44c788-ae52-4d23-a439-20d93ea315da)

### data.info():
![image](https://github.com/ShanmathiShanmugam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121243595/ce55c579-cf65-4a40-9d7a-8cd921129ab1)

### data.isnull().sum()
![image](https://github.com/ShanmathiShanmugam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121243595/1623ad92-fb22-4c9f-9d2c-e99f022f9c2a)

### Elbow method Graph:
![image](https://github.com/ShanmathiShanmugam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121243595/845abcec-8790-4352-9d91-dda40d30bd88)

### Kmeans clusters:
![image](https://github.com/ShanmathiShanmugam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121243595/ea3de085-e626-4671-bd24-a7b22ba9ff07)

### Customer segments graph:
![image](https://github.com/ShanmathiShanmugam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121243595/b0a799fb-00bb-4062-9508-1c050ebc341c)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.


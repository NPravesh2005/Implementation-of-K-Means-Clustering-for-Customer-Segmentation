# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.start the program.

2.Import libraries.

3.Read the given CSV file.

4.Import KMeans and use for loop to cluster the data.

5.Predict the cluster and plot data graphs.

6.Print the outputs and end the program.

7.End the program.

## Program:
```python
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRAVESH N
RegisterNumber: 212223230154
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("C:/Users/admin/Desktop/INTR MACH/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss= [] #with-in the cluster sum of square

for i in range(1, 11):
    kmeans= KMeans(n_clusters = i , init= "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11) , wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters= 5)
km.fit(data.iloc[:, 3:])

KMeans(n_clusters= 5)

y_pred= km.predict(data.iloc[:,3:])
y_pred

data["cluster"]= y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"] , c="red", label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"] , c="black", label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"] , c="blue", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"] , c="green", label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"] , c="magenta", label="cluster4")
plt.legend()
plt.title("Customer Segements")
```

## Output:
### Elbow method:
![image](https://github.com/user-attachments/assets/e59815e8-8d4e-4848-8985-638ac3f7bfb7)

### Y-prediction:
![image](https://github.com/user-attachments/assets/e2b7eabe-3691-4af7-993d-181e088cdd25)

### Customer Segment(Cluster):
![image](https://github.com/user-attachments/assets/a815bd8f-7c8d-4bc1-9587-34dbd1f6357d)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

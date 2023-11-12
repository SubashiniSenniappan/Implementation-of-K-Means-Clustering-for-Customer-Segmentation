# Ex-08 Implementation-of-K-Means-Clustering-for-Customer-Segmentation
# Date:

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
 1.Import pandas and matplot libraries.
2.import Kmeans algorithm to solve customer segmentation.
3.Using the for loop cluster the given data
4.Predict the output and plot data graphs.
5.Display the outputs 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 
RegisterNumber:  
*/
```
```
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wess=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wess.append(kmeans.inertia_)
plt.plot(range(1,11),wess);
plt.xlabel("no of clusters")
plt.ylabel("wess")
plt.title("elbow method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income"],df0["Score"],c="red",label="cluster0")
plt.scatter(df1["Annual Income"],df1["Score"],c="black",label="cluster1")
plt.scatter(df2["Annual Income"],df2["Score"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income"],df3["Score"],c="green",label="cluster3")
plt.scatter(df4["Annual Income"],df4["Score"],c="red",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## 0UTPUT:

## DATA.HEAD():


![280380630-2d3fb8ae-d5ca-4f60-852c-000d78e97472](https://github.com/SubashiniSenniappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404951/4056f83a-91fb-4bf4-bab1-417479838457)

## DATA.INFO():

![280380766-a051b2a4-545d-48d9-b5c6-40053c7544b4](https://github.com/SubashiniSenniappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404951/a2770fb5-bc73-49eb-acbb-99a3eb1e4870)


![280380819-8077d049-16f3-4efb-9b52-d275f6d2b85a](https://github.com/SubashiniSenniappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404951/b84a80bf-372c-447c-b71d-ecf783113cf9)


![280380872-5fdcc1df-c948-4735-9e14-b21cf03c3379](https://github.com/SubashiniSenniappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404951/1187a3d7-5c31-4bda-9e53-a5d3dbc279b4)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1. Import the necessary packages using import statement. 
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program
```

## Program:
```
Program to implement the K Means Clustering for Customer 
Segmentation.


Developed by: subikshan.p
RegisterNumber: 212223240161


import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head(
data.info())
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
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
### Data.head():
<img width="404" alt="output1" src="https://user-images.githubusercontent.com/93427208/172998817-61b39c68-cd38-498e-a955-0d1ce3e5f015.png">

### Data.info():

<img width="361" alt="output2" src="https://user-images.githubusercontent.com/93427208/172998848-bdcca435-4c37-4aaa-be67-8184138d380a.png">

### Data.isnull().sum():

<img width="206" alt="output3" src="https://user-images.githubusercontent.com/93427208/172998901-61487ea7-5111-4fb6-a27b-ce3e1d028b7a.png">

### plt-Elbow Method:

<img width="399" alt="output4" src="https://user-images.githubusercontent.com/93427208/172998951-25ef29d3-df58-4c55-886f-ec5f4a26cbfa.png">

### Km.fit(data.iloc):

<img width="214" alt="output5" src="https://user-images.githubusercontent.com/93427208/172998986-8a505214-c43b-434c-ba52-88e4a332d42c.png">

### plt-Customer Segments:
<img width="214" alt="output5" src="https://user-images.githubusercontent.com/93427208/172999026-8469ff2a-7719-4da2-af35-fdf8bae4e94f.png">


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

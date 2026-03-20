# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3.Import KMeans and use for loop to cluster the data.
4.Predict the cluster and plot data graphs.
5.Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Vardhansai I 
RegisterNumber:  25015695
*/
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# ------------------------------
# Step 1: Sample dataset
# ------------------------------
data = {
    'CustomerID': [1,2,3,4,5,6,7,8,9,10],
    'Gender': ['Male','Female','Female','Male','Female','Male','Male','Female','Female','Male'],
    'Age': [19,21,20,23,31,22,35,30,25,28],
    'Annual Income (k$)': [15,16,17,18,19,20,21,22,23,24],
    'Spending Score (1-100)': [39,81,6,77,40,76,6,94,3,72]
}

df = pd.DataFrame(data)

# ------------------------------
# Step 2: Select features for clustering
# ------------------------------
X = df[['Annual Income (k$)', 'Spending Score (1-100)']]

# ------------------------------
# Step 3: Apply K-Means (choose clusters, e.g., 3)
# ------------------------------
kmeans = KMeans(n_clusters=3, init='k-means++', random_state=42)
df['Cluster'] = kmeans.fit_predict(X)  # Automatically fits and assigns clusters

# ------------------------------
# Step 4: Visualize clusters
# ------------------------------
plt.figure(figsize=(8,6))
for i in range(3):
    plt.scatter(X[df['Cluster']==i]['Annual Income (k$)'],
                X[df['Cluster']==i]['Spending Score (1-100)'],
                label=f'Cluster {i+1}')

# Plot centroids
plt.scatter(kmeans.cluster_centers_[:,0], kmeans.cluster_centers_[:,1],
            s=200, c='yellow', label='Centroids', marker='X')

plt.title('Customer Segmentation (K-Means)')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()

# ------------------------------
# Step 5: Show dataset with clusters
# ------------------------------
print(df)
```

## Output:
![K Means Clusteri<img width="706" height="1137" alt="image" src="https://github.com/user-attachments/assets/a75db46c-9625-40d2-95c6-edc47699e6ec" />
ng for Customer Segmentation](sam.png)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

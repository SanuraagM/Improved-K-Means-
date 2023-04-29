**K-Means Clustering Algorithm**

This is a simple implementation of the K-Means clustering algorithm in Python. The algorithm takes a dataset and a number of clusters as input and returns the cluster centers and the corresponding labels for each data point in the dataset.

**How to implement K Means**
1.	Import the following packages:
import numpy as np
      import seaborn as sns
      import pandas as pd
      import matplotlib.pyplot as plt

2.	Define the distance function
def dist(x1,x2,y1,y2):
               	p1=x1-x2
               	p2=y1-y2
   		n=p1**2+p2**2
   		d=np.sqrt(n)
   		return(d)

3.	Define the initial cluster centers
cluster_center = np.empty((K, 2), dtype=float)
	for i in range (K) :
  		random_row = df.sample()  
  		cluster_center[i]=random_row

4.	Calculate distance from each data point to the cluster centers
for i in range (n):
    		d[i][0]=dist(cluster_center[0][0],dfarr[i][0],cluster_center[0]				[1],dfarr[i][1]) 
   		 d[i][1]=dist(cluster_center[1][0],dfarr[i][0],cluster_center[1]				[1],dfarr[i][1])

5.	Define a function to get hold of the data point to segregate it to the respective cluster array
def find_value_location(arr, value):
    		for i in range(len(arr)):
        			for j in range(len(arr[0])):
            			if arr[i][j] == value:
                				return (j)

6.	Segregate the data points to their closest cluster centers
for i in range (n):
    	j=find_value_location(d, min(d[i]))
    	if (j==0):
      		Cluster1x=np.append(Cluster1x,dfarr[i][0])
      		Cluster1y=np.append(Cluster1y,dfarr[i][1]) 
    	elif (j==1):
      		Cluster2x=np.append(Cluster2x,dfarr[i][0])
      		Cluster2y=np.append(Cluster2y,dfarr[i][1])

7.	Update the cluster centers by taking an average of the segregated data points
cluster_center[0][0]=np.mean(Cluster1x) 
  	cluster_center[0][1]=np.mean(Cluster1y)
 	cluster_center[1][0]=np.mean(Cluster2x)
  	cluster_center[1][1]=np.mean(Cluster2y)

8.	Run a while loop until the old and the new cluster centers converge

**Changes for implementation of improved K Means**

For improved K Means the only difference is instead for defining the clusters again and again we will only check for the those points whose distance from the new cluster center is more than previous cluster center.

for i in range(n):
    J=find_value_location(d, min(d[i]))
    if new_d[i][J]>d[i][J]:                          
Here we are just comparing the new and previous distance of the point from its cluster center.

**Why use Improved K Means**

 Because the computational complexity of the standard k-means algorithm is objectionably high owing to the need to reassign the data points several times during every iteration, which makes the efficiency of standard k-means clustering low. This new algorithm presents a simple and efficient way for assigning data points to clusters. This algorithm ensures the entire process of clustering in O(nk) time without sacrificing the accuracy of clusters. Experimental results show the improved algorithm can improve the execution time of k-means algorithm. So, the proposed k-means method is feasible.

**Other Resources**

The dataset-https://www.kaggle.com/datasets/imanjowkar/clustering

For More understanding refer - https://1drv.ms/w/s!AtESBPVQLrCYi7hOa-2f0bnVpbt5Pw?e=Qpc0q8



# KNN-algorithm-scratch-implementation

## **KNN Theory and Deep Dive**

**Things you will learn in this notebook:**
* Implementation of KNN from scratch and using SK learn.
* Hyperparameter tuning and selection of optimum value of K.
* Time complexity of KNN algorithm.
* Underfitting and Overfitting of KNN algo with respect to K value selected.
* Impact of Outliers on KNN algorithm.
* Weighted Knn.

This notebook can be used to quickly revise the KNN algorithm.
                                
**1. Introduction** :
 KNN is a simple, intuitive, and versatile machine learning algorithm used for both classification and regression tasks. It's based on the principle that similar data points tend to have similar labels or target values.
 
 **2. Algorithm Overview** :
Given a dataset with labeled data points, KNN classifies new data points or predicts their target values based on the majority vote (for classification) or average (for regression) of their k nearest neighbors.
In this notebook we are just looking at the classificatio part.

**3. Steps of KNN Algorithm** :


![image.png](attachment:2fa73788-7cef-4cb1-bbcd-13f54eb0e945.png)

 Step 1: 
* Load the dataset containing labeled data points.
* Each data point has features (attributes) and a corresponding class label (for   classification) 

Step 2: 
* Choose the value of K, the number of nearest neighbors to consider.
* Choosing k is crucial and can affect the model's performance.

Step 3: 
* Normalize the attributes or features using either standard scaler or minmax scaler.
* Normalization is important in distance based algorithms, KNN is a distance based algorithm which will be explained in the notebook subsequently.

Step 4:
* Iterate the dataset and calculate the distance of each datapoint from all the datapoints and store them in a list.
* The distance calculated can be euclidean distance or manhattan distance or even cosine similarity distance.
* The type of distance depends on the number points in the dataset. If you have a very large dataset with many data points and in very high dimensions then calculating the euclidean distance if very computationally expensive (because of square root) so in such cases you can prefer manhattan distance or cosine similarty distance which are not that computationally expensive.

Step 5:
* Sort the distances in ascending order to find the K nearest neighbours.
* The best sorting algorithm takes n*log(n) time complexity.

Step 6:
* Determine the class labels of the k nearest neighbors.
* Assign the class label that appears most frequently (mode) among the k neighbors to the query point.

Step 7:
* Output the predicted class label for classification.

# CryptoClustering

**Preparing the data**
- Used the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
- Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
- The first five rows of the Scaled Dataframe are as follows:

![image](https://github.com/Anubala85/CryptoClustering/assets/158111116/c953dcac-34ff-40c8-a3d5-53dd9f03d545)

**Find the Best Value for k Using the Original Scaled DataFrame**
- Coded the elbow method algorithm to find the best value for k. Using a range from 1 to 11.
- Visually identified the optimal value for k, plotted a line chart of all the inertia values computed with the different values of k.

![image](https://github.com/Anubala85/CryptoClustering/assets/158111116/5a834ab6-f1ee-4af6-8fa9-a969e41a263f)

- Answered the following question: What’s the best value for k? - **Based on the Elbow Curve, the best value for k is `k=4`**

**Cluster the Cryptocurrencies with K-Means by Using the Original Data**
- Initialized the K-means model with four clusters by using the best value for k.
- Fitted the K-means model by using the original data.
- Predicted the clusters for grouping the cryptocurrencies by using the original data. Resulting array of cluster values below:

![image](https://github.com/Anubala85/CryptoClustering/assets/158111116/78b49ea9-1a93-4066-94e1-f73973774d8a)

- Created a copy of the original data, and then added a new column of the predicted clusters.
- Using hvPlot, created a scatter plot by setting x="price_change_percentage_24h" and y="price_change_percentage_7d". Colored the graph points with the labels that you found by using K-means. Then added the crypto name to the hover_cols parameter to identify the cryptocurrency that each data point represents.

  ![image](https://github.com/Anubala85/CryptoClustering/assets/158111116/c5a750bd-a86f-470a-baf8-51ec93933101)

**Optimize the Clusters with Principal Component Analysis**
- Created a PCA model instance, and set n_components=3.
- Used the PCA model to reduce the features to three principal components. Then reviewed the first five rows of the DataFrame.
![image](https://github.com/Anubala85/CryptoClustering/assets/158111116/02f108cf-d854-48e1-a073-18aec05d0c3e)

- Got the explained variance to determine how much information can be attributed to each principal component.
- Answered the following question: What’s the total explained variance of the three principal components?
**The Total explained variance of the three principal components is 0.895 or 89.5%**
- Created a new DataFrame with the PCA data. Set the coin_id index from the original DataFrame as the index for the new DataFrame.

**Find the Best Value for k by Using the PCA Data**
- Coded the elbow method algorithm, and used the PCA data to find the best value for k. Used a range from 1 to 11.
- Visually identified the optimal value for k, plotted a line chart of all the inertia values computed with the different values of k.
![image](https://github.com/Anubala85/CryptoClustering/assets/158111116/5a251893-7391-4980-879c-407a82e7d92f)

- Answered the following questions: What’s the best value for k when using the PCA data? Does it differ from the best value for k that you found by using the original data? **Based on the elbow curve, the best value for k when using the PCA data is k=4. No, it does not differ from the k value found using the original data**

**Cluster the Cryptocurrencies with K-means by Using the PCA Data**
- Initialized the K-means model with four clusters by using the best value for k.
- Fitted the K-means model by using the PCA data.
- Predicted the clusters for grouping the cryptocurrencies by using the PCA data. Reviewed the resulting array of cluster values.
- Created a copy of the DataFrame with the PCA data, and then added a new column to store the predicted clusters.
- Using hvPlot, created a scatter plot by setting x="PC1" and y="PC2". Colored the graph points with the labels that you found by using K-means. Then added the crypto name to the hover_cols parameter to identify the cryptocurrency that each data point represents.

![image](https://github.com/Anubala85/CryptoClustering/assets/158111116/fab37b51-3d6b-4dec-ae35-84ea25e3e6d7)

**Visualize and Compare the Results**
- Created a composite plot by using hvPlot and the plus sign (+) operator to compare the elbow curve that was created from the original data with the one that was created from the PCA data.
- Created a composite plot by using hvPlot and the plus (+) operator to compare the cryptocurrency clusters that resulted from using the original data with those that resulted from the PCA data.
- Answered the following question: Based on visually analyzing the cluster analysis results, what’s the impact of using fewer features to cluster the data by using K-means? **Using fewer features to cluster the data using K-means has resulted in concentrated clusters for clusters 0 and 3. Cluster 2 which was origninally interspersed with cluster 3 is now separated. PCA data seems to be better for further analysis compared to the original data.**
  


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

  


# CryptoClustering
In this project, Python and unsupervised learing was used to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.
## Prepare the Data
- Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
- Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
## Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best value for k using the following steps:
- Create a list with the number of k values from 1 to 11.
- Create an empty list to store the inertia values.
- Create a for loop to compute the inertia with each possible value of k.
- Create a dictionary with the data to plot the elbow curve.
- Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
- Answer the following question in your notebook: What is the best value for k?
![Elbow Curve Original Data](https://github.com/mac1033/CryptoClustering/assets/119431420/aa5ce03d-c6f7-49df-91aa-a947ed7ff5ec)

## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the original scaled DataFrame.
- Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
- Create a copy of the original data and add a new column with the predicted clusters.
- Create a scatter plot using hvPlot as follows:
- Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
- Color the graph points with the labels found using K-means.
- Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
![Scaled Plot Original Data](https://github.com/mac1033/CryptoClustering/assets/119431420/5e6396f5-30af-42e9-909c-ea4ec9a75a6d)

## Optimize Clusters with Principal Component Analysis
- Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
- Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
- What is the total explained variance of the three principal components?
- Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:
- Create a list with the number of k-values from 1 to 11.
- Create an empty list to store the inertia values.
- Create a for loop to compute the inertia with each possible value of k.
- Create a dictionary with the data to plot the Elbow curve.
- Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
- Answer the following question in your notebook:
- What is the best value for k when using the PCA data?
- Does it differ from the best k value found using the original data?
![PCA Elbow Curve](https://github.com/mac1033/CryptoClustering/assets/119431420/b7d12feb-585c-4f2c-8542-eafccb693598)

## Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the PCA data.
- Predict the clusters to group the cryptocurrencies using the PCA data.
- Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
- Create a scatter plot using hvPlot as follows:
- Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
- Color the graph points with the labels found using K-means.
- Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
![PCA Market Plot](https://github.com/mac1033/CryptoClustering/assets/119431420/db1325be-aac3-4ed8-8be9-ba0be8eb0b03)

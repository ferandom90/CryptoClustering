# CryptoClustering

Data Loading and Summary:
The code starts by importing necessary libraries and dependencies, including pandas, hvplot, and components from sklearn for clustering and dimensionality reduction.
The cryptocurrency market data is loaded from a CSV file into a Pandas DataFrame (df_market_data) with the 'coin_id' column as the index.
The first 10 rows of the data are displayed using df_market_data.head(10).
Summary statistics of the data are generated using df_market_data.describe().

Data Visualization:
The data is visualized using the hvplot library, creating a line chart with columns as x-values and their corresponding data points as y-values.

Data Normalization:
The selected columns for normalization are listed in columns_to_normalize.
The data in these columns is normalized using the StandardScaler from scikit-learn, creating the normalized_data array.
A new DataFrame (df_market_data_scaled) is created with the normalized data, retaining the coin IDs as indices.

Determining Optimal Clusters (Original Data):
The optimal number of clusters (k) is determined by computing the inertia values for different values of k using the KMeans algorithm.
A list of k values is created, and for each value, KMeans is fit on the scaled data, and the inertia values are stored.
A DataFrame (df_elbow_data_normalized) is created with k and corresponding inertia values for plotting.

PCA Analysis:
Principal Component Analysis (PCA) is applied to reduce the dimensionality of the data to three principal components.
The first five rows of the transformed PCA data are printed.
The explained variance ratio of each principal component is printed.
The total explained variance using the three principal components is calculated (0.89).

Determining Optimal Clusters (PCA Data):
Similar to the original data, the optimal number of clusters is determined using the elbow method, this time with the PCA-transformed data.
A DataFrame (df_elbow_data_pca) is created to store k and inertia values for plotting.

Clustering with K-Means (PCA Data):
KMeans is applied with the optimal k value (5) determined from the PCA data.
The clustered labels are predicted and assigned to the PCA-transformed data.
A new DataFrame (clustered_df_pca) is created to store the clustered data along with cluster labels.

Visualizing and Comparing Results:
The results of the clustering analysis are visualized using scatter plots.
Two scatter plots are generated: one for the normalized data and one for the PCA data.
Each scatter plot colors the data points based on their cluster assignments, and hovering over a point displays the corresponding coin ID.

Composite Visualization:
The two elbow curves (one for normalized data and one for PCA data) are composited into a single plot to visually compare how the optimal k values differ for each approach.
A composite scatter plot is also generated, contrasting the clustering results from normalized data and PCA data. This helps to understand the impact of using fewer features (PCA) on clustering.

Answering the Questions:
The best value for k using the original data is 4.
The best value for k using PCA data is 5, which differs from the best k value found using the original data.
The impact of using fewer features (PCA) for clustering is discussed in the final response.
Overall, the code performs exploratory data analysis, normalizes the data, determines optimal clusters using both the original and PCA-transformed data, and visualizes the results to compare the two approaches.

Overall, the code performs data loading, normalization, dimensionality reduction with PCA, cluster analysis using K-means, and various visualizations to compare the effects of different techniques on cryptocurrency clustering. It demonstrates the iterative process of exploring and analyzing data to make informed decisions about clustering.

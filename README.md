# CryptoClustering
# Cryptocurrency Clustering with K-Means and PCA

This challenge demonstrates how to cluster cryptocurrencies using the K-Means algorithm and Principal Component Analysis (PCA) for dimensionality reduction. The dataset is normalized using Scikit-learn's `StandardScaler` module and visualized for insights.

---

## Steps in the Workflow

### 1. Normalize the Data
- Use `StandardScaler()` from Scikit-learn to normalize the data from the CSV file.
- Create a new DataFrame with the scaled data, setting the `coin_id` from the original DataFrame as the index.
- Example output: the first five rows of the scaled DataFrame.

---

### 2. Find the Best Value for k (Elbow Method)
To determine the optimal number of clusters:
1. Create a list of `k` values ranging from 1 to 11.
2. Initialize an empty list to store the inertia values.
3. Use a `for` loop to compute inertia for each `k`.
4. Store the data in a dictionary for visualization.
5. Plot an elbow curve to visually identify the best value for `k`.
6. Document the chosen value of `k` in your notebook.

---

### 3. Cluster Cryptocurrencies Using the Scaled DataFrame
Steps:
- Initialize the K-Means model with the selected value of `k`.
- Fit the K-Means model to the scaled data.
- Predict clusters to group cryptocurrencies.
- Create a copy of the scaled DataFrame and add the cluster predictions as a new column.
- Use `hvPlot` to create a scatter plot:
  - X-axis: `price_change_percentage_24h`
  - Y-axis: `price_change_percentage_7d`
  - Color: cluster labels
  - Hover: display `coin_id` for each data point.

---

### 4. Optimize Clusters with PCA
- Perform PCA on the scaled DataFrame to reduce features to three principal components.
- Retrieve the explained variance to measure information retained by the principal components.
- Document the total explained variance of the three components.
- Create a new DataFrame with the PCA-transformed data, using `coin_id` as the index.
- Example output: the first five rows of the PCA DataFrame.

---

### 5. Find the Best Value for k Using the PCA DataFrame
Repeat the elbow method for the PCA DataFrame:
1. Generate a list of `k` values from 1 to 11.
2. Calculate inertia for each value of `k` in a `for` loop.
3. Plot an elbow curve to find the best value for `k`.
4. Document whether the best `k` value differs from that of the original scaled DataFrame.

---

### 6. Cluster Cryptocurrencies Using the PCA DataFrame
Steps:
- Use K-Means with the optimal `k` value from the PCA DataFrame.
- Fit the K-Means model to the PCA data.
- Predict the clusters and add them as a new column in a copy of the PCA DataFrame.
- Use `hvPlot` to create a scatter plot:
  - X-axis: `PC1`
  - Y-axis: `PC2`
  - Color: cluster labels
  - Hover: display `coin_id` for each data point.

---

### 7. Impact of PCA on Clustering
- Compare the clustering results between the original scaled data and the PCA-transformed data.
- Answer the question: What is the effect of using fewer features in clustering?

---

## Technologies Used
- **Python**: Core programming language.
- **Scikit-learn**: For normalization, PCA, and K-Means clustering.
- **hvPlot**: For creating interactive scatter plots.
- **Pandas**: Data manipulation and analysis.
- **Matplotlib/Seaborn**: For creating the elbow curve.

---

## Questions
- What is the optimal value for `k` in both scenarios (scaled data and PCA-transformed data)?
- How does PCA affect the
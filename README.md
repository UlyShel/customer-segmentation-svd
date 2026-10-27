# Customer Segmentation with K-Means and PCA

## About the project

This project explores customer segmentation using the K-Means clustering algorithm and investigates whether dimensionality reduction with PCA (implemented via SVD) can improve clustering quality on a dataset with only three numerical features.

## Dataset

The dataset contains information about 200 mall customers:

- **Age** — customer's age
- **Annual Income (k$)** — annual income in thousands of dollars
- **Spending Score (1-100)** — spending score assigned by the mall

## Methods

- Exploratory Data Analysis (EDA)
- Feature standardization with `StandardScaler`
- K-Means clustering with different numbers of clusters
- PCA implemented using Singular Value Decomposition (SVD)
- Clustering evaluation using the Silhouette Score
- Comparison of cluster assignments using Adjusted Rand Index (ARI)
- Visualization of clusters in a two-dimensional space

## Results

The best Silhouette Score among the tested K-Means configurations on the original standardized features was approximately **0.417**, obtained with 5 clusters.

In an initial experiment, reducing the data to two principal components increased the Silhouette Score to approximately **0.553** in the reduced space. However, this experiment used centered but non-standardized features for SVD, so the result is not directly comparable to the baseline.

In a subsequent experiment using standardized features, the Silhouette Score for the SVD-based clustering assignments was **0.326** when evaluated in the original feature space, compared with **0.417** for the baseline model. The Adjusted Rand Index between the two clusterings was **0.522**.

Overall, the experiments did not establish that PCA improves clustering quality. They illustrate the importance of consistent preprocessing and evaluation when comparing clustering approaches.

## Technologies

- Python
- pandas
- NumPy
- Matplotlib
- scikit-learn
- Jupyter Notebook

## How to run

1. Clone the repository.
2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Open the notebook in `notebooks/` and run the cells.

## Conclusion

This project demonstrates a basic customer segmentation workflow and compares clustering on original features with clustering after dimensionality reduction. It highlights that PCA can provide a more compact representation of data, but dimensionality reduction does not necessarily improve clustering quality.

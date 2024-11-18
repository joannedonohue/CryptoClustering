# Cryptocurrency Clustering with K-means and PCA

## Overview
This project applies **K-means clustering** and **Principal Component Analysis (PCA)** to classify cryptocurrencies based on their price fluctuations over various timeframes. By leveraging machine learning techniques, we aim to uncover patterns and group similar cryptocurrencies for better insights.

## Dataset
The data includes **price change percentages** over several timeframes:
- **24 hours**
- **7 days**
- **14 days**
- **30 days**
- **60 days**
- **200 days**
- **1 year**

The dataset is stored in a CSV file named `crypto_market_data.csv`, with the column `coin_id` representing unique cryptocurrency identifiers.

## Project Workflow

### 1. Data Loading and Preprocessing
- Load the dataset into a Pandas DataFrame.
- Normalize the data using `StandardScaler` to ensure all features have equal weight.
- Prepare the DataFrame for clustering by scaling the features and preserving the `coin_id` column for easy reference.

### 2. K-means Clustering on Scaled Data
- Use the **Elbow Method** to determine the optimal number of clusters (`k`) for the K-means algorithm.
- Fit a K-means model with the optimal value of `k = 4`.
- Assign clusters to the cryptocurrencies and visualize the clusters using scatter plots.

### 3. Dimensionality Reduction with PCA
- Reduce the dataset's dimensionality to **three principal components** using PCA.
- Analyze the explained variance to confirm that **~90%** of the variance is captured by the first three components.
- Use the PCA-transformed data to perform K-means clustering and determine the optimal number of clusters again using the Elbow Method.

### 4. Clustering with PCA Data
- Fit the K-means model on the PCA-reduced data and assign clusters.
- Visualize the clusters using scatter plots to compare results with the original scaled data.

### 5. Feature Analysis
- Analyze the influence of different features on each principal component to understand which timeframes impact the clusters the most.

## Results

### Optimal Number of Clusters
- Both the original scaled data and the PCA-transformed data suggested **4 clusters** as the optimal number (`k = 4`).

### Principal Component Analysis Insights
- **PCA1**: Primarily influenced by long-term price changes (200 days, 1 year).
- **PCA2**: Heavily influenced by mid-term changes (14 days, 30 days, 60 days).
- **PCA3**: Driven by short-term fluctuations (7 days, 14 days).

### Key Findings
- Cryptocurrencies can be effectively grouped into clusters based on their price change patterns over different timeframes.
- Dimensionality reduction using PCA preserved ~90% of the information, making the clustering more efficient while retaining key insights.

## Installation and Requirements

To run this project, you'll need the following libraries:

```bash
pip install pandas scikit-learn hvplot
```

Make sure to also have Jupyter Notebook or Google Colab installed to run the notebook.

### Usage
1. Clone the repository:
```bash
git clone https://github.com/yourusername/crypto-clustering.git
```

2. Navigate to the project directory:
```bash
cd crypto-clustering
```
3. Open the Jupyter Notebook:
```bash
jupyter notebook crypto_clustering.ipynb
```
4. Upload the dataset (crypto_market_data.csv) if using Google Colab.

### Visualizations
* Elbow Curve: Used to determine the optimal number of clusters.
* Scatter Plots: Visualize clusters based on various features and principal components.


### Future Work
* Explore additional clustering algorithms such as DBSCAN or Hierarchical Clustering.
* Apply deeper feature engineering to enhance the clustering process.
* Integrate sentiment analysis data to see if it correlates with price changes.

### Acknowledgments
The project is inspired by the K-means and PCA algorithms.
Special thanks to scikit-learn, Pandas, and hvPlot for providing the necessary tools.

### Author

Joanne Donohue

GitHub Profile: https://github.com/joannedonohue

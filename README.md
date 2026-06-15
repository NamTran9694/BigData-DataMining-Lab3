# MSCS 634 – Lab 3: Clustering Analysis Using K-Means and K-Medoids Algorithms

## Purpose
This lab explores and compares two unsupervised clustering algorithms: **K-Means** and **K-Medoids** — applied to the **Wine Dataset** from `sklearn`.  
The goal is to understand how each algorithm partitions data, evaluate cluster quality using standard metrics, and determine when each method is most appropriate.

## Dataset
- **Source:** `sklearn.datasets.load_wine`
- **Samples:** 178 wine samples
- **Features:** 13 chemical measurements (alcohol, malic acid, ash, etc.)
- **True Classes:** 3 wine cultivars (class 0: 59, class 1: 71, class 2: 48 samples)
- **Preprocessing:** Z-score normalization via `StandardScaler`

## Key Results

| Algorithm  | Silhouette Score | Adjusted Rand Index (ARI) |
|------------|:---------------:|:------------------------:|
| K-Means    | ~0.285          | ~0.898                   |
| K-Medoids  | ~0.266          | ~0.726                   |

## Key Insights

- **K-Means outperformed K-Medoids** on both metrics for this dataset. The high ARI (~0.90) shows that K-Means clusters align very closely with the true wine class labels.
- **K-Medoids** was slightly less accurate here because the dataset is well-structured and low in outliers — the very scenario where K-Means thrives.
- When clusters are approximately spherical and data is clean/scaled, **K-Means is faster and more accurate**. K-Medoids is preferred for noisy data, non-Euclidean distances, or when explainability of cluster centers matters.

## Challenges & Decisions
- **Visualization choice:** PCA was used to project 13-dimensional data into 2D for plotting since direct 2D feature subsets would not represent the full cluster structure.
- **Metric selection:** Both Silhouette Score (internal, no ground truth needed) and ARI (external, uses true labels) were included to provide a complete evaluation picture.



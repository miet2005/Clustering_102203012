# Comparative Study of Clustering Algorithms with Various Preprocessing Techniques

This repository contains a comparative performance study of different clustering algorithms on the Seeds dataset from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/machine-learning-databases/00236/seeds_dataset.txt), using a variety of preprocessing techniques and evaluated on standard clustering metrics.

## 📊 Objective

To evaluate and compare the performance of:
- **K-Means Clustering**
- **Hierarchical Clustering (Agglomerative)**
- **Mean Shift Clustering**

using different:
- **Preprocessing Techniques**:
  - No Processing
  - Normalization (`StandardScaler`)
  - Transformation (`PowerTransformer`)
  - PCA
  - Combinations: Transform + Normalization, Transform + Normalization + PCA
- **Number of Clusters**: c = 3, 4, 5 (as applicable)
- **Evaluation Metrics**:
  - Silhouette Score
  - Calinski-Harabasz Index
  - Davies-Bouldin Score

---

## 📁 Dataset

- **Dataset Name**: Seeds Dataset
- **Source**: [UCI Repository](https://archive.ics.uci.edu/ml/machine-learning-databases/00236/seeds_dataset.txt)
- **Features Used**: 
  - area, perimeter, compactness, length, width, asymmetry, groove

---

## 📘 Methodology

1. **Data Preprocessing**  
   - Applied normalization and transformation techniques.
   - PCA used to reduce dimensionality for analysis and visualization.

2. **Clustering Algorithms**  
   - Implemented using `sklearn.cluster` with selected parameters.

3. **Evaluation Metrics**  
   - `silhouette_score`, `calinski_harabasz_score`, and `davies_bouldin_score` from `sklearn.metrics`.

4. **Environment**  
   - Python with Google Colab.

---



## 📈 Visualizations

- Bar plots for metric comparison
- Heatmaps of clustering performance

---

## 📦 Files in Repository

- `miet.ipynb` – Full Colab notebook with code and outputs
- `README.md` – Project documentation
- `results/` – Screenshots or tables
- `plots/` – Graphs and cluster plots

---


## 📊 Results

### 🔹 K-Means Clustering
- **Best Silhouette Score**: 0.4963 with `Transform + Norm + PCA` (3 clusters)
- **Best Calinski-Harabasz Score**: 387.01 with `PCA` (3 clusters)
- **Best Davies-Bouldin Score**: 0.7533 with `No Processing` (3 clusters)
- **Observation**: 
  - PCA significantly boosts CH index.
  - T+N+PCA yields the best all-round performance.
  - Normalization alone leads to drop in Silhouette scores.

### 🔹 Hierarchical Clustering
- **Best Silhouette Score**: 0.4492 with `No Processing` (3 clusters)
- **Best Calinski-Harabasz Score**: 352.83 with `No Processing` (3 clusters)
- **Best Davies-Bouldin Score**: 0.6688 with `Transform + Norm + PCA` (4 clusters)
- **Observation**:
  - Strong performance on raw data for Silhouette and CH.
  - Preprocessing helps reduce DB index, especially with PCA.

### 🔹 Mean Shift Clustering
- **Best Silhouette Score**: 0.5235 with `PCA`
- **Best Calinski-Harabasz Score**: 357.80 with `PCA`
- **Best Davies-Bouldin Score**: 0.6818 with `PCA`
- **Observation**:
  - Highest Silhouette score among all algorithms.
  - Performs exceptionally with PCA and its combinations.
  - Reliable without needing to predefine cluster count.

---

## ✅ Conclusion

- 🔸 **KMeans** shows excellent results with PCA and compound preprocessing (T+N+PCA). Avoid relying solely on normalization.
- 🔸 **Hierarchical Clustering** is effective without preprocessing but benefits in DB score with `Transform + PCA`.
- 🔸 **Mean Shift** emerges as the most balanced and robust algorithm, especially in Silhouette score, performing best with `T+N+PCA`.
- 🔸 **PCA** is a consistently effective preprocessing technique across all algorithms.
- 🔸 **Transform + Norm + PCA** proves to be the most reliable preprocessing pipeline overall.

> 📌 **Insight**: Choose the algorithm and preprocessing method based on your primary metric — e.g., Silhouette for separation, Calinski-Harabasz for compactness, and Davies-Bouldin for cluster distinction.

---

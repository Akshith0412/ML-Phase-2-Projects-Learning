# Project 4: Unsupervised Learning – When Clustering Fails

## Objective
To understand the assumptions behind clustering algorithms, why evaluation metrics can be misleading, and when unsupervised learning is not a meaningful solution.

---

## Dataset
Mall Customer Segmentation Dataset (Kaggle)

---

## KMeans Analysis
- KMeans was applied on scaled features such as income and spending score.
- Elbow method and silhouette score suggested reasonable cluster counts.

### Observation
- Clusters were formed even when the separation felt arbitrary.
- Different values of k produced different yet seemingly valid groupings.

### Interpretation
KMeans always produces clusters by design, even when the data does not contain strong natural groupings.

---

## Silhouette Score Observation
- Silhouette score appeared convincing numerically.
- However, visual inspection and domain reasoning did not support meaningful segmentation.

### Key Insight
Silhouette score measures geometric separation, not real-world meaning.  
A good score does not guarantee that clusters are useful or interpretable.

---

## DBSCAN Analysis
- DBSCAN was applied using different values of eps and min_samples.
- Results varied significantly with small parameter changes.

### Observation
- Either most points were labeled as noise or a single large cluster was formed.
- Stable and interpretable clusters were difficult to obtain.

### Interpretation
DBSCAN struggled because the dataset did not exhibit consistent density, violating DBSCAN’s core assumption.

---

## Real-World Usefulness
Clustering did not meaningfully solve a real problem for this dataset.  
The data appeared to vary continuously rather than forming discrete groups.

---

## Final Honest Conclusion
In unsupervised learning, metrics can be misleading and algorithms may force structure where none exists.  
When data assumptions are violated, the correct conclusion is that clustering is not meaningful for the problem.

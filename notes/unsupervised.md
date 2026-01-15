# Unsupervised Learning – Practical Diagnostic Notes

## 1. KMeans Assumptions
- KMeans assumes clusters can be represented by centroids.
- Uses Euclidean distance to assign points to the nearest centroid.
- Works best for compact, roughly spherical, equally sized clusters.
- Always produces clusters, even if no real structure exists.

---

## 2. Silhouette Score – Common Pitfall
- Silhouette score measures compactness vs separation.
- It evaluates geometric structure, not semantic or business meaning.
- A high silhouette score can exist even when clusters are arbitrary.
- Metrics can look good while the conclusion is still wrong.

---

## 3. DBSCAN Assumptions
- DBSCAN assumes clusters are dense regions separated by sparse areas.
- Requires meaningful distance and density definitions.
- Highly sensitive to eps and min_samples.
- Struggles when data is widely spread or density varies.

---

## 4. Key Mistakes and Corrections
- Mistake: Trusting silhouette score as proof of meaningful clustering.
  - Correction: Metrics only evaluate geometry, not usefulness.

- Mistake: Assuming clustering must work because an algorithm exists.
  - Correction: Some datasets do not support unsupervised segmentation.

- Mistake: Interpreting algorithm output as truth.
  - Correction: Unsupervised models do not have ground truth and must be judged cautiously.

---

## 5. Important Question Addressed
### What to do when data assumptions are violated and clustering is not meaningful?

Correct responses include:
- Use Exploratory Data Analysis (EDA) to understand continuous patterns.
- Use anomaly detection if the goal is to find unusual behavior.
- Reformulate the problem as supervised learning if decisions are required.
- Use dimensionality reduction only for visualization, not decision-making.
- Use rule-based or domain-driven segmentation instead of forced ML.
- Explicitly conclude that no ML solution is appropriate.

Rejecting clustering is a valid and professional outcome.

---

## 6. Final Mental Model
- Unsupervised learning discovers structure; it does not create truth.
- Metrics can lie when assumptions are violated.
- The most honest ML decision can be to not use ML at all.

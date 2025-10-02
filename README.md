# Customer Segmentation (Beginner K-Means)

This mini project groups customers into clusters using two columns from `Mall_Customers.csv`:
- Annual Income (k$)
- Spending Score (1-100)

The Jupyter notebook `customer_segmentation.ipynb` does:
1. Load the CSV
2. Show basic summary of the two features
3. Plot scatter + histograms
4. Scale the features (StandardScaler)
5. Try k = 2..10 with K-Means, record SSE (inertia) + silhouette
6. Pick the k with the highest silhouette score
7. Fit final K-Means
8. Plot clusters (original + scaled space)
9. Show cluster sizes
10. (Bonus) Try DBSCAN with a few eps values (shows clusters + noise)
11. (Bonus) Analyze average spending per K-Means cluster (and per DBSCAN cluster excluding noise)
12. Save results (K-Means labels + centers)

## Files
- `Mall_Customers.csv` (input dataset)
- `customer_segmentation.ipynb` (run this)
- `customers_with_clusters.csv` (output with K-Means cluster labels)
- `cluster_centers.csv` (final K-Means cluster centers in original units)

## Quick Start
(Optional) create a virtual environment:
```
python -m venv .venv
.venv\Scripts\activate
```
Install dependencies:
```
pip install -r requirements.txt
```
Launch Jupyter (if needed):
```
pip install notebook
jupyter notebook
```
Open `customer_segmentation.ipynb` and run the cells top to bottom.

## Choosing k
We look at both the Elbow (SSE) curve and the Silhouette curve. The notebook keeps it simple and selects the k with the highest silhouette score.

## Bonus: DBSCAN
The DBSCAN cell tests a small list of `eps` values and picks the first that yields between 2 and 10 clusters (ignoring noise). Noise points are colored gray. These labels are not saved by default. To save them you can add after running the notebook:
```
# optional: save DBSCAN labels too
df.to_csv('customers_with_clusters_dbscan.csv', index=False)
```

## Average Spending Analysis
The final bonus cell prints the average spending score per K-Means cluster and (if present) per DBSCAN cluster (excluding noise with label -1). This helps compare purchasing intensity across segments.

## Outputs
After running all required cells you will see:
- `customers_with_clusters.csv` (each row has a `cluster` from K-Means)
- `cluster_centers.csv` (K-Means centers)
(Optional if you add the snippet):
- `customers_with_clusters_dbscan.csv` (with `dbscan_cluster`)

## Extending
Ideas if you want to go further:
- Add `Age` and re-run (may need 3D plots or PCA for visualization)
- Tune DBSCAN with a k-distance plot
- Try Gaussian Mixture Models and compare silhouette scores
- Label segments (e.g., High Value / Medium / Low) using center positions

## Requirements
See `requirements.txt` (pandas, numpy, scikit-learn, matplotlib, seaborn).

## License
See `LICENSE`.

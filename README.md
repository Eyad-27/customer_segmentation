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
9. Save results

## Files
- `Mall_Customers.csv` (input dataset)
- `customer_segmentation.ipynb` (run this)
- `customers_with_clusters.csv` (output with cluster labels)
- `cluster_centers.csv` (final cluster centers in original units)

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
We look at both the Elbow (SSE) curve and the Silhouette curve. The notebook keeps it simple and just selects the k with the highest silhouette score.

## Outputs
After running all cells you will see:
- `customers_with_clusters.csv` (each row has a `cluster`)
- `cluster_centers.csv` (center for each cluster)

## Extending
Ideas if you want to go further:
- Add `Age` and re-run (may need 3D plots or PCA for visualization)
- Try other clustering methods (DBSCAN, Gaussian Mixture)
- Add a simple label (e.g., High Value / Moderate / Low) based on center positions

## Requirements
See `requirements.txt` for the minimal list of libraries used.

## License
See `LICENSE`.

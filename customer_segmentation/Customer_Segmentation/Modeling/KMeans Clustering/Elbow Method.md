The elbow method is a heuristic technique used in k-means clustering to determine the optimal number of clusters(k). It works by analyzing the Within-Cluster sum of squares(WCSS) decreased as the number of cluster increases. It involves iterating through the data, generating clusters for various values of k. The k-means algorithm calculate the sum of square distances between each data point and it's assigned cluster centroid, and then assign a inertia score. By plotting the inertia scores against the k value, we create a graph that typically exhibits an elbow shape. The elbow point is the point where the value of this inertia score is the least. And we choose that as the number of cluster in our dataset.

```python
# Calculate WCSS for different K values
wcss = []
for k in range(1, 11):
    kmeans = KMeans(n_clusters=k, random_state=42)
    kmeans.fit(customer_data_scaled)
    wcss.append(kmeans.inertia_)

# Plot the Elbow Curve
plt.plot(range(1, 11),wcss, marker='o', linestyle='--', color='#FFA500', label='WCSS')
plt.title('Elbow Method to Find Optimal K', fontsize=14, fontweight='bold')
plt.xlabel('Number of Clusters (K)', fontsize=12)
plt.ylabel('WCSS (Within-Cluster Sum of Squares)', fontsize=12)

plt.grid(color='gray', linestyle='--', linewidth=0.5, alpha=0.7)
plt.axvline(x=3, linestyle='--', color='r', label='Optimal K (3)')
plt.legend(fontsize=12)
plt.tight_layout()
```

Result:

Leads to :
[[Implementation]]

So now I will apply k-means clustering with the optimal cluster size 3. In case of K-means clustering it is super important to note that k-means algorithm might assign different labels to the clusters in each run. To address this, we can use the concept of label swapping which is crucial for obtaining label consistency across different runs of the k-means algorithm, especially when the clusters are being interpreted for the real-world applications such as customer segmentation.


```python

#Apply KMEANS clustering using the optimal k

kmeans = KMeans(n_clusters = 3,init = 'k-means++',n_init = 10,max_iter= 100,random_state = 0)
kmeans.fit(customer_data_scaled)

#Get the frequency of each cluster

cluster_frequencies = Counter(kmeans.labels_)

#Create a mapping from old labels to new_labels based on frequency

label_mapping = {label:new_label for new_label,(label, _) in enumerate(cluster_frequencies.most_common())}

# Reverse the mapping to assign labels as per your criteria
label_mapping = {v: k for k, v in {2: 1, 1: 0, 0: 2,}.items()}  

# Apply the mapping to get the new labels
new_labels = np.array([label_mapping[label] for label in kmeans.labels_])

#Append the new cluster labels to the original version of the dataset
customer_data['cluster'] = new_labels

#Append the new cluster labels to the scaled version of the dataset

customer_data_scaled['cluster'] = new_labels
```

Leads to :
[[K-Means clustering]]

Tags:
#status/needs-work



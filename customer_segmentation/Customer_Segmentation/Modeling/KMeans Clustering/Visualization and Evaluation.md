This is the last part of the overall Machine learning project cycle where we try to visualize our result in a better way and evaluate the performance. I will be

- Using a pie chart to demonstrate the frequency of the points in each of the cluster
- Further, I will be evaluating the fitness of the model, unlike in supervised learning we don't have a straightforward approach to evaluating an unsupervised model but still we can use some internal and external evaluation technique to see how good the data points are clustered in the dataset. I will use
- Silhouette Score: A measure to evaluate the separation distance between the clusters. Higher values indicate better cluster separation. It ranges from -1 to 1.
- Calinski Harabasz Score: This score is used to evaluate the dispersion between within clusters. A higher score indicates better-defined clusters.

Visualization code:

```python
# Get the value counts of the 'cluster' column
cluster_counts = customer_data_scaled['cluster'].value_counts()

# Define a color palette for the pie chart
colors = sns.color_palette("colorblind", n_colors=3)  # 'Set2' is a nice palette for distinct values

# Plot the pie chart
plt.figure(figsize=(8, 6))
plt.pie(cluster_counts, labels=cluster_counts.index, autopct='%1.1f%%', colors=colors, 
        startangle=90, explode=(0.1, 0.1, 0.1), wedgeprops={'edgecolor': 'black', 'linewidth': 2})

# Customize the chart with title and legend
plt.title('Cluster Distribution')
plt.legend(cluster_counts.index, title="Clusters", loc='upper left', bbox_to_anchor=(1, 1))

# Display the chart
plt.axis('equal')  # Equal aspect ratio ensures that pie is drawn as a circle.
plt.show()

```

Result: 

![[Image4.png]]
Evaluating using silhouette method:

```python 
#Calculating the number of observation in customer_data
observations = len(customer_data_scaled)
# seperate x which has all the features except for the cluster

X = customer_data_scaled.drop(columns = ['cluster'])

# y has cluster feature
y = customer_data_scaled['cluster']
y_= customer_data_scaled['cluster'].astype('str')

# compute the metrics

silhoutte = silhouette_score(X,y)

#score = calinski_harabasz_score(X, y_)

# Print the result
print(f"Total number of observations: {observations} Silhouette score: {silhoutte} ")

```

Result: 
Total number of observations: 4067 Silhouette score: 0.5619251434386497 

From the above observation, we got a solid 0.58(Close to 0.6) score for our cluster separation which in fact is a very good value. So, it in turn tells us that our clustering algorithm is performing very well.

Leads to :

[[Profiling and Refinement]]
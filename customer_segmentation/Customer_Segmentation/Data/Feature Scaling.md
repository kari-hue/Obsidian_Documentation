
This Feature scaling  is done after . It  is one of the most crucial step that is to be followed before proceeding with any type of machine learning algorithm. As the name suggests this process is helpful in scaling down the feature(without losing its individuality) in such a way that they belong to a similar magnitude and will not create any biases during the model training process.

Here, In our problem we will be using standard scaler method for scaling our data points. Before that we need to mind all the features in our customer data table does not require scaling. Thus I will not be scaling Customer_ID,'Is_uk','Day of the week'. 


Code

```python
# Defining a scaler variable that calls standardScaler()function

scaler = StandardScaler()

# We need to exclude the columns from the table

Columns_to_scale = customer_data.columns.difference(['CustomerID', 'is_uk','Day_of_week'])

# keeping the old data safe from customer_data so using new variable 

customer_data_scaled = customer_data.copy()

# Now implementing the standard_scaler 

customer_data_scaled[Columns_to_scale] = scaler.fit_transform(customer_data_scaled[Columns_to_scale])

# Display the first few rows of the scaled data
customer_data_scaled.head()
```

Result:
![[Image3.png]]

Leads to:
[[K-Means clustering]]

Tags:
#status/completed 
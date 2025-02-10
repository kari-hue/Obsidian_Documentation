
---
date: 02.02.2025
project: Customer Segmentation
title: Task - Detecting and Handling Missing Values - Customer Segmentation
---


Template: [[Template - EDA]]
Project: [[Customer Segmentation- Project Overview]]
Works with : [[EDA - Detecting and Handling Duplicates]]

### Task

### Code snippets
```python
# Calculating the percentage of missing values for each column
missing_data = retail_data.isnull().sum()
missing_percentage = (missing_data[missing_data > 0] / retail_data.shape[0]) * 100

# Prepare values
missing_percentage.sort_values(ascending=True, inplace=True)

# Plot the barh chart
fig, ax = plt.subplots(figsize=(15, 4))
ax.barh(missing_percentage.index, missing_percentage, color='#ff6200')

# Annotate the values and indexes
for i, (value, name) in enumerate(zip(missing_percentage, missing_percentage.index)):
    ax.text(value+0.5, i, f"{value:.2f}%", ha='left', va='center', fontweight='bold', fontsize=18, color='black')

# Set x-axis limit
ax.set_xlim([0, 40])

# Add title and xlabel
plt.title("Percentage of Missing Values", fontweight='bold', fontsize=22)
plt.xlabel('Percentages (%)', fontsize=16)
plt.show

# Removing rows with missing values in 'CustomerID' and 'Description' columns

retail_data = retail_data.dropna(subset=['CustomerID', 'Description'])
```

### Result
![[Image2.png]]

### Inference

Removal of the missing value because machine learning model doesn't work properly with the missing data.

Tags:
#status/completed 







---
date: 02.02.2025
project: Customer Segmentation 
Title: Detecting and Handling Duplicates
---


Template: [[Template - EDA]]
Project: [[Customer Segmentation- Project Overview]]
Works with : [[EDA - Handling Outliers]]

### Task
*  Detecting duplicate value and then deleting them

### Code snippets
```python
## Counting the duplicate values

count_of_duplicate_values = retail_data.duplicated().sum()
print("The duplicate data in the column are", count_of_duplicate_values)#using string interpolation 

## Removing the duplicate value

retail_data.drop_duplicates(inplace = True) # with inplace the drop operation is basically permanent in the dataset
```

### Result
Permanently deleted the duplicate value to prevent any future inconsistency while training the data.

### Inference

Tags:
#status/completed 














---
Date: 02.02.2025
Project: Customer Segmentation
Title: Descriptive Statistical Analysis
---

Template: [[Template - EDA]]
Project: [[Customer Segmentation- Project Overview]]
Works with : [[EDA Detecting and Handling Missing Values - Customer Segmentation]]

### Task

* We simply try to generate simple statistical summary of our dataset(only generates for numerical value).
### Code snippets

```python
retail_data_summary = retail_data.describe()

```
### Result
![[Image1.png]]

### Inference

Quantity and unit price are the only interesting character over here.

1. Quantity:
+ The average of products in a transaction is approximately 9.55
+ The quantity has a wide range, with a minimum value of -80995 and a maximum value of 80995. The negative values indicate returned or canceled orders, which must be handled appropriately.
+ The standard deviation is quite large, indicating a significant spread in the data. The presence of outliers is marked by a large difference between the maximum and the 75th percentile values.

2. Unit price:
+ The average unit price of the product is approximately 4.61
+ The unit price also shows a wide range, from -11062.06 to 38970.00 which also shows that there is error or noise in the data, as negative prices don't make sense
+ Similar to the quantity column, the presence of outliers is indicated by the large difference between the maximum and the 75th percentile values

## Status  
#status/completed
    








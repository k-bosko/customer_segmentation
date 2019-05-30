## Table of Contents

1. [Installation](#Installation)
2. [Project Motivation](#Project-Motivation)
3. [File Descriptions](#File-Descriptions)
4. [Results](#Results)
5. [Acknowledgements](#Acknowledgements)

## Installation
- Python 3.7.2
- _Data_: the datasets belong to Bertelsmann partners AZ Direct and Arvato Financial Solutions and are private
- _Libraries_: scikit-learn, pandas, NumPy, Matplotlib, Seaborn

## Project Motivation
In this project, I apply unsupervised learning techniques to identify segments of the population that form the core customer base for a mail-order sales company in Germany. I work with real-life data provided by Bertelsmann partners AZ Direct and Arvato Finance Solution. 
Prior to applying the machine learning methods, I assess and clean the data in order to convert the data into a usable form. 

In short, I completed the following steps:
- **Step 1: Preprocessing**
  - dealed with missing data both columnwise and rowwise
  - selected and re-encoded categorical features via `pd.get_dummies`
  - engineered mixed-type features
  - created a `clean_data()` function
- **Step 2: Feature Transformation**
  - applied feature scaling using `Imputer()` and `StandardScaler()`
  - performed dimensionality reduction using sklearn's `PCA()` 
  - created `scree_plot()` function to decide upon number of principal components
  - created `map_pca` to map weights and investigate feature associations for the first 3 principal components
- **Step 3: Clustering**
  - applied `KMeans()` clustering on the general population dataset
  - used _Elbow Method_ to decide upon optimal number of clusters 
  - re-fitted the k-means model with the selected number of clusters 
  - applied the clean_data() function, the feature scaling, PCA, and clustering steps on the customer data
- **Step 4: Comparing Customer Data to Demographics Data**
  - created a plot that compared cluster distributions in the general population and the customers data
  - used `pca.inverse_transform()` to explore target clusters 


## File Descriptions
Because datasets are private, you can see only the results of the analysis in complete Jupyter Notebook here:

* [Identify_Customer_Segments.ipynb](https://github.com/k-bosko/customer_segmentation/blob/master/Identify_Customer_Segments.ipynb)

or download html-report here:
* [Identify_Customer_Segments.html](https://github.com/k-bosko/customer_segmentation/blob/master/Identify_Customer_Segments.html)

## Results
The cluster analysis of customer data and democraphics data shows that there are primarily 2 segments of the population that are interested in the company's products. The target audiences for the company are thus clusters 5 and 8, because these segments are overrepresented in the customer data. This information can then be used for targeting in a marketing campaign to maximize rate of returns.

Almost 40% of customers are in Cluster 5, followed by almost 20% in cluster 8. 

TARGET GROUPS:

**Cluster 5 - "conservative prosperous middle-aged green avangarde"**. This segment is comprised of predominantly  prosperous middle-aged Germans (from middle class to upper class) located in West Germany born in the 1960s. They prefer 'green energy' and can be classified as "green avantgarde". These are older families with kids probably already grown-up (but also single/couples). Conservative, likely religious, rational, materialistic and dutiful.

**Cluster 8 - "dominant-minded middle-aged men with average income"**: the second target group consists of mostly dominant-minded and combative men of the same age as the first target group. However, they are less affluent than the first group and belong to established/consumption oriented middleclass with average income. They are unlikely to have kids and live a bit further away from the city center than the first target group.

LEAST LIKELY CUSTOMER GROUP:

**Cluster 4 - "single less affluent women in their 20s-30s"**: The least likely customers are women born in the 1980s that come from working class and are less affluent. They are probably single or are young couples with children. Not religious, dreamful, irrational and not conservative. Price-driven with regards to energy consumption. 

## Acknowledgements
The project is part of Udacity Data Science Nanodegree. Datasets are owned by Bertelsmann partners AZ Direct and Arvato Financial Solutions and are not publicly available here.

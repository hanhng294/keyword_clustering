# Keyword Clustering
This task aims at automating one of the most crucial tasks in SEO - keyword research. The project takes keywords as input data and output clusters that group similar keywords in a cluster. The model also output a keyword that well represent the cluster to be the cluster topic

Programming language: Python
Packages: pandas, numpy, matplotlib, seaborn, sklearn, wordcloud, re, nltk, sentence_transformers
Dataset: [*societyone_keywords*](https://github.com/hanhng294/keyword_clustering/blob/main/Result.csv)

- Task Description
- Dataset Description
- Exploratory Data Analysis
- Data Handling
- Predction model
- Important features

## Task Description
In SEO, keyword research is beneficial for obtaining relevant keywords to a website. However, its process might come with many tedious and time consuming tasks such as finding keyword data and gathering them in a group. This projects aims to automate the process of grouping up keywords with great semantic similarity for automating the task of keyword clustering. This is performed by KMeans Clustering that would group keywords and find a topic for each cluster.

## Dataset description
The dataset shows the current keyword metrics for the website societyone.com.au, which is a loan company. For the keyword clustering task we will only focus on the "Keyword" column and train the model to group them up into clusters.

## Exploratory Data Analysis
- I examined the dataset by looking at summary of information as well as using visualizations (bar chart) for exploring distributions
- I used pairplot to cover all attributes and correlation plot combined with heatmap to explore correlations.

## Data Handling
- Due to high number of attributes, I dropped some columns that have low correlation with target attribute (gender) or has high correlation with
another attribute (I dropped arrival delay in minutes as it is highly correlated with Departure delay in minutes)

## Prediction Model
I used SVM and Catboost to train on training dataset and predict satisfaction on test set. The results are discussed in [*Analysis_Report.pdf*](https://github.com/hanhng294/Airline_Satisfaction/blob/main/Analysis_Report.pdf)

## Important features
I used the get_feature_importance in catboost to uncover important factors that contribute to customer satisfaction. This can help airline
companies to understand what are the deciding factors that lead to level of customer satisfaction and helo narrow down neccesary actions.
Important features are discussed in: [*Analysis_Report.pdf*](https://github.com/hanhng294/Airline_Satisfaction/blob/main/Analysis_Report.pdf)

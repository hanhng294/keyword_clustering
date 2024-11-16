# Keyword Clustering
This task aims at automating one of the most crucial tasks in SEO - keyword research. The project takes keywords as input data and output clusters that group similar keywords in a cluster. The model also output a keyword that well represent the cluster to be the cluster topic

Programming language: Python
Packages: pandas, numpy, matplotlib, seaborn, sklearn, wordcloud, re, nltk, sentence_transformers
Dataset: [*societyone_keywords*](https://github.com/hanhng294/keyword_clustering/blob/main/Result.csv)

- Task Description
- Dataset Description
- Exploratory Data Analysis
- Data processing
- K-Means clustering model
- Find topic keywords to represent clusters

## Task Description
In SEO, keyword research is beneficial for obtaining relevant keywords to a website. However, its process might come with many tedious and time consuming tasks such as finding keyword data and gathering them in a group. This projects aims to automate the process of grouping up keywords with great semantic similarity for automating the task of keyword clustering. This is performed by KMeans Clustering that would group keywords and find a topic for each cluster.

## Dataset description
The dataset shows the current keyword metrics for the website societyone.com.au, which is a loan company. For the keyword clustering task we will only focus on the "Keyword" column and train the model to group them up into clusters.

## Exploratory Data Analysis
- I examined the dataset by checking null and duplicated values
- I used wordcloud to visualize the common words in the dataset

## Data Processing
- I first remove non-ascii, stop words, punctuation and convert the words to lowercase.
- I then lemmatize the word to bring the words to original forms (for example: running will be converted to run)
- I tokenize the keywords to split them in separate words or tokens
- Word vectorization helps convert words into numbers so that machine can understand. The method I used is Term Frequency-Inverse Document Frequency

## Dimensionality Reduction
Since word vectors generate a large amount of data with high dimensionality, I applied Principal Component Analysis (PCA) to significantly reduce the dataset's dimensions while retaining 90% of the cumulative explained variance.

## K-Means Clustering
I applied K-Means clustering to group the data into 23 clusters, as was suggested by the silhouette score plot. Using the k-means++ initialization method, which helps improve the convergence speed and accuracy, the model was trained on the reduced-dimensional dataset (x_pca). A random seed of 33 was set to ensure reproducibility of the clustering results.

## Find topic keyword to represent cluster
For each cluster:
- The mean embedding of the cluster was calculated to represent its centroid.
- Cosine similarity was used to compare the keywords' embeddings with the centroid.
- The keyword closest to the centroid was selected as the representative "topic" for that cluster.

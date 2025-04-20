# Steam Recommendation System

![steam](https://github.com/HailXD/SC1015-MiniProject/blob/main/Images/Steam.jpg)
## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on steam games from [Steam Games Dataset](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data). 

For detailed walkthrough, please view the source code in order from:

0. Download games.csv from [Steam Games Dataset](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data) and place in Dataset folder
1. [Data Preprocessing & Cleaning](https://github.com/HailXD/SC1015-MiniProject/blob/main/ML_Recommendation.ipynb)
2. [EDA & Data Visualization](https://github.com/HailXD/SC1015-MiniProject/blob/main/EDA.ipynb)
3. [Recommendation Models](https://github.com/HailXD/SC1015-MiniProject/blob/main/ML_Recommendation.ipynb)
  
## Contributors

- @HailXD - EDA, Modeling
- @rarkrx - Video, Cleaning, EDA

## Problem Definition

### Background
Steam is platform for developers and users to share and play games, however, over the years, the number of games available on the platform has grown drastically.

The extensive and growing library of games on Steam makes it difficult for users to discover similar games to the ones they play.

### Motivation
For this project, we are trying to build a recommendation system for Steam Games using the [Steam Games Dataset](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data) from Kaggle, to allow users to discover similar games based on the characteristics of games they might already know or like.

This is to enhance user experience, help users discover games they might otherwise miss, understand what features are most indicative of game similarity and to create a practical recommendation model with different approaches to evaluate their effectveness.

![prediction](https://github.com/HailXD/SC1015-MiniProject/blob/main/Images/Prediction.png)

### Problem Statement
- How to effectively recommend games to a user based on the characteristics of games they might already know or like, given the massive catalog of games available on Steam?
- Which features or combination of features are most indicative of game similarity?
- Which model would be the best for this task?


## Preprocessing & Cleaning
- Correct broken format
- Inspect data types, structures, missing values
- Check for duplicates
- Handle missing values
- Drop features that are not relevant to our analysis
- Clean text data (e.g., converting to lowercase, removing punctuation and special characters)

## EDA & Data Visualization
- Understand distribution of individual features
- Check for skew in numerical columns
- Fix skews using log transformation 
- Understand distribution of categorical features 
- Word Cloud and frequency analysis for descriptions, tags, genres and categories
- Apply one-hot encoding to categorical features

## Models Used

1. TF-IDF (Term Frequency-Inverse Document Frequency) + Cosine Similarity
2. K-Nearest Neighbors (KNN) + Cosine Similarity

## Data-Driven Insights
- Many games made by indie devs and with low player count
- Metadata like Peak CCU and total reviews were heavily skewed, too many games with no players and reviews
- Common tags (Like Indie, Singleplayer, adventure,..) were everywhere, so needed to use niche tags for differentiation
- TF-IDF model performed quite bad, just only using text descriptions for similarity was not enough
- KNN model performed better, recommending some games that were also recommended by steam themselves
- Content features (tags/genres,categories) and metadata (popularity/ratings) don't correlate well with each other, but they can be used together to improve recommendation accuracy in the KNN model

## Recommendations
- Go hybrid, rely not just on game descriptions but also on metadata and content features
- Could use PCA (principal component analysis) to determine the importance of each feature
- Could experiment with Generative Retrieval, consolidate all information within a corpus into a single model
- No way to test the model at the moment, could scrape actual recommendations from steam and compare with our model's recommendations to see if they are similar

## Conclusion
- How to effectively recommend games to a user based on the characteristics of games they might already know or like, given the massive catalog of games available on Steam? Use clustering, either using TF-IDF to group similar games together
- Which features or combination of features are most indicative of game similarity? The most indicative features we found were tags, genres and categories, numerical features like peak CCU and total reviews were not very useful for similarity although were still included in the KNN model
- Which model would be the best for this task? KNN performed better
- Overall yes, it is possible to recommend games based on existing games using TF-IDF and KNN.

## Learning Beyond the Course
- Applied TF-IDF for meaningful text vectorization
- Worked with high-dimensional sparse data structures
- Used Log Transformation to fix skewed data
- Learn about practical applications of KNN for similarity-based tasks, particularly using cosine similarity
- Combined different types of features (text, categorical, numerical) into a unified representation for machine learning

## References
- https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data (Steam Games Dataset)
- https://www.quora.com/What-is-high-dimensional-sparse-data (High-Dimensional Sparse Data)
- https://www.datacamp.com/tutorial/one-hot-encoding-python-tutorial (One-Hot Encoding)
- https://medium.com/@abhishekjainindore24/tf-idf-in-nlp-term-frequency-inverse-document-frequency-e05b65932f1d (TF-IDF)
- https://www.ibm.com/think/topics/knn (KNN)
- https://www.ibm.com/think/topics/principal-component-analysis (PCA)
- https://arxiv.org/pdf/2305.05065 (Generative Retrieval)
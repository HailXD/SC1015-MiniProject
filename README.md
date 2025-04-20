# Project: Steam Recommendation System

Lab: FR1
Members
    - Chew Jun Yang (U2323006A)
    - Kong Kai Wang ()

## Individual Contributions
   **[Chew Jun Yang]:** [EDA, Modeling]
   **[Kong Kai Wang]:** [Video, Cleaning, EDA]

## Overview
[Steam](https://steamcommunity.com/) is a digital platform for developers to develop games and publish games. However, over the years, the number of games on the platform has grown drastically, making it difficult for users to discover similar games to the ones they play. In order to resolve this, our project uses the [Steam Games Dataset](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data) from Kaggle to build a recommendation system for Steam Games. 

## Problem Definition
The core problem we are trying solve is: *How to effectively recommend games to a user based on the characteristics of games they might already know or like, given the massive catalog of games available on Steam?* 

## Data Preparation and Cleaning
We used the [Steam Games Dataset](https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data) from Kaggle. The raw data required some preprocessing and cleaning. This step also provide an overview of the data. This involved:
    - Checking initial data types, structures, missing values
    - Fixing broken column names
    - Handling missing values
    - Checking for duplicates
    - Dropping features that are not relevant to our analysis
    - Cleaning text data (e.g., converting to lowercase, removing punctuation and special characters)
    - Creating a few features from existing data that would help in EDA
    
## Exploratory Data Analysis (EDA) & Visualization
This step helped us understand the structure and content of the dataset. This involved:
    Univariate analysis:
        - Understanding distribution of individual features
        - Checking for skew in numerical columns
        - Fixing skews using log transformation 
        - Understanding distribution of categorical features 
        - Word Cloud and frequency analysis for descriptions, tags, genres and categories
        - Applied one-hot encoding to categorical features
    Bivariate analysis:
        - Compared number of recommendations against estimated ownerse
        - Comparing Peak Concurrent Users across different genres
        - Investigating the length and nature of game `Descriptions`.
    Multivariate analysis:
        - Checking for correlations between features

## Models Used
    - TF-IDF (Term Frequency-Inverse Document Frequency) + Cosine Similarity
    - K-Nearest Neighbors (KNN) + Cosine Similarity

## Conclusion
    - Popularity of games has little correlation with the tags, genres and categories of games
    - Yes, it is possible to recommend games based on existing games using TF-IDF and KNN.

## Data-Driven Insights and Recommendations


## Learning Beyond the Course
    - Applied TF-IDF for meaningful text vectorization
    - Worked with high-dimensional sparse data structures
    - Used Log Transformation to fix skewed data
    - Learn about practical applications of KNN for similarity-based tasks, particularly using cosine similarity
    - Combined different types of features (text, categorical) into a unified representation for machine learning

---

## References
    - https://www.kaggle.com/datasets/fronkongames/steam-games-dataset/data
    - https://www.quora.com/What-is-high-dimensional-sparse-data
    - https://www.datacamp.com/tutorial/one-hot-encoding-python-tutorial
    - https://medium.com/@abhishekjainindore24/tf-idf-in-nlp-term-frequency-inverse-document-frequency-e05b65932f1d
    - https://www.ibm.com/think/topics/knn
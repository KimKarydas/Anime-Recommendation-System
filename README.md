![Image Alt Text](Anime_2.jpg)
# Anime-Recommendation-System

A recommendation system is a technology that analyzes user preferences and behaviours to suggest relevant items, such as products, movies, or content. It's widely used in e-commerce, streaming services, and online platforms to enhance user experience, increase engagement, and drive sales by providing personalized and tailored suggestions, improving content discoverability, and increasing user satisfaction.


- **User-Profile-Based Content Filtering**, which recommends items to users based on their individual preferences and historical interactions with items, creating user profiles to make personalized recommendations.
- **Item-Based Collaborative Filtering**,This approach recommends items (in this case, anime) based on the similarity between items. The similarity is determined by analyzing user ratings for items. The system looks for items similar to those that a user has already shown interest in.


# **Anime Recommendation System - Content Based Filtering**
[System_CB.ipynb](https://github.com/KimKarydas/Anime-Recommendation-System/blob/main/System_CB.ipynb)

I developed a content-based anime recommendation system focusing on genres. To better understand the dataset, I initially examined the first and last 5 rows, revealing multiple missing values marked as 'Unknown.' Although the dataset had 17,562 rows and 35 columns, 15,978 rows contained missing values. For this genre-based recommendation, I concentrated on the 'Genre' and 'Type' columns, ignoring missing values in other columns. After creating a new 'Tag' column combining genres and show types, I standardized the 'Tag' words for model efficiency. The final preparation involved creating a 'new_df' DataFrame with anime names, tags, and IDs.

I utilized CountVectorizer and nltk libraries for natural language processing, creating a token count matrix of genres and types. The 'Tag' column underwent standardization, and the resulting DataFrame was converted to an array. The CountVectorizer model revealed 296 distinct features. To process text data further, I employed the nltk PorterStemmer model. A function split the text in the 'Tags' column into words, reducing them to essential meanings. Using cosine_similarity, a similarity matrix was generated, allowing for comparisons of text similarities. The recommend function, part of the content-based system, suggests anime with similar content based on user input.


# **Anime Recommendation - Item-Based Collaborative Filtering**
[System_ItCF.ipynb](https://github.com/KimKarydas/Anime-Recommendation-System/blob/main/System_ItCF.ipynb)

For the collaborative filtering system based on anime ratings, I cleaned the data by converting 'Unknown' values to '0.0' in score columns. The 'new_df' DataFrame was created to include anime names and score columns. Using the cosine similarity model, I generated a similarity matrix named 'cos_matrix.' The recommend function identifies the index of a given anime, retrieves similarity scores from 'cos_matrix,' and suggests the top 5 similar anime based on these scores. 



*data source:* [Kaggle](https://www.kaggle.com/datasets/hernan4444/anime-recommendation-database-2020)

# # Movie Recommendation System

## Overview
This project is a content-based movie recommendation system that suggests movies similar to the one selected by the user. It leverages natural language processing and machine learning techniques to analyze and process movie data.

## Dataset
The system uses the *TMDB 5000 Movies Dataset*, which includes:
- Movie metadata such as genres, keywords, production companies, and cast.
- A credits dataset containing information about cast and crew.

## Technologies & Libraries Used
- *Programming Language:* Python
- *Libraries:*
  - Pandas (for data manipulation)
  - NumPy (for numerical operations)
  - Scikit-learn (for feature extraction and similarity computation)
  - NLTK (for natural language processing and stemming)
  - Ast (for handling string-to-list conversions)
  - Pickle (for model serialization)

## Data Preprocessing
1. *Data Merging:* Merged movie and credit datasets on the title column.
2. *Feature Selection:* Retained only relevant columns such as id, title, genres, keywords, cast, crew, and overview.
3. *Handling Missing Values:* Dropped rows with missing values.
4. *Text Cleaning:*
   - Converted JSON-like lists into Python lists using ast.literal_eval.
   - Extracted relevant features such as top 3 actors and directors.
   - Removed spaces and converted text to lowercase.
5. *Feature Engineering:* Created a tags column by combining genres, keywords, cast, crew, and overview.
6. *Text Vectorization:* Used CountVectorizer with max_features=5000 to transform text data into a numerical format.
7. *Stemming:* Applied the Porter Stemmer algorithm to standardize words.

## Similarity Calculation
- *Cosine Similarity:* Used to compute similarity between movies based on their feature vectors.

## Movie Recommendation Function
- The function takes a movie title as input and returns the top 5 most similar movies.
- It retrieves the index of the selected movie, computes similarity scores, and sorts them in descending order.

## Model Saving
- The final dataset and similarity matrix are stored using pickle for future use without reprocessing.

## How to Use
1. Load the movie_list.pkl and similarity.pkl files.
2. Call the recommend(movie_name) function to get movie recommendations.

## Future Enhancements
- Implement a web-based interface for user-friendly interaction.
- Integrate additional metadata for more refined recommendations.
- Experiment with deep learning-based embeddings for better accuracy.

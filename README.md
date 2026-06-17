# 🎬 Movie Recommendation System

A Content-Based Movie Recommendation System built using Python, Pandas, Scikit-learn, and NLP techniques. The system recommends movies similar to a given movie based on genres, keywords, cast, crew, and movie overview.

## 📌 Features

- Content-based filtering approach
- Recommends top 5 similar movies
- Uses movie metadata such as:
  - Genres
  - Keywords
  - Cast
  - Director
  - Overview
- Text vectorization using CountVectorizer
- Similarity calculation using Cosine Similarity
- Serialized model and processed data using Pickle for deployment

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- NLP (Text Processing)
- Pickle

## 📂 Dataset

The project uses the TMDB 5000 Movie Dataset:

- tmdb_5000_movies.csv
- tmdb_5000_credits.csv

Dataset Source:
https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

## ⚙️ Project Workflow

### 1. Data Collection
- Load movie and credits datasets.
- Merge datasets using movie title.

### 2. Data Preprocessing
- Select relevant columns:
  - movie_id
  - title
  - overview
  - genres
  - keywords
  - cast
  - crew
- Remove missing values.

### 3. Feature Engineering
- Extract:
  - Genres
  - Keywords
  - Top 3 Cast Members
  - Director
- Clean text by removing spaces.
- Combine all features into a single `tags` column.

### 4. Text Vectorization
- Apply CountVectorizer with:
  - max_features = 5000
  - stop_words = 'english'

### 5. Similarity Calculation
- Generate feature vectors.
- Compute cosine similarity between movies.

### 6. Recommendation Generation
Given a movie title:
1. Find its index.
2. Retrieve similarity scores.
3. Sort movies based on similarity.
4. Return the top 5 recommendations.

## 🚀 Example

```python
recommend("Ramanujan")
```

Output:

```text
Movie 1
Movie 2
Movie 3
Movie 4
Movie 5
```

## 📁 Files

```text
├── tmdb_5000_movies.csv
├── tmdb_5000_credits.csv
├── MovieRecommender.ipynb
├── movie_list.pkl
├── similarity.pkl
└── README.md
```

## 💾 Model Serialization

The processed movie dataset and similarity matrix are stored using Pickle:

```python
pickle.dump(new, open('movie_list.pkl', 'wb'))
pickle.dump(similarity, open('similarity.pkl', 'wb'))
```

These files can be directly used in a web application (e.g., Streamlit) for real-time recommendations.

## 📈 Future Improvements

- Add movie posters using TMDB API.
- Deploy using Streamlit.
- Include movie ratings and popularity.
- Hybrid recommendation system.
- Improve recommendations using TF-IDF and advanced NLP techniques.


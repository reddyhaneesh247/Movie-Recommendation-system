# 🎬 Movie Recommendation System

## Overview

This project is a Content-Based Movie Recommendation System that recommends movies similar to a user's selected movie using Natural Language Processing (NLP) and Cosine Similarity. The system analyzes movie metadata such as genres, keywords, cast, crew, and plot overview to identify similar movies.

## Features

* Content-based movie recommendations
* NLP-based feature engineering
* Movie similarity computation using Cosine Similarity
* Efficient recommendation generation
* Serialized recommendation artifacts using Pickle
* Fast retrieval of similar movies

## Dataset

The project uses the TMDB 5000 Movies Dataset:

* `tmdb_5000_movies.csv`
* `tmdb_5000_credits.csv`

Features utilized:

* Genres
* Keywords
* Cast
* Crew (Director)
* Overview

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* CountVectorizer
* Cosine Similarity
* Pickle

## Project Workflow

### Data Preprocessing

* Merged movies and credits datasets
* Removed missing values
* Extracted genres, keywords, cast, and director information
* Cleaned and transformed text features

### Feature Engineering

Created a combined `tags` feature containing:

* Overview
* Genres
* Keywords
* Top Cast Members
* Director

### Text Vectorization

Converted movie tags into vectors using:

```python
CountVectorizer(max_features=5000, stop_words='english')
```

### Similarity Computation

Calculated movie similarity using:

```python
cosine_similarity()
```

### Recommendation Generation

The system identifies movies with the highest similarity scores and recommends the top matching movies.

## Example

```python
recommend("Ramanjun")
```

Output:

```text
Guardians of the Galaxy
John Carter
Star Trek
Aliens
Titan A.E.
```

## Model Persistence

Serialized processed movie data and similarity matrix using Pickle:

```python
import pickle

pickle.dump(new, open('movie_list.pkl', 'wb'))
pickle.dump(similarity, open('similarity.pkl', 'wb'))
```

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/reddyhaneesh247/Movie-Recommendation-system.git
cd Movie-Recommendation-system
```

### 2. Install Required Libraries

```bash
pip install pandas numpy scikit-learn
```

### 3. Open the Notebook

Open the notebook in Google Colab or Jupyter Notebook:

```text
MovieRecommender.ipynb
```

### 4. Run All Cells

Execute all notebook cells sequentially to:

* Load and preprocess data
* Generate movie tags
* Create vector representations
* Compute cosine similarity
* Generate movie recommendations

### 5. Generate Recommendations

```python
recommend("Ramanjun")
```

The system will return the top 5 most similar movies.

## Project Structure

```text
Movie-Recommendation-system/
│
├── MovieRecommender.ipynb
├── tmdb_5000_movies.csv
├── tmdb_5000_credits.csv
├── movie_list.pkl
├── similarity.pkl
└── README.md
```
The End



